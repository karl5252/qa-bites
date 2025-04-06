---
layout: post
title: "Selenium Quickstart: Your First Automated Web Test"
date: 2025-04-06
categories: [QA, Automation, Selenium]
tags: [selenium, pytest, webdriver, automation, quickstart]
lang: en
---

> _"Don't read about testing. **Do** the testing."_  
> Here’s your fast-track to firing your first Selenium test with Python & Pytest.

## 🚀 TL;DR

- Setup ChromeDriver  
- Add some WebDriver options  
- Write a Pytest test  
- ✅ Profit

```python
pip install selenium pytest
```

## 📦 Setup

```python
from selenium import webdriver
import pytest

@pytest.fixture
def driver():
    options = webdriver.ChromeOptions()
    options.add_argument('--headless')
    driver = webdriver.Chrome(options=options)
    yield driver
    driver.quit()
```

## 🧪 First Test

```python
def test_page_load_and_title(driver):
    driver.get("https://www.example.com")
    assert "Example Domain" in driver.title
```

## 💡 Gotchas

- Always use `yield` in fixture, or you’ll get ghost browsers haunting your RAM.
- Use `--headless` for CI pipelines (no GUI).
- Selenium tests = real browser = real slow → use sparingly.

## 🔍 Want More?

Feeling curious or confused? Jump into the deep dives:

- 🧠 [Pytest Fixtures Demystified](/qa/test%20automation/selenium-quickstart-fixtures.en/)
- 🧰 [All About WebDriver Options](/qa/test%20automation/selenium-quickstart-options.en/)
- 🧼 [Selenium Best Practices 101](/selenium-best-practices)

---

Stay sharp, test sharper. 🔪
