---
layout: post
title: "Enkimail: How I Set Up My Own Transactional Email Service with Docker and Postfix"
date: 2026-10-01 12:00:00 +0300
categories: [technology, development, self-hosting, email]
---

Ever since I started building independent web apps and side projects, reliable email delivery has been a quiet, lingering headache. When you launch a new service, you need transactional emails immediately: account verifications, password resets, order notifications, and status alerts. The conventional advice is always the same: *"Just plug in SendGrid, Mailgun, or Resend."*

In January 2026, while building the foundation for **Enkimail**, I decided to take the opposite route: setting up and hosting my own dedicated transactional mail server from scratch using Docker, Postfix, and Dovecot. Everyone asked why I would take on the deliverability baggage of mail servers in 2026. The reality? Self-hosting gives you complete architectural control, zero per-email pricing, and a crystal-clear understanding of mail deliverability that SaaS platforms keep hidden behind black boxes.

<!--more-->

---

### Why Self-Host Transactional Email?

For an indie developer or small product studio, commercial email APIs seem generous at first, but their friction compounds quickly:

* **Zero Marginal Cost:** Commercial tiers scale fast once your user base grows or when running background testing workflows. With your own infrastructure, sending 5,000 or 50,000 emails costs exactly the same as keeping your VPS alive.
* **Immunity to Arbitrary Account Suspensions:** SaaS transactional providers use aggressive automated algorithms that can flag and freeze new accounts overnight with zero human appeal process. Owning the box means nobody can cut off your transactional pipeline.
* **Full Delivery Visibility:** When an email fails or bounces, you don't wait for a delayed webhook. You can tail Postfix logs directly and inspect the exact SMTP handshake, TLS negotiation, and remote MX response.
* **Deep Architectural Knowledge:** Running a mail server forces you to truly master DNS authentication, queue management, and IP reputation—skills that pay dividends across any web infrastructure project.

---

### The Infrastructure Stack

Email delivery requires several moving parts working in harmony. To keep things modular, reproducible, and easy to redeploy, I containerized the entire stack:

1. **Postfix (MTA):** The core engine handling outbound SMTP delivery, routing, and TLS encryption.
2. **Dovecot:** Handles local mailbox storage and IMAP/POP3 protocols for receiving bounces and incoming responses.
3. **Redis:** Manages rate limiting, delivery queues, and transient state to prevent bursts that could trigger spam filters.
4. **Let's Encrypt:** Automated TLS certificates for encrypted connections between servers (`STARTTLS`).
5. **DNS Authentication Suite:** Strictly configured SPF, DKIM (2048-bit), and DMARC records to establish domain legitimacy.

---

### Core Configuration: Postfix & Docker

Running Postfix inside Docker requires careful handling of network interfaces and persistent storage for mail queues and configurations.

#### 1. Postfix Dockerfile

Here is the lightweight container definition based on a Debian/Python slim image:

```dockerfile
FROM python:3.11-slim

RUN apt-get update && apt-get install -y \
    postfix \
    redis-tools \
    dovecot-core \
    dovecot-imapd \
    libsasl2-modules \
    mailutils \
    && rm -rf /var/lib/apt/lists/*

# Postfix main configuration
ENV MAIL_HOSTNAME=mail.yourdomain.com
ENV DOMAIN=yourdomain.com

# Core Postfix settings
RUN postconf -e "myhostname = ${MAIL_HOSTNAME}" \
    && postconf -e "mydomain = ${DOMAIN}" \
    && postconf -e "myorigin = \$mydomain" \
    && postconf -e "inet_interfaces = all" \
    && postconf -e "inet_protocols = ipv4" \
    && postconf -e "mydestination = \$myhostname, localhost.\$mydomain, localhost, \$mydomain"

# Security & Anti-Relay
RUN postconf -e "smtpd_recipient_restrictions = permit_mynetworks, reject_unauth_destination" \
    && postconf -e "smtpd_relay_restrictions = permit_mynetworks, reject_unauth_destination"

# TLS & Encryption
RUN postconf -e "smtpd_tls_cert_file = /etc/ssl/certs/mail.crt" \
    && postconf -e "smtpd_tls_key_file = /etc/ssl/private/mail.key" \
    && postconf -e "smtpd_tls_security_level = may" \
    && postconf -e "smtp_tls_security_level = may" \
    && postconf -e "smtp_tls_loglevel = 1"
```

