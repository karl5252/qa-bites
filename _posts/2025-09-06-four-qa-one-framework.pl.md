---
layout: post
title: "Czterech QA. Jeden framework. Zero kontynuacji."
date: 2025-09-06 08:00:00 +0200
categories: [QA]
tags: [automation, reality-check, rotation]
lang: pl
excerpt: Jeden framework, cztery pary rąk i wiele miesięcy. Tylko jedna osoba dowiozła. O tym, dlaczego projekt QA-ów nie wspiera — i co to mówi o samym projekcie.
---

# 📉 Czterech QA. Jeden framework. Zero kontynuacji.

W ciągu ostatnich kilku lat przez projekt przewinęło się **czterech QA**. Tylko jeden zbudował coś trwałego.  
Reszta — z różnych powodów — nie dowiozła.  

To nie tylko opowieść o rotacji. To **diagnoza projektu**, który:

- nie wspiera ludzi,  
- nie rozwija procesów,  
- i nie ma strategii na QA.  

---

## 📌 QA #1 — *TOSCA Dream, Zero Delivery*

- Zadanie: stworzyć automatyzację w **TOSCA**.  
- Efekt po roku pracy:
  - brak testów,  
  - brak frameworka,  
  - brak czegokolwiek do utrzymania.  
- Wniosek?  
  Zły kierunek od początku + brak konkretów = zero efektu.

---

## 📌 QA #2 — *From Scratch to Stable*

- Start **od zera**, bez odziedziczonego kodu.
- Powstało:

  - 🔧 Framework w **C# + Playwright + SpecFlow (BDD)**
  - 🐍 Skrypty w **Pythonie** do zarządzania środowiskami
  - ⚙️ Pipeline’y CI
  - 📚 QA Handover: dokumentacja, wiki, OneNote
  - 📈 ~270 scenariuszy, podzielonych na moduły

- Produkcyjnie używane.  
- Stabilne.  
- Utrzymywane przez jedną osobę.  

---

## 📌 QA #3 — *Lost in Setup*

- Miał doświadczenie, ale…
- Przez **2 miesiące** utknął na konfiguracji środowiska.
- **Nie stworzył żadnego testu**.
- Nie wniósł wartości.

---

## 📌 QA #4 — *Pół roku, zero regresji*

- Mimo pełnej dokumentacji i gotowego frameworka:

  - ❌ brak nowej automatyzacji,
  - ❌ brak refaktoru,
  - ❌ problemy z uruchomieniem testów — trwające miesiącami.

- Cytaty, które zapamiętasz:

  > *“Nie wiem co zrobić, nie ma tutoriala.”*  
  > *“Nie lubię czytać dokumentacji.”*

- Próby przepisywania wszystkiego “po swojemu”, zamiast korzystać z gotowych scenariuszy i stepów.  
- Efekt końcowy?  
  **Brak regresji. Bugi przechodzą. QA przestaje istnieć.**

---

# 🎯 Podsumowanie

- Trzech QA nie dowiozło nic.  
- Jeden QA dowiózł wszystko.  

Ale projekt nie wyciągnął wniosków:

- brak wsparcia technicznego,  
- brak jasnej roadmapy QA,  
- brak decyzji, kto odpowiada za rozwój automatyzacji.

---

## 🧠 Wniosek?

Jeśli w projekcie **QA to zawsze problem**,  
to może problemem **nie są ludzie**, tylko **projekt — i sposób, w jaki traktuje QA**.

---