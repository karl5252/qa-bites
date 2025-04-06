---
title: "Dobre praktyki w automatyzacji testów: Bez chaosu i bez wstydu"
date: 2025-04-06
lang: pl
layout: post
categories: [QA, Automatyzacja Testów]
tags: [best practices, QA, Pytest, Selenium, clean code]
---

Chcesz pisać testy, które nie wyglądają jak spaghetti z GPIO?  
Dobrze trafiłeś.

Oto zestaw **drapieżnych zasad**, które pomogą Ci ogarnąć testowy bałagan i wejść na wyższy level automatyzacji.

---

## 🎯 1. Jeden test = jeden cel

Nie rób z testu **kuchni fusion**. Test ma sprawdzać **jedną rzecz**.

Źle:
```python
def test_login_and_change_password_and_logout():
    ...
```

Dobrze:
```python
def test_login_successful():
    ...

def test_password_change():
    ...
```

---

## 🔍 2. Nazwy testów mówiące jak error 404

Jeśli twoje testy mają nazwy typu `test_1`, `test_final_final_v2`, to lepiej już przestań.  

Testy to kod. Nazwa to kontrakt.  
**`test_login_fails_with_invalid_credentials`**?  
Tak. Mów do mnie jeszcze.

---

## 🧪 3. Setup i teardown? Fixtury, ziomek.

Nie kopiuj setupu do każdego testu jakbyś miał CTRL+C w makrze.  
Fixtury (`@pytest.fixture`) są po to, żeby Cię z tego ratować.

---

## 🪓 4. Unikaj hardcodów jak ognia

Jeśli coś zmieniasz w trzech miejscach, to masz **problem z reużywalnością**.  
Parametry, pliki konfiguracyjne, dane z zewnątrz. To Twoi sprzymierzeńcy.

---

## 🧱 5. Oddziel testy od asercji

Nie mieszaj setupu, akcji i weryfikacji w jednym wielkim sosie.  
Stosuj zasadę **Arrange – Act – Assert**.

```python
# Arrange
driver.get("https://example.com")

# Act
login(driver, "user", "pass")

# Assert
assert "Welcome" in driver.page_source
```

---

## 🧼 6. Sprzątaj po sobie (driver.quit)

Zostawianie sterty otwartych instancji przeglądarki to **grzech śmiertelny**.  
Sprzątaj. Fixture z `yield` załatwia temat.

---

## 🛠️ 7. Używaj retry / waitów z głową

Nie śpij `time.sleep(5)` – to nie ZUS.  
Używaj **WebDriverWait** i retry logic.  
Twoje testy będą działać szybciej i stabilniej.

---

## 🧙‍♂️ 8. Nie pisz testów jakbyś był jedyny na świecie

Twój kod będą czytać inni.  
Albo Ty po pół roku.  
Pisz tak, żeby dało się to utrzymać.  
Komentarz raz na jakiś czas? Nie zabije.

---

## 🐍 9. Trzymaj się konwencji

`test_`, `assert`, `fixtures`, `naming` – trzymaj się zasad frameworka.  
To nie freestyle – to projekt.

---

## 🧩 10. Pisz testy, które mają sens

Nie testuj przycisku "OK" tylko dlatego, że jest.  
Zadaj sobie pytanie: **"co mi ten test daje?"**  
Jeśli odpowiedź brzmi "meh" – wywal.

---

## TL;DR

✅ Jeden test = jeden cel  
✅ Nazwy mają mówić  
✅ Setup w fixturze  
✅ Zero hardcodów  
✅ Kod testowy = czytelny kod

Nie pisz testów, których sam byś nie chciał debugować.

W następnym wpisie: **Page Object Model** bez nudy, czyli jak nie zrobić z niego potworka z dwoma głowami.

Zostań z nami, testuj mądrze 🔥

