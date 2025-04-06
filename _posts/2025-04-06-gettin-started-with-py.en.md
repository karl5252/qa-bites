---
layout: post
title: 🚀Getting Started with Python- Why QA Devs Should Care 
date: 2023-06-04 10:00:00 +0200
categories: [QA, Automatyzacja]
tags: [framework, testy]
lang: en
---
Let’s skip the poetry and get to the point about Python.

Python = fast, readable, powerful.  
You = QA trying to automate without losing your mind.  
This post = your cheat code.  

---

### 🧠 Why Python Slaps

- 🐍 Clean syntax = fewer WTFs per minute  
- 🧰 Libraries galore: Selenium, Playwright, requests, etc.  
- 🔌 Perfect for glueing together weird, multilingual Frankenstein apps  
- 💻 From scripting to full-blown backend – it scales

> You don’t need to be a dev ninja. Just sharp enough to cut through flaky UI tests.

---

### ⚔️ Test Framework Deathmatch

#### 🧱 `unittest` – The Old Guard  
- Comes built-in  
- Class-based, verbose, but reliable  
- Great if you like structure and discipline  
📎 [Docs](https://docs.python.org/3/library/unittest.html)

#### 🪦 `nose` – The Ghost of QA Past  
- Was cool. Isn’t anymore.  
- Still breathing, but don’t build your future on it  
📎 [Docs](https://nose.readthedocs.io/)

#### 🔥 `pytest` – The Fan Favorite  
- Minimalist. Modular. Mighty.  
- Fixtures, plugins, parameterization – you name it  
- Reads like plain English  
📎 [Docs](https://docs.pytest.org/)

---

### 🧪 Your First Python Test Tool: The "Averageinator"

```python
numbers = list(map(int, input("Enter numbers: ").split()))
print(sum(numbers) / len(numbers))
```

> Don’t be a script kiddie – type it out. Break it. Fix it. Learn it.  

---

### 🧾 TL;DR

- 🐍 Python = QA's gateway drug to automation  
- 🛠️ Choose `pytest` unless you like pain  
- 💡 Start small, iterate fast  
- 💬 Comment your war stories below

Next time: How to write `pytest` tests that don’t suck.

---
