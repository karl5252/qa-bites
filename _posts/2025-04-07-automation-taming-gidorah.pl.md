---
layout: post
title: "Jak okiełznać Gidorahę: AQA w realu, czyli krwawy przewodnik przetrwania"
date: 2025-04-07
lang: pl
categories: [QA, Test Automation, Real Talk]
tags: [automatyzacja, selenium, api, urządzenie fizyczne, strategia testów, mocki, flaky]
---

> „Automatyzacja wszystkiego to piękna idea. Ale to tylko idea.”  
> – Przysłowie testerskie

Nie owijajmy w bawełnę.  
Automatyzacja testów, zwłaszcza w systemach typu **Web UI + API + urządzenie fizyczne + desktop UI**, to nie szwajcarski zegarek.  
To **Gidorah** – trzy głowy, jeden chaos.  

---

## 🐉 Trzy głowy, jeden ból głowy

Wyobraź sobie taki projekt:
- **Aplikacja webowa (App A)**,
- **Desktopowa (App B)** na Qt WebView (czytaj: koszmar),
- **Urzadzenie fizyczne** (nazwa kodowa: **CHUCKY**),
- I jedno wspólne **API**, trzymające to wszystko jak sznurki w marionetce.

Zmieniasz coś w App A → CHUCKY powinien to przyjąć.  
Potem robisz GET po API → sprawdzasz, czy parametry się zgadzają.  
A potem przychodzi tester i odpala App B „na wszelki wypadek”.

---

## 💣 Prawdziwe życie, czyli brud, pot i łzy  
*(...z bezsilności, wylewane cichutko do kawy w ciemnym kątku)*

### Przebieg testu wyglądał mniej więcej tak:

1. **Login, przygotowanie danych, pierdoły.**
2. **Ustaw parametry CHUCKY'ego przez Web UI** – min, max, losowe, z delayem, żeby nie padło.
3. **Zrób GET po API**, sprawdź, czy urządzenie faktycznie przyjęło.
4. **Obserwuj UI.** I módl się, żeby suwak nie odskoczył jak po LSD.

### Co mogło się wywalić?

- **CHUCKY traci połączenie** w środku testu. Bo tak.
- **CHUCKY wypada z rejestru.** Powód? Vibes.
- Zbyt szybkie ustawienia → **CHUCKY robi BRRR** albo crashuje.
- **CHUCKY ma siostry.** *Anabelle*, *M3GAN*. Wyglądają tak samo, ale każda ma inne paramy.
- Ktoś „pożyczył CHUCKY’ego” bo *„myślał, że nikt nie używa”*.
- API mówi OK, ale **UI cofa** param po 5 sekundach.
- **Desktop UI?** Zapomnij. Qt WebView to gremlin z kacem. Selenium nie ma wjazdu, Pywinauto się dławi.

---

## 🧠 „To może zamockujemy?”

Jasne. Można:
- Zamockować **API**, żeby przetestować frontend.
- Zamockować **urządzenie** przez Dockerowy emulator.
- Zamockować **frontend**, testując sam backend.

Ale uwaga:  
**Jeszcze gorsze niż flaky testy są te, które dają fałszywe poczucie pewności.**

W systemach regulowanych albo z krytycznym hardware’em (czytaj: CHUCKY) tylko **pełne E2E** daje ci sen w nocy.  
Bo ręczne testowanie 200+ parametrów to bilet w jedną stronę do wypalenia.

---

## 🪛 Problem z `conftest.py`

Masz testy UI i API w jednym repo.

Co chcesz?
- Robić screenshoty przy failu.
- Ale `driver.take_screenshot()` wywala się przy testach API.
- Więc robisz `try-except` na pałę.
- Teraz twój **conftest.py wygląda jak spaghetti po wypadku.**

Podział?
1. `conftest_ui.py`
2. `conftest_api.py`
3. Global config

I co z tego, skoro **pytest nie wspiera takiego podziału natywnie**?  
Witamy w świecie fixture’ów napuchniętych jak backlog po retro.

---

## 🚨 Presja z każdej strony

Biznes:  
> „Zautomatyzujcie wszystko, co manualne!”

PM:  
> „QA, czy *na pewno wszystko* pokryte?”

QA Manager:  
> „Ej Karol, da się to zautomatyzować, nie?”

Ja (Senior AQA):  
> **„honk-honk 🥲”** *(zaczynam pisać nowy fixture)*

---

## 🧪 Co czasem działało

- Tworzenie **dynamicznych map parametrów** zamiast hardkodów.
- Użycie **emulatorów urządzeń w Dockerze** – morderstwo bez ryzyka.
- Rozdział testów Web UI i API, ale **koordynacja pełną gębą**.
- Założenie, że **ktoś odłączy CHUCKY’ego w połowie testu**.
- Pisanie logów jak powieści detektywistycznej.  
  O 2 w nocy dziękujesz sam sobie.

---

## 🔥 AQA = Ludzki Firewall

Prawda jest taka: automaty nie są magiczne.  
To **wytrenowana kaczka**, która na powierzchni wygląda spokojnie,  
a pod spodem zapierdala jak dzika.

A Ty jako AQA:
- Obrywasz za flaky testy,
- Masz naprawić cudzą architekturę,
- Masz dowieźć 100% pokrycia **na wczoraj**,
- I jeszcze **uśmiechnąć się na sprint review**.

Bo testy nie padły dlatego, że appka jest zjebana…  
tylko dlatego, że **CHUCKY mrugnął**.

---

## Ostatnia myśl

Nie wierz w testowe piramidy z prezentacji.  
**Prawdziwe testowanie to syf, chaos i ból.**  
Ale też coś pięknego – na swój pokręcony sposób.

Więc następnym razem, jak test poleci,  
i ktoś zapyta: „Czemu nie działa?”,  
szepnij tylko:

> **„Gidorahy się nie oswaja. Na Gidorahę trzeba się przygotować.”**

🐉🔥🧪

---

**Stay brutal, testerzy.**  
I pamiętajcie:  
**Mocki to przyjaciele. Logi to terapia. Docker to zbawienie.**
