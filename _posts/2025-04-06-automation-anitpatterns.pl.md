---
title: "Antywzorce w automatyzacji testów- Czyli czego nie robić i jak to naprawić"
date: 2025-04-07
lang: pl
layout: post
categories: [QA, Automation, Best Practices]
tags: [testing, antipatterns, automation, pytest, qa]
---

> _Testy automatyczne są jak lasagne: świetne, gdy świeże, śmierdzące, gdy zaniedbane._

W świecie testów automatycznych istnieją rzeczy, o których się nie mówi. Brudne sekrety. Dziwne struktury folderów. Skrypty pisane po pijaku. I dziś się z nimi rozprawimy.

Czas przyjrzeć się **antywzorcom w testach automatycznych** – czyli temu, co robimy źle (często nieświadomie), a co sprawia, że nasze frameworki przypominają spaghetti kod zamiast eleganckiego lasagne z testami na każdej warstwie.

---

## 🧟‍♂️ Potworny przykład z życia wzięty

```text
qa_tests/
├── tests/
│   ├── TestClass1.py
│   ├── BashTests.py
│   ├── ApiTestClass2.py
│   └── ConfigReader.py
├── resources/
│   └── test_data.json
```

Pierwsze objawy choroby:

- **Zero modularności**: kod testów, helperów i konfiguracji zmiksowany w jednym folderze.
- **Brak konwencji**: pliki nazwane „na pałę” – próbujesz znaleźć test klasy 2? Powodzenia.
- **Brak separacji odpowiedzialności**: testy, logika, i dane wszystko w jednym pliku – jak barszcz, tylko bez smaku.

---

## 🔍 Diagnoza: Najczęstsze antywzorce

### 🔥 Wszystko w jednym worku
Logika, testy, setup, dane testowe – jedno wielkie miszmasz. 

➡️ **Zrób tak**: Rozdziel testy (`/tests`), page objecty (`/pages`), dane (`/resources`) i helpery (`/utils`).

### 🎭 Udawanie Page Object Model
Masz klasę z 200 metodami do kliknięcia wszystkiego na stronie? To nie jest POM. To horror klasy B.

➡️ **Zrób tak**: Dziel według widoków i odpowiedzialności. Każda strona = osobna klasa.

### 🤕 Testy klecone na pałę
Nazwy typu `test_1`, `test_final_fixed_final2`, `try_this_one` – serio?

➡️ **Zrób tak**: Test ma mówić co sprawdza: `test_user_login_with_valid_credentials` – prosto i zrozumiale.

### 📦 Dane testowe hardcodowane w kodzie
Serio? `username = "admin"` w środku testu?

➡️ **Zrób tak**: Używaj plików `.json`, `.yaml`, lub fixture'ów do generowania danych.

### 😴 Brak raportowania
Brak wyników testów? Albo co gorsza – printy w konsoli?

➡️ **Zrób tak**: Wygeneruj HTML report. Albo jeszcze lepiej – zintegruj z TestRail/JIRA i bądź królem CI.

---

## 🛠 Jak to posprzątać?

Oto proponowana struktura:

```text
root/
├── Config/
├── Pages/
├── Results/
├── Model/
├── Utils/
├── tests/
│   ├── api/
│   ├── web/
│   └── conftest.py
```

### 📐 Dodaj BaseTest
Każda klasa testowa dziedziczy po `BaseTestClass`, który ogarnia setup/teardown. Nie duplikuj kodu – nie jesteśmy w latach 90.

### 🧪 Fixture’y, nie magia
Zamiast tworzyć WebDriver w każdym teście – użyj fixture’a. `conftest.py` to twoje centrum dowodzenia.

### 📊 Raportuj jak człowiek
Podłącz `pytest-html` albo `Allure`. Zrób z testów coś, co można pokazać PMowi bez tłumaczenia „co autor miał na myśli”.

### 🔁 Automatyzacja = ewolucja
Framework testowy to organizm. Refaktoruj. Rób code review. Mierz coverage. I co jakiś czas – wróć do tego posta ;)

---

## 🧠 TL;DR – Antywzorce vs dobre praktyki

| Antywzorzec                       | Co robić zamiast                   |
|----------------------------------|------------------------------------|
| Wszystko w jednym folderze       | Rozdziel strukturę projektu        |
| Brak POM                         | Dziel Page Objecty per widok       |
| Hardcodowane dane                | Externalizacja danych testowych    |
| Brak raportów                    | pytest-html, Allure, TestRail      |
| Brak modularności                | BaseTest, fixture’y, utils         |

---

**Testy nie muszą być piekłem.**

Ale muszą być pisane z głową.

Nie pozwól, żeby twój framework wyglądał jak Frankenstein po refaktorze w Notatniku.

Bo debugowanie w piekle to nie jest coś, co chcesz przeżyć.

---

_Pisz dobrze. Refaktoruj często. Testuj z dumą._
