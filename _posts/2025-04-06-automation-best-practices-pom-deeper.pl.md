---
layout: post
title: "Refaktoryzacja testów Selenium: Od chaosu do Page Object Model"
date: 2025-04-06
lang: pl
categories: [QA, Test Automation, Python]
tags: [selenium, pytest, POM, page object model, clean code]
---

> Przestań się powtarzać. Twoje testy zasługują na więcej.

## Przed: Klasyczny chaos testów

Przyznajmy szczerze. Każdy z nas kiedyś napisał coś takiego:

```python
def test_login():
    driver = webdriver.Chrome()
    driver.get("https://example.com/login")

    username = driver.find_element(By.ID, "username")
    password = driver.find_element(By.ID, "password")
    login_btn = driver.find_element(By.ID, "submit")

    username.send_keys("admin")
    password.send_keys("secret")
    login_btn.click()

    assert "Dashboard" in driver.title
    driver.quit()
```

Selektory na twardo, duplikacja, zero reużywalności. Działa, dopóki nie musisz tego zmienić. Albo przetestować drugi raz.

## Po: Page Object Model (POM) w akcji

Sprzątamy kod.

```python
# pages/login_page.py
class LoginPage:
    def __init__(self, driver):
        self.driver = driver

    def load(self):
        self.driver.get("https://example.com/login")

    def login(self, user, pwd):
        self.driver.find_element(By.ID, "username").send_keys(user)
        self.driver.find_element(By.ID, "password").send_keys(pwd)
        self.driver.find_element(By.ID, "submit").click()
```

```python
# tests/test_login.py
def test_login(driver):
    login = LoginPage(driver)
    login.load()
    login.login("admin", "secret")
    assert "Dashboard" in driver.title
```

Czyściej. Reużywalnie. Do utrzymania bez płaczu.

---

## Jeszcze lepiej: BasePage

Dajmy temu jeszcze trochę DRY i będzie git.

```python
# pages/base_page.py
class BasePage:
    def __init__(self, driver):
        self.driver = driver

    def find(self, by, value):
        return self.driver.find_element(by, value)

    def visit(self, url):
        self.driver.get(url)
```

```python
# pages/login_page.py
class LoginPage(BasePage):
    def load(self):
        self.visit("https://example.com/login")

    def login(self, user, pwd):
        self.find(By.ID, "username").send_keys(user)
        self.find(By.ID, "password").send_keys(pwd)
        self.find(By.ID, "submit").click()
```

Mniej duplikacji, więcej kontroli. Idealne miejsce na timeouty, logi, screenshoty.

---

## Na koniec

POM to nie tylko ładny kod – to twoje ubezpieczenie na przyszłość.  
Zacznij od małych kroków. Refaktoruj, kiedy zaczyna boleć. A jak boli za bardzo – dodaj `BasePage`.

Bądź sprytny. Testuj sprytniej.  
– Karol