#### 2. Docker Compose Orchestration

The compose file connects the mail transfer agent with Redis for asynchronous queuing and volume mounts for persistent mail storage:

```yaml
version: "3.8"

services:
  postfix:
    build: ./postfix
    container_name: enkimail-postfix
    restart: unless-stopped
    ports:
      - "25:25"     # Standard SMTP for server-to-server delivery
      - "587:587"   # Submission port for authenticated clients
    volumes:
      - ./postfix/config:/etc/postfix
      - ./postfix/certs:/etc/ssl/certs:ro
      - ./postfix/keys:/etc/ssl/private:ro
      - mail_spool:/var/spool/postfix
    depends_on:
      - redis

  redis:
    image: redis:7-alpine
    container_name: enkimail-redis
    restart: unless-stopped
    command: redis-server --appendonly yes
    volumes:
      - redis_data:/data

volumes:
  mail_spool:
  redis_data:
```

---

### Deliverability Traps & DNS Records

Setting up the server is only 30% of the battle; the remaining 70% is earning trust with destination providers like Google, Microsoft, and ProtonMail. If your DNS is missing even one required record, your emails will go straight to the spam abyss.

#### Essential DNS Configuration

```dns
; 1. A Record for the Mail Host
mail.yourdomain.com.    IN A        YOUR_SERVER_IP

; 2. MX Record pointing to your mail server
yourdomain.com.         IN MX 10    mail.yourdomain.com.

; 3. SPF (Sender Policy Framework) - Authorized sending IPs
yourdomain.com.         IN TXT      "v=spf1 mx ip4:YOUR_SERVER_IP -all"

; 4. DKIM (DomainKeys Identified Mail) - 2048-bit Public Key
mail._domainkey.yourdomain.com. IN TXT (
    "v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA..."
)

; 5. DMARC (Domain-based Message Authentication)
_dmarc.yourdomain.com.  IN TXT      "v=DMARC1; p=none; rua=mailto:dmarc-reports@yourdomain.com; pct=100; sp=none"
```

#### Critical Rules to Avoid the Spam Folder

1. **Reverse DNS (PTR Record):** Ensure your hosting provider configures the PTR record for `YOUR_SERVER_IP` to resolve back to `mail.yourdomain.com`. Without valid rDNS, Gmail will reject your connection on the spot.
2. **Gradual IP Warmup:** Never send hundreds of emails on day one from a fresh IP address. Start by sending 10 to 20 emails per day to known friendly addresses, verify they inbox, and slowly ramp up volume over several weeks.
3. **Progressive DMARC Enforcement:** Start with `p=none` to collect failure reports without blocking deliveries. Once your SPF and DKIM pass 100% of reports, graduate to `p=quarantine`, and finally `p=reject`.
4. **Bounce & Feedback Monitoring:** Keep your hard bounce rate strictly below 2%. High bounce rates signal stale or harvested lists to spam heuristics.

---

### Lessons Learned & Final Reflections

Running self-hosted transactional email for Enkimail has proven that the supposed "impossible barrier" to email self-hosting is largely a myth sustained by SaaS marketing. Once the fundamental DNS records (SPF, DKIM, DMARC, rDNS) are properly configured and your IP is treated with patience, deliverability is remarkably rock-solid.

The peace of mind that comes from knowing your transactional infrastructure is entirely under your control—running on simple, battle-tested open-source software—makes the initial setup well worth every hour spent in the terminal.

---

_This article is part of the ongoing Enkimail and Enkihost series documenting independent developer infrastructure._
