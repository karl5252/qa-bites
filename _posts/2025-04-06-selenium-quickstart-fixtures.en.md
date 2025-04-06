---
title: "Pytest Fixtures: Setup Without the Pain"
date: 2025-04-06
lang: en
layout: post
categories: [QA, Test Automation]
tags: [Pytest, Fixtures, Selenium, Automation, QA]
---

So you've got your `webdriver` setup down. Great.  
Now what? You want to **stop writing the same setup/teardown crap** in every test?

That’s where **Pytest fixtures** come in.

---

## What's a Fixture?

A fixture is your pre-test butler.  
It sets things up, hands the keys to your test, then quietly cleans up.

```python
import pytest
from selenium import webdriver

@pytest.fixture
def driver():
    options = webdriver.ChromeOptions()
    options.add_argument('--headless')
    driver = webdriver.Chrome(options=options)
    yield driver
    driver.quit()
```

---

## Why Use Fixtures?

- 💥 **No repetition** – one setup, reused across tests.
- 🧼 **Automatic cleanup** – no browser zombies.
- 🧪 **Customizable scopes** – per function, class, module, you name it.

---

## Real-Life Test

```python
def test_page_load(driver):
    driver.get("https://example.com")
    assert "Example" in driver.title
```

Simple, clean, effective. No boilerplate. Just test logic.

---

## Advanced Moves?

- Use `scope='session'` to share a browser across multiple tests.
- Parametrize fixtures for different environments or browsers.
- Chain fixtures together like a QA ninja stacking buffs.

---

## TL;DR

Stop copy-pasting your setup like it’s 2009.

Use fixtures.  
Keep your tests clean.  
Keep your sanity.

Next up: **Test code best practices** – where your `assert` gets some actual style.  
Stay tuned.

