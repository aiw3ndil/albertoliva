---
layout: post
title: "The Solitary Builder: What Nietzsche Can Teach an Indie Developer"
date: 2026-10-01 20:30:00 +0300
categories: [philosophy, reflection, indie-hacking]
tags: [nietzsche, amor-fati, solitude, building-in-public]
---

For the last few weeks, this blog has been split in two. On one side, the technical posts: Postfix containers, procedural dungeons in GDScript, analytics dashboards that refuse to move. On the other, the quieter posts about Nietzsche, solitude, and the strange light of a Finnish autumn.

I used to think these were two different versions of me. Lately I suspect they are the same conversation. Building something alone, with no audience and no guarantee, is not only an engineering problem or a marketing problem. It is a philosophical one. And the philosopher who understood that situation best was a half-blind, chronically ill man who sold almost no books in his lifetime.

<!--more-->

---

### 1. Writing for Readers Who Do Not Exist Yet

Nietzsche published *Thus Spoke Zarathustra* with the subtitle *"A Book for All and None."* The fourth part was printed privately in about forty copies, and he could barely find people to send them to.

Compare that with my own numbers from last week: a few hundred visits, almost all of them from emails I sent by hand, and a single visitor from a search engine. It is tempting to read that as a verdict. Nietzsche suggests a different reading. In *Ecce Homo* he writes that some people are born posthumously — their work arrives before the readers who need it.

I am not claiming my Docker Compose file is *Zarathustra*. The point is more modest: **an empty dashboard measures timing, not value.** A tutorial about configuring OpenDKIM has the same worth on the day nobody reads it as on the day someone finally finds it at two in the morning, desperate, with every email landing in spam. Write for that person. They exist; they just have not arrived yet.

---

### 2. The Danger of the Herd Metric

There is a passage in *Daybreak* that I keep returning to, where Nietzsche warns against measuring ourselves by the approval of those around us — the morality of custom, he calls it, the instinct to do what the group rewards.

Modern software has its own morality of custom. It is called metrics. Stars on GitHub. Upvotes. Impressions. Monthly recurring revenue screenshots on X. None of these are bad in themselves, but when they become the *reason* to build, something hollows out. You start choosing projects because they would look good in a launch thread, not because they solve a problem you actually have.

Enkihost started because I wanted a place to host my own Jekyll sites without friction. Enkimail started because I needed to send email without handing my contact list to a third party. Those reasons are still true, whether or not anyone signs up tomorrow. That is the ground I want to stand on — not the dashboard.

---

### 3. "He Who Has a Why..."

The most quoted line from *Twilight of the Idols* is almost a cliché by now:

> "If we have our own *why* of life, we shall get along with almost any *how*."

For an indie developer, the *how* is brutal. Debugging a mail server at midnight. Rewriting the landing page for the fifth time. Getting your post removed by a Reddit bot for self-promotion. Explaining to friends what exactly you do all day.

Without a *why*, each of those moments is a small humiliation. With one, they become part of the work. My *why* is not "get users" — that is a *how*, a means. My *why* is closer to this: build tools that are simple, transparent, and sovereign, and learn as much as possible about every layer of the stack while doing it. By that measure, the last six months have been a success, even if the user count says otherwise.

---

### 4. Amor Fati and the Silent Launch Day

In *The Gay Science* (aphorism 276), Nietzsche writes his New Year's resolution:

> "I want to learn more and more to see as beautiful what is necessary in things; then I shall be one of those who make things beautiful. *Amor fati*: let that be my love henceforth!"

*Amor fati* — love of fate — is not passive acceptance. It is not "oh well, nobody came." It is the stronger claim that the silence itself is necessary, and can be loved.

What would that look like in practice? Something like this: the quiet launch gave me time to harden the infrastructure before real load arrived. The failed social media posts taught me which channels are worth my energy. The awkward experiment of emailing personal contacts forced me to think seriously about consent and unsubscribe links — which is exactly the kind of thinking an email service should be built on. None of that would have happened with an instant viral hit.

I do not always manage to feel this. Some mornings the dashboard just hurts. But *amor fati* is a practice, not a mood, and practices are built by repetition — like code.

---

### 5. Solitude Is a Tool, Not a Sentence

Living in Helsinki, solitude is not an abstract idea. In a few weeks the days will shrink to a few grey hours, and much of life will move indoors. I wrote earlier this year about how that silence can feel both heavy and clarifying.

Nietzsche needed distance to think — Sils-Maria, Genoa, long walks alone in the mountains. He did not see that distance as a failure to belong, but as a condition for seeing clearly. The indie developer has a similar relationship to solitude. Working alone means no one to blame, no one to share the 3 a.m. win with, no one to say "this is good enough, ship it." But it also means no committee, no roadmap you did not choose, no meetings about meetings.

The trick is not to escape solitude, but to use it deliberately — and then, at the right moment, to come down from the mountain. Zarathustra spends ten years alone before he decides he must go back among people and share what he has gathered. The solitude was never meant to be permanent; it was preparation.

For me, that means accepting that the next phase is not more code. It is conversation: writing to communities where the work is useful, answering questions, building a real opt-in list instead of shouting into feeds.

---

### 6. Become Who You Are

The phrase that runs underneath all of Nietzsche's work — borrowed from Pindar — is *"become who you are."* It is not about discovering some hidden true self. It is about shaping yourself through what you choose to do, again and again, until the choices become a character.

Every small project I ship — a mail queue, a hosting panel, a procedurally generated catacomb — is one of those choices. Individually, they look scattered. Together, they draw the outline of a person who builds, who wants to understand how things work all the way down, and who would rather own a small, honest tool than rent a large, opaque one.

That outline is the real product. The users, I hope, will come. But the becoming is already happening.

---

### Closing Thought

If you are building something alone right now — a side project, a small SaaS, a game nobody has played yet — I would offer one question in place of "how many users do I have?":

*If you knew for certain that this would never go viral, would you still want to have built it?*

If the answer is yes, you already have your *why*. The *how* will follow.

*What keeps you building when nobody seems to be watching? I'd genuinely like to know.*
