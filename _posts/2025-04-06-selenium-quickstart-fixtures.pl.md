---
title: "Fixtury Pytest: Setup bez bólu"
date: 2025-04-06
lang: pl
layout: post
categories: [QA, Automatyzacja Testów]
tags: [Pytest, Fixtures, Selenium, Automatyzacja, QA]
---

Masz już opanowanego `webdrivera`? Super.  
Ale co dalej?  
Nie chcesz przecież **pisać tego samego setupu i cleanupu** w każdej funkcji testowej, prawda?

I tu wchodzą **fixtury w Pytest** – całe na biało.

---

## Czym jest fixtura?

Fixtura to taki pomocnik testowy.  
Zrobi setup, poda ci drivera jak kawę do łóżka, a po teście wszystko posprząta.

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

## Dlaczego warto?

- 🧽 **Koniec duplikacji** – setup piszesz raz, używasz wielokrotnie.
- ⚰️ **Brak trupów w tle** – nie zostawiasz sterty otwartych przeglądarek.
- 📦 **Scope jak chcesz** – per test, per klasa, globalnie – masz wybór.

---

## Przykład testu z życia

```python
def test_page_load(driver):
    driver.get("https://example.com")
    assert "Example" in driver.title
```

Bez boilerplate’u. Bez syfu. Czysty test.

---

## Można ambitniej?

- `scope='session'` – jeden driver do wielu testów.
- Parametryzacja fixture dla różnych środowisk/przeglądarek.
- Łączenie fixture jak perki w skill-tree – serio, można.

---

## TL;DR

Nie klep setupu jak w 2009.  
Użyj fixtur.  
Zachowaj porządek w kodzie.  
Zachowaj zdrowie psychiczne.

W następnym wpisie: **dobre praktyki testów** – czyli jak nie pisać potworków.

Zostań z nami.

