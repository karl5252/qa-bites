---
title: "Scope Creep: When Something Small Becomes a QA Nightmare"
date: 2025-04-08
lang: en
layout: post
categories: [QA, Automation]
tags: [qaRealTalk, scopeCreep, ticketMutation, testingWilderness, qaTherapy]
---

## This Tuesday started like a Monday.

Or, as Peter Steele would sing:

> _“I don’t wanna be me.”_

Gym pass didn’t work. Leasing guy gaslit me with contract dates.  
QA?  
**QA gets a last-minute handoff at the end of the sprint with a cheerful “will you manage?”**  
And that’s not a question – that’s a stress test. 🔥

## And then, the ticket shows up.

> _“We just need a thousands separator.”_  
Said someone, not realizing how _not just_ that was.

Turns out – the separator shows up **only on the banner**. Everything else?

> _“Not in scope.”  
“We just decided it’ll be banner-only.”  
“We’ll add the rest later.”  
“That’ll be in a different ticket.”_ 🔥

## What does the ticket even look like?

Two blurry screenshots and poetic license.  
It reads like a haiku written at 1am — drunk and half-blind. And any actual requirements – if they exist – are buried somewhere in a 128-message-long dev chat thread.  
If you weren’t online for that thread live, good luck guessing what was _really_ agreed on. 🔥

## Meanwhile, there’s a Big QA Milestone happening.

Not a release milestone – a **"Let’s Get Serious About Quality™"** kind of milestone:

> _90% E2E test coverage,  
test docs written **before** merging,  
QA linters,  
and CI pipelines triggering our tests in every dev repo like a holy sourdough starter._ 🔥

### It was supposed to be a breakthrough moment.

Testing, not as an afterthought, but as a condition for existence.

And I – the last QA heretic – quietly suggest:

> _“Smoke, sanity, ROI. Automate what breaks the most.  
E2E only where it’s critical.”_ 🔥

And then it hits me.

- We have a backend – that changes every sprint.  
- A CMS – maintained by a different team.  
- A user-service – separate backend, separate team.  
- And it all ties together... on the frontend.

The system is distributed, mutating, and alive.  
And we’re aiming for **90% E2E coverage** on a thing that’s half unknown and half unreachable.

**QA in 2025: trying to ensure quality in a system that speaks through headsets, but no one’s listening.** 🔥

## And when QA dares mention sanity tests, smoke, or ROI?

> _“Let’s just focus on coverage and regression trends...”_

The QA team ramps up – **because business wants metrics**.  
So there will be metrics. There will be dashboards. There will be charts.  
A bit forced, if you ask me.  
Kind of just to keep business happy. 🔥

And me?  
I just want to do it right.  
Not spend months fixing flaky E2E.  
Not write a test that dies before the ticket does.  
**Just build tests that make sense.**

But the only response I get is a few sighs and eventually the classic:

> _“We’ll just do it our way.”_ 🔥

---

## All of this wrapped in a beautifully empty buzzword:

**“Interdisciplinary team.”**

In reality?  
Four teams. Four priorities. Four sprints. Zero shared direction.  
And QA is left to stitch it all together like Frankenstein – with a deadline. 🔥

## And honestly...

Are we talking about **application sanity** – or my own?

After a few sprints full of ticket mutations, 90% E2E targets, and reminders that smoke is “not a cigarette,” you start wondering who really needs a sanity check.

Spoiler: **QA. Always QA.**

---

## PS. QA Therapy – Tuesday Edition

You know what else?

I spent over an hour today comparing fonts, colors, spacing – element by element – to the Figma design.  
Because someone said, _“but it works.”_  
And I was the idiot who had to prove it doesn’t look like it’s supposed to.  
That’s not testing.  
**That’s UI babysitting.** 🔥

And to top it off – today I got bit in the ass by the “interdisciplinary” dream.

They got the info on Thursday.  
On Friday they replied:

> _“We’ll deliver it Monday.”_  
Monday... nothing.  
Tuesday?  
> _A whole lotta nothing. Just a bannerless void._ 🔥

No data. No way to test.  
And there I was, test in hand, waiting for something that _should have been ready days ago_.

“Interdisciplinary”?  
More like **intervention-needed QA**.  
Because once again, I’m the one patching what no one delivered. 🔥

---

**And that’s why this post had to be written.**  
**Not as a manifesto. Not as a complaint.**  
**But as a QA battle journal – for everyone who says “sanity” and hears only silence in return.** 🔥
