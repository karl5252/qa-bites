---
layout: post
title: "Singleton w Pythonie: Globalne zło czy lokalny bohater?"
date: 2025-04-07 10:00:00 +0200
last_modified_at: 2025-04-07 10:00:00 +0200
categories: [QA, Python, Wzorce Projektowe]
tags: [singleton, wzorce projektowe, python, automatyzacja]
lang: pl
---

> _„Singleton to zło!”_ – ktoś w internecie, pewnie z czerwonymi oczami od nadmiaru DI.  
> _„A jednak tu jesteśmy.”_ – Ty, próbując ogarnąć współdzielony stan jak dorosły człowiek.

Pogadajmy o najbardziej znienawidzonym wzorcu projektowym, który wraca jak flaky test, co **"już był naprawiony"** – czyli **Singleton**.

---

## 😈 Wzorzec, który każdy lubi hejtować

Singleton gwarantuje, że klasa ma **tylko jedną instancję** i udostępnia do niej globalny dostęp.

Brzmi sensownie?  
To czemu ten hejt?

Bo rzekomo:

- Wprowadza **globalny stan**,
- Psuje testowalność,
- Łączy wszystko ze wszystkim,
- Sprawia, że CI eksploduje jak w memie z psem i kawą w płomieniach.

A mimo to – działa. Rozwiązuje konkretne problemy.  
Zwłaszcza w kodzie QA.

---

## 🤫 Kiedy Singleton MA sens

Masz klasę **reportera**, która:

- Tworzy raport HTML raz,
- Dopisuje logi z każdego kąta testów,
- Zamyka raport na koniec z godnością.

Jakie masz opcje?

- Tworzyć nowego reportera w każdym teście?  
  _Nie. Po prostu nie._

- Trzymać to jako globalną zmienną?  
  _Witamy w spaghetti world._

- **Singleton?**  
  _Elegancko. Skutecznie. Z kontrolą._

Oto leniwa wersja Singletona w Pythonie:

```python
class SingletonLazy:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

class Reporter(SingletonLazy):
    def __init__(self):
        self.log = []

    def add_log(self, message):
        self.log.append(message)
```

Użycie:

```python
r1 = Reporter()
r2 = Reporter()

print(r1 is r2)  # True
```

Jedna instancja. Zero chaosu.

---

## 🙀 Ale przecież to globalny stan!

Tak. I co z tego?  
Twój **ConfigManager**, **połączenie z DB**, **instancja drivera Selenium** – to już są Singletony.  
Po prostu czasem udajesz, że nie są.

Klucz to **dyscyplina**.  
Nie rób z Singletona śmietnika. Używaj tam, gdzie ma sens i zachowuj się odpowiedzialnie.

---

## ✅ Gdzie Singleton błyszczy w QA

- 🗂️ **ConfigManager** – jeden config, jedno źródło prawdy.
- 🧪 **Reporter/Logger** – jeden raport, zero chaosu.
- 🔌 **Połączenia do DB** – reuse, nie recreate.

Pamiętaj: piszesz framework testowy, nie architekturę NASA.

---

## 🧠 TL;DR

- Singleton nie jest złem wcielonym. **Źle użyty Singleton – już tak**.
- Używaj tam, gdzie ma sens: centralna kontrola, współdzielony zasób.
- Zachowuj kontrolę i myśl architektonicznie, nie kompulsywnie.

---

## 🔥 Na zakończenie

Singleton to jak piła łańcuchowa.  
W nieodpowiednich rękach – masakra. Ale dobrze użyta – tnie jak marzenie.

Nie przepraszaj, że go używasz. Używaj świadomie.  
Niech inni wrzeszczą „antywzorzec”, a Ty rób robotę i generuj raporty jak boss.

*Testuj z godnością. Singletonowo, ale odpowiedzialnie.* 🧪
