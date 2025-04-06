---
layout: post
title: "Szybki start z Selenium: Twój pierwszy test automatyczny"
date: 2025-04-06
categories: [QA, Automatyzacja, Selenium]
tags: [selenium, pytest, webdriver, automatyzacja, quickstart]
lang: pl
---

> _"Nie czytaj o testowaniu. **Testuj**."_  
> Lecimy z konkretem – pierwszy test w Selenium z Pythonem i Pytestem w parę minut.

## 🚀 TL;DR

- Pobierz ChromeDriver  
- Skonfiguruj WebDriver options  
- Napisz test w Pytest  
- ✅ Profit

```bash
pip install selenium pytest
```

## 📦 Setup

```python
from selenium import webdriver
import pytest

@pytest.fixture
def driver():
    options = webdriver.ChromeOptions()
    options.add_argument('--headless')  # tryb bez GUI
    driver = webdriver.Chrome(options=options)
    yield driver
    driver.quit()
```

## 🧪 Pierwszy test

```python
def test_page_load_and_title(driver):
    driver.get("https://www.example.com")
    assert "Example Domain" in driver.title
```

## 💡 Na co uważać?

- **Nie zapomnij o `yield`** – bez tego narobisz sobie zombie-chromów w tle.
- `--headless` = twój przyjaciel na CI/CD.
- Selenium to prawdziwa przeglądarka → nie pchaj tam wszystkiego. Tylko to, co trzeba.

## 🔍 Chcesz więcej?

Zajrzyj głębiej, jeśli czujesz głód wiedzy:

- 🧠 [Pytest Fixtures – o co chodzi?](/pytest-fixture-deep-dive)
- 🧰 [Opcje WebDrivera – headless, sandbox i spółka](/selenium-options-headless)
- 🧼 [Selenium Best Practices dla QA](/selenium-best-practices)

---

Bądź sprytny. Testuj sprytniej. 🔪

