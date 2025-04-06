---
title: "Pierwsze kroki z Selenium: Opcje WebDrivera pod lupą"
date: 2025-04-06
lang: pl
layout: post
categories: [QA, Test Automation]
tags: [Selenium, WebDriver, Headless, ChromeOptions, QA]
---

Witaj w świecie testów automatycznych. Masz już dość klikania w te same guziki? Dobrze trafiłeś. Zaczniemy od podstaw, ale z pazurem – bez lukru i zbędnych wstępów.

## Po co te całe „opcje”?

Selenium pozwala automatyzować przeglądarki. Ale zanim browser w ogóle się podniesie – możemy rzucić mu kilka argumentów. Dosłownie.

```python
options = webdriver.ChromeOptions()
options.add_argument('--headless')
driver = webdriver.Chrome(options=options)
```

To jak pierwsza kawa dla Twojej przeglądarki – decydujesz, w jakim nastroju ma wstać.

---

## Przegląd opcji – po co i kiedy?

- `--headless`: Bez GUI. Brak okienka, maksymalna wydajność. Idealne na CI/CD.
- `--disable-gpu`: Nie baw się z akceleracją – oszczędzisz problemy.
- `--window-size=1920,1080`: Kontroluj rozmiar – przydatne przy testach responsywności.
- `--no-sandbox`: Czasem potrzebne w kontenerach, ale z głową.
- `--disable-dev-shm-usage`: Gdy `/dev/shm` się zapycha – na Dockerze jak znalazł.
- `--ignore-certificate-errors`: SSL leży? A test musi przejść. Uważaj w produkcji.
- `--disable-extensions`: Żegnajcie, adblocki i inne dziwactwa.

---

## Czy potrzebujesz wszystkich?

Nie. Używaj tylko tego, co Ci realnie potrzebne. Nadmiar opcji to jak nadmiar przypraw – nie wszystko razem smakuje lepiej.

---

## TL;DR

- `--headless`: domyślny wybór dla CI.
- `--window-size`: konieczność przy testach layoutów.
- `--no-sandbox`, `--disable-dev-shm-usage`: must-have w Dockerze.

---

W kolejnej części pogadamy o **fixture'ach w Pyteście** – czyli jak nie powtarzać tego samego setupu w kółko.

Do przeczytania. 🚀

