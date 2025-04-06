---
layout: post
title: "Page Object Model: Przepis na testy, które nie gryzą"
date: 2025-04-06 10:00:00 +0200
categories: [Test Automation, QA, POM]
tags: [pytest, selenium, page object model, automatyzacja, architektura]
lang: pl
---

> „Testy mają być czytelne jak przepis na makaron. A nie jak wykres zależności w mikroserwisach.”

## Dlaczego w ogóle POM?

Masz testy Selenium, które klikają, sprawdzają, wchodzą, wychodzą… ale coś zaczyna śmierdzieć. Zmiana jednego selektora rozwala pół projektu. Ktoś dodał nowe pole – i nagle 10 testów czerwone. Kod wygląda jak ctrl+c / ctrl+v po trzech kawach.

Rozwiązanie? **Page Object Model (POM)** – wzorzec, który oddziela logikę testową od implementacji UI. Brzmi poważnie, działa prosto.

## Jak działa?

Zamiast pisać test, który bezpośrednio grzebie w elementach strony, tworzysz klasę – **obiekt strony**, który wie, jak się z tą stroną obchodzić:

```python
class LoginPage:
    def __init__(self, driver):
        self.driver = driver
        self.username_field = driver.find_element(By.ID, "username")
        self.password_field = driver.find_element(By.ID, "password")
        self.login_button = driver.find_element(By.ID, "login")

    def login(self, username, password):
        self.username_field.send_keys(username)
        self.password_field.send_keys(password)
        self.login_button.click()
```

I teraz w teście:

```python
def test_valid_login(driver):
    login_page = LoginPage(driver)
    login_page.login("admin", "admin123")
    assert "dashboard" in driver.current_url
```

## Zalety? Oto one:

- 🔄 **Reużywalność** – nie duplikujesz kodu w 10 testach.
- 🔧 **Łatwe utrzymanie** – zmieniasz selektor raz.
- 🧠 **Czytelność** – test opisuje _co_ się dzieje, nie _jak_.

## Gdzie trzymać POM?

- Osobny folder: `pages/`
- Jedna klasa = jedna strona lub komponent
- Używaj inicjalizacji drivera i trzymających się siebie metod (np. `fill_form()`, `submit()`, `get_error_message()`)

## Czego unikać?

- ❌ Przerzucania całej logiki testu do PageObject – to ma być API do strony, nie mini-test-runner.
- ❌ Przekombinowania z dziedziczeniem – keep it simple.
- ❌ „PageGodObjects” – jeśli strona robi wszystko, podziel ją.

## TL;DR

**Page Object Model** to jak kuchenny organizer – wszystko na miejscu, wiesz gdzie szukać, nic się nie wylewa.

Zamiast pisać test jak partyzant w dżungli DOM-u, robisz to jak strateg: budujesz warstwę abstrakcji i idziesz jak po sznurku.

---

W kolejnych postach: struktura projektu testowego z POM, refaktor klasycznego testu w Pytest, a także integracja z fixture’ami i CI/CD.

Testuj z głową.  
I pamiętaj – czysty kod to szczęśliwy QA. 🧼

– Karol


