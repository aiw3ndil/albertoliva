---
layout: post
title: "3 Weeks of Vibe Coding: Jombo, Truek, and Enkimail"
date: 2026-02-19 10:00:00 +0200
categories: [technology, development, projects]
---

<img src="/assets/images/jombo-logo.png" alt="Project logos" style="float: left; width: 40%; margin-right: 20px; margin-bottom: 10px; border-radius: 8px;">

Lately there has been a lot of buzz around the concept of **Vibe Coding**—that way of building software where the friction between idea and execution practically vanishes thanks to AI assistance. After applying it intensely for about three weeks, I can genuinely say the result has been incredible: I have launched three fully functional, production-ready projects. The sheer velocity of iteration has been the secret sauce allowing me to juggle three distinct products in parallel.

<div style="clear: both;"></div>

<!--more-->

Here is what I've been working on:

1. **[Jombo.es](https://jombo.es)**: A community-focused carpooling platform that is completely **commission-free**. The mission is to enable shared, direct transportation in an ethical and accessible way.
2. **[Truek.xyz](https://truek.xyz)**: An item bartering and exchange platform. In a world full of clutter and consumer accumulation, Truek facilitates trading what you no longer use for what you actually need.
3. **[Enkimail.com](https://enkimail.com)**: A high-throughput email queue processor designed specifically for email marketing. It allows you to dispatch bulk campaigns efficiently and with fine-grained delivery control.

### The Tech Stack
Across all three projects, I stuck to a cohesive and repeatable stack, allowing for extreme agility:
* **Backend:** Ruby in API-only mode. Ruby's developer ergonomics and velocity remain second to none for getting ideas off the ground.
* **Frontend:** Next.js. All frontends are deployed on **Vercel's** free tier, leveraging their seamless Git integration and global CDN performance.
* **Backend Infrastructure:** All backends run side-by-side on a single virtual server orchestrated via **Coolify**. For those unfamiliar, Coolify is like running your own self-hosted Heroku—a godsend for automating container builds and SSL without exorbitant PaaS bills.

### The Infrastructure Challenge of Enkimail
The **Enkimail** project was naturally the most demanding on the systems side. I used **Docker** to spin up a customized **Postfix** mail transfer agent directly integrated with the application queues.

Anyone with experience in email marketing knows that sender IP reputation is everything. I was extraordinarily fortunate to secure a sparkling clean IP not listed on any major blocklists, which is essential to ensure emails land straight in the inbox from day one.

These three weeks have served as a powerful reminder: with modern developer tools and the right mindset, the distance between "I have an idea" and "I have a shipped product" has never been shorter.
