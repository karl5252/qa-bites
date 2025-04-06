---
layout: post
title: "Refactoring Selenium Tests: From Chaos to Page Object Model"
date: 2025-04-06
lang: en
categories: [QA, Test Automation, Python]
tags: [selenium, pytest, POM, page object model, clean code]
---

> Stop repeating yourself. Your tests deserve better.

## Before: Classic Test Chaos

Let’s face it. We’ve all written tests like this:

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

Hardcoded selectors, duplication, zero reuse. Looks fine until you need to change something. Or reuse it. Or debug.

## After: Enter Page Object Model (POM)

Let’s clean it up.

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

Cleaner. Reusable. Maintainable. You want this.

---

## Level Up: BasePage Pattern

Let’s go DRYer. You’ll thank yourself later.

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

Even less repetition. One place to extend things like waits, logs, screenshots, etc.

---

## Final Words

Page Object Model isn’t just about clean code – it’s your future-proof insurance.  
Start small. Refactor when things hurt. And when they hurt a lot – reach for `BasePage`.

Stay sharp, test sharper.  
– Karol


