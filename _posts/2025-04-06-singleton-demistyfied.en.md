---
layout: post
title: "Singleton in Python: Global Villain or Local Hero?"
date: 2025-04-07 10:00:00 +0200
last_modified_at: 2025-04-07 10:00:00 +0200
categories: [QA, Python, Design Patterns]
tags: [singleton, design pattern, python, software design]
lang: en
---

> _"Singleton is evil!"_ – someone on the internet, probably.  
> _"Yet here we are."_ – you, trying to manage shared state like an adult.

Let’s talk about the most hated design pattern that keeps creeping back like that one flaky test you swore you fixed: **Singleton**.

---

## ☠️ The Pattern Everyone Loves to Hate

Singleton ensures a class has **only one instance**, and provides a global point of access to it.  
Sounds useful, right? Then why all the shade?

Critics will tell you it’s an **anti-pattern**, that it introduces **global state**, **tight coupling**, and will cause your CI pipelines to spontaneously combust.

And yet… it works. It solves problems. Especially in QA code.

Let’s expose the hypocrisy.

---

## 🔍 When Singleton Actually Makes Sense

You’re writing test automation. You’ve got a **reporter** class that needs to:

- create an HTML doc once,
- append logs from all over the test universe,
- wrap things up neatly at the end.

What are your options?

- Instantiating a new reporter in each test?  
  _Gross. Repetitive. Error-prone._

- Making it a global variable?  
  _Welcome to spaghetti._

- **Singleton**?  
  _Elegant. Focused. Controlled._

Here’s a lazy-loaded Singleton in Python. Because if you're gonna do it, do it right:

```python
class SingletonLazy:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

class Reporter(SingletonLazy):
    def __init__(self):
        self.log = []

    def add_log(self, message):
        self.log.append(message)
```

Used like this:

```python
r1 = Reporter()
r2 = Reporter()

print(r1 is r2)  # True
```

One instance. Controlled access. Clean.

---

## 🤬 But What About Global State?!

Oh no, your test framework has a shared object.  
So does your **config loader**, **database connection**, and **browser instance**. You already live in Singleton world – might as well do it intentionally.

The trick is **discipline**. Keep Singleton logic isolated. Don’t mutate state recklessly. Use it where **single ownership makes architectural sense**.

---

## 📊 Real Use Cases in QA Land

- 📁 **ConfigManager** – you don’t want fifty different configs flying around.
- 🧪 **Reporter/Logger** – centralized output, not chaos.
- 🔌 **Database session/connection pool** – reuse, not recreate.

You’re not building a 10,000-dev microservices org. You’re writing efficient, scoped, automation tools.

---

## 💡 TL;DR

- Singleton ≠ evil. Abused Singleton = evil.
- Use it when **single point of control** makes architectural sense.
- Be explicit, be clean, be in control.

---

## 👋 Parting Shots

The Singleton pattern is like a chainsaw. Dangerous in untrained hands. But in the right context, it clears the way fast.

So don’t apologize for using it. Own it. Just don’t use it as your default hammer.

Let the rest scream "anti-pattern" while you ship clean, maintainable code that actually works.

*Happy testing – and may your logs be ever appended.* 🧪

