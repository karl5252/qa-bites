---
layout: post
title: "Taming Gidorah: Real-life AQA Survival Guide"
date: 2025-04-07
lang: en
categories: [QA, Test Automation, Real Talk]
tags: [automation, selenium, api, real device, test strategy, mocks, flakiness]
---

> “One does not simply automate everything.”
> – QA proverb

Let’s be honest for a second.  
Test automation, especially in environments that involve **Web UI + API + Real Devices + Desktop UI**, is **less like building a Swiss watch** and **more like taming a three-headed kaiju.**  
Meet **Gidorah**.

---

## 🐉 Three heads, one nightmare

Imagine a project where your system consists of:
- A **web app** (App A),
- A **desktop app** using Qt WebView (App B),
- A **physical device** (codename: **CHUCKY**),
- And one shared **API** sitting in the middle like a fragile spinal cord.

Every change in App A is supposed to reflect on CHUCKY.  
Every param you poke through the web UI needs to be confirmed via the API.  
And sometimes… some brave soul tests it via App B.

---

## 💣 Real Talk from the Trenches

### The test flow looked like this:

1. **Login and preconditions.**
2. **Set parameters on CHUCKY** via Web UI – min, max, random, delays. Try to break it just enough.
3. **Fire GET via API** to confirm the device accepted it.
4. **Watch the UI**. Pray the slider doesn't dance back to 0 because CHUCKY lagged out.

### And what could possibly go wrong?

- CHUCKY **drops network mid-test**. Like a ghost.
- CHUCKY **gets evicted from the registry**. No reason. Just vibes.
- Sometimes, setting params too fast makes CHUCKY go BRRR... or crash completely.
- CHUCKY has **siblings** – *Anabelle*, *M3GAN* – same hardware, different quirks.
- Someone just **borrows CHUCKY**. "Oh, I thought nobody was using it."
- The API returns OK, but the UI **randomly resets** your settings after 5 seconds.
- **You can't automate the desktop app**, because it's Qt WebView and behaves like a gremlin with a hangover.

---

## 🧠 Can’t you just... mock it?

Sure. You can:
- Mock the **API** to isolate UI tests.
- Mock the **device** via a Dockerized emulator.
- Mock the **frontend** when testing backend behavior.

But here's the catch: **the only thing worse than flaky tests is false confidence**.

In regulated systems or critical hardware (read: the kind that talks to CHUCKY), **only E2E gives you sleep at night**. Because manually testing 200+ parameters is a one-way ticket to burnout.

---

## 🪛 The "conftest.py" problem

Your test suite has both API and UI tests.

Now you:
- Want to take screenshots on test failure.
- But `driver.take_screenshot()` breaks for API-only tests.
- So you add `try-except` to everything.
- And now your **global `conftest.py` looks like a spaghetti junction**.

You could split them into:
1. `conftest_api.py`
2. `conftest_ui.py`
3. Global config

But guess what? **Pytest doesn’t support that out of the box.**  
So now your fixtures are more bloated than your backlog.

---

## 🚨 Pressure from all sides

Business:  
> “Let’s automate all the manual test cases!”

PM:  
> “QA team, can you confirm that *everything* is covered?”

QA Manager:  
> “Hey Karol, can you automate the unautomatable?”

Me:  
> **“honk-honk 🥲”** *(starts writing new fixture)*

---

## 🧪 What worked (sometimes)

- Creating **dynamic test param maps** instead of hardcoded values.
- Using **Docker-based emulators** to test devices without ruining your day.
- Keeping Web UI + API tests **separate but strategically coordinated**.
- Always assuming **someone will unplug CHUCKY mid-test**.
- Writing logs like a detective novel. You’ll thank yourself at 2AM.

---

## 🔥 AQA = Human Firewall

The truth? Automation isn’t magic.  
It’s **a highly-trained duck** paddling like hell under the surface.

And as AQA, you’re:
- Blamed for flaky tests,
- Asked to fix bad architecture,
- Expected to deliver 100% coverage **yesterday**,
- And still **smile in sprint review** like it's all sunshine.

We live in a world where tests fail not because the app is broken…  
but because CHUCKY **blinked**.

---

## Final thought

Don’t trust clean test pyramids on slides.  
**Real testing is messy. Chaotic. Painful.**  
But also kind of beautiful in its absurdity.

So next time your test fails,  
and someone asks, “Can’t you just fix it?”  
just whisper:

> “You can’t tame Gidorah. You can only prepare.”

🐉🔥🧪

---

Stay strong, fellow testers.  
And remember:  
**Mocks are friends. Logs are therapy. Docker is salvation.**
