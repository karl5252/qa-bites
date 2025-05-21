---
layout: post
title: "How (Not) to Build a QA POC in a Multi-Region Project"
date: 2025-05-23 05:00:00 +0200
categories: [QA]
tags: [poc, automation, testing, frustration]
lang: en
excerpt: Three QA engineers, three POCs, three visions of the world — all in one project with five regions. Here’s what happens when theory meets reality.
---

## 🧪 How (Not) to Build a QA POC in a Multi-Region Project

Imagine an e-commerce application being rolled out in over a dozen countries — each of them a separate **region**, with its own configuration, content, and expectations.  
In theory: one app, one codebase, global standardization.  
In practice? Local exceptions, regional features, and orders that *must work in Malaysia, but not in Nigeria.*

In such an environment, trying to build a shared automation framework — or even just a POC — can trigger a series of... fascinating collisions between hard reality and the PowerPoint version of QA. And that’s exactly what this post is about.

---

### 👨‍🔬 Three QA Engineers, Three POCs, Three Worlds

#### ✅ **POC #1: Works, scales, and understands the context (mine)**

- Supports multiple regions with dynamic user and outlet selection  
- Supports test tagging (`@country:ZA`, `@outlet:full`, `@authenticated`)  
- Separate logic layer for login, language switching, region, etc.  
- Based on **Playwright + TypeScript**, with fixture logic for easier test reuse  
- CI/CD ready — even if not fully integrated (yet)  
- Extensible: currently works on `TEST`, can add `ACC`, `PROD` via env-switch

Philosophy? Flexibility. Low entry barrier. Real-world scenarios, not theory.

---

#### 🧩 **POC #2: Tutorial-style patchwork (J’s version)**

- One region, one test, one type of user  
- No dynamic outlet, language, or region switching  
- Sample test with hardcoded data  
- Zero assertions (they kept failing)  
- `.env` file contains ACC and TEST tokens at the same time — what could possibly go wrong?

Does it work? Yes.  
Is it scalable? Not really.  
Is it still a POC, or already a *proof of conceptually skipping everything difficult*? — you decide.

---

#### 📊 **POC #3: The Ideal World on Paper (R’s roadmap)**

- Roadmap created in January  
- Code planned for "phase 4"  
- Components? “GraphQL connector”, “Virto CMS layer”, “PageUtils module”, “Unified test state handler”  
- Declared approach: full e2e testing, no Page Object Model (because *it’s 2025 now*)

There’s no code. No tests.  
But there is a linter, a prettier config, a package manager — and a meeting schedule.  
Sounds like Waterfall? You’re not alone.

---

### 🧱 And Then Comes That Sentence...

> “It can’t be that regions just choose their own features — we need to standardize this.”

Except... **that’s exactly how it is.** And how it will be.  
Because regions aren’t our hobby — they’re our clients.  
And if Zanzibar wants a pink font and a loyalty banner on Thursdays only, then we build it —  
not schedule a global BA alignment meeting.

Otherwise, QA isn’t product support — it’s just another blocker.

---

### 🧭 Takeaways

This post isn’t about who’s right.  
It’s about how QA without context is like a linter without code — **clean, but useless.**

When building a POC:

- 🧪 test what’s real (not what you *wish* was real)  
- 🌐 assume differences — don’t ignore them  
- 🤝 don’t fight regions — support them  
- 🛠️ don’t pick tools before you have a need (*do we really need a potato connector?*)

And finally:  
📝 If your POC has more documentation than tests — **stop writing. Start building.**

---

## 🔗 Repository (Code, Not Product)

You can check out the POC described in this post here:  
👉 [github.com/karl5252/demo-ecommerce-tests/tree/main](https://github.com/karl5252/demo-ecommerce-tests/tree/main)

It’s not a framework you can run *out of the box.*  
It’s not integrated with a real application —  
but it **is full of ideas, structure, and approaches** you can bring into your own project.

The code shows:

- how to handle multiple regions without rewriting every test,  
- how tagging and environment control work,  
- how to write tests that separate logic from implementation.

No roadmap. No theory. **Just code.**
