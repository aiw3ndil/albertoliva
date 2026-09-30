---
layout: post
title: "The Web Traffic Illusion: Why Social Media Falls Flat and the Dilemma of Direct Email Outreach"
date: 2026-09-30 15:51:35 +0300
categories: [technology, entrepreneurship, indie-hacking]
---

Writing technical articles takes serious effort. Researching, writing code snippets, documenting real-world bugs, and publishing with the hope of contributing something valuable to the community is deeply rewarding—until you open your analytics dashboard the next day and hear nothing but crickets.

If you maintain an independent tech blog or side project, you know the drill: you share a link on social media expecting some discussion, but the counter barely budges. Recently, I sat down to dissect the latest 7-day analytics on **enkilabs.site**, and the reality of traffic acquisition could not be more blunt.

<!--more-->

---

### What the Numbers Actually Say

Over the past week, the dashboard showed around **460 active users** and over **500 views**, showing an apparent spike of +1,900%. On paper, it looks like sudden momentum. But looking under the hood reveals where those visits actually came from:

* **Direct Traffic (`(direct) / (none)`): 427 sessions.** The overwhelming majority of the audience.
* **Organic Social Media (`t.co`, `linkedin`, `facebook`):** A combined trickle (55 sessions from X/Twitter, 6 from Facebook, 5 from LinkedIn).
* **Search Engines (`Google`, `Bing`): Just 1 visit.** (Google: 0, Bing: 1).

The posts driving that traffic were:

1. *Why I Swapped Rails for Sinatra (And the Mystery of My 98.59% Uptime)* — **162 views**
2. *The Harsh Reality of Marketing Web Projects (And the Dilemma of Dubious Directories)* — **135 views**
3. *How I Configured Postfix and OpenDKIM on Debian to Send Emails Without Falling into Spam* — **18 views**

Geographically, readers arrived mostly from cities like Amsterdam (120), Dublin (113), Ashburn (31), London (22), and New York (15).

The pattern here is unmistakable: **that 90%+ direct traffic didn't appear by chance, nor through SEO magic.** It came from a single source: **emailing links to my latest blog posts directly from my personal email account.**

---

### The Solo Developer Dilemma: Only Email Moves the Needle

Posting on LinkedIn or Twitter nowadays feels like whispering into a void unless you play the algorithmic engagement game or pay for sponsored posts. Meanwhile, search engines take months—sometimes years—to rank new independent domains against algorithmically generated content.

The only reliable way I found to get real developers to read my technical writeups was reaching out directly via email with links to what I had just published.

And that is where things get complicated.

---

### 1,200 Personal Contacts and the Legal Grey Zone

Over the years, my personal address book has grown to around 1,200 contacts: former colleagues, collaborators, acquaintances, and tech peers.

On one hand, they are the ideal audience for topics like Sinatra vs. Rails, Debian mail server setups, and infrastructure deployment. On the other hand, strictly speaking under modern privacy regulations (like the GDPR), **having someone in your contacts is not the same as having their explicit opt-in consent to receive blog updates.**

It is an uncomfortable paradox for any indie creator:

* Organic channels are heavily throttled by platform algorithms incentivizing ad spend.
* The one direct channel that works borders on unsolicited outreach.

---

### A Pragmatic Compromise: Adding an "Unsubscribe" Link to Personal Emails

I am well aware that broadcasting blog updates without prior opt-in does not strictly follow standard email compliance rules. Because I respect the people receiving these messages, I implemented a clear **unsubscribe link** at the bottom of every email I send.

While adding an unsubscribe option doesn't instantly turn cold personal outreach into a 100% compliant newsletter, it establishes essential digital courtesy:

1. **Full Transparency:** I clearly state why I'm emailing and what the post is about.
2. **Zero Friction to Opt Out:** Anyone not interested in reading my backend development or architecture notes can leave with a single click.
3. **Immediate List Pruning:** Every opt-out request is promptly removed so they never receive another update.

---

### Where Do We Go From Here?

Relying on direct outreach to personal contacts is not a sustainable, long-term solution. It risks burning goodwill and doesn't scale.

Moving forward, the goal is clear:

* Turn incoming traffic into **genuine, opt-in subscribers** through an official double-opt-in newsletter.
* Keep producing in-depth technical writeups so that organic search can gradually build up over time.
* Share writeups natively within relevant developer communities where the content provides immediate utility.

Building in public often comes with a gap between marketing best practices and day-to-day realities.

How do you tackle early distribution for your tech writeups and side projects without an ad budget? I’d love to hear your thoughts.