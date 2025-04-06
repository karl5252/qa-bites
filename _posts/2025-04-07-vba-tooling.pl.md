
---
layout: post
title: "VBA kontra Korpo Procesy: Jak przestałem klepać XML-e i zacząłem żyć"
date: 2025-04-07
lang: pl
categories: [QA, Narzędzia, Real Talk]
tags: [vba, sepa, xml, automatyzacja, druciarstwo, excel]
---

> „Jak ja przychodziłem, to też robiłem ręcznie.”  
> – Klasyk z open space'u

W ramach testów regresyjnych trzeba było przygotowywać pliki **SEPA XML** – przelewy, zwroty, konfiguracje.

Bez API.  
Bez generatora.  
Bez litości.

Kopiuj-wklej z Excela do Notepad++. Mała pomyłka w IBAN?  
Walidacja mówi: nie.  
Wracasz do początku.

---

## 🛠️ Druciarstwo kontrolowane

W pewnym momencie uznałem, że **szkoda życia na ręczne klepanie XML-i**, więc... napisałem własne narzędzie. W Excelu. W VBA.

Co potrafiło?

- Obsługa **8 typów płatności** (w tym 2-in/2-out i zwroty),
- **Lista rozwijana** z IBAN/BIC – bez kopiowania z plików,
- **Zamiana stron płatności** jednym kliknięciem,
- **Płatności przyszłe** – ustaw datę i gotowe,
- **Druk seryjny** – np. 10 przelewów jednym kliknięciem.

Efekt?  
Zamiast bawić się w detektywa po nieudanym imporcie, miałem gotowy zestaw plików, które po prostu działały.

---

## 🤷‍♂️ Bo tak się robiło od zawsze

Dlaczego to narzędzie powstało?

Bo alternatywą była ręczna orka.  
Bo „dedykowany tool” w Javie był dostępny tylko dla wybranych.  
Bo niektórym wystarczało Notepad++ i cierpliwość.  

Ja po prostu postanowiłem **skręcić sobie coś lepszego**.

---

## 🧠 Nie rewolucja, a ewolucja

To nie było rocket science.  
To było **pragmatyczne QA druciarstwo** – reakcja na zbyt dużo frustracji i zbyt mało narzędzi.

Nie miałem ambicji budować startupu wokół Excela.  
Chciałem tylko **nie robić 20 razy tej samej czynności** i nie tracić czasu na szukanie literówek w XML-u.

---

## ✅ Wnioski

- Jeśli możesz coś zautomatyzować – zrób to. Nawet „brzydko”.
- VBA w Excelu to nie wstyd. To narzędzie.
- QA też może robić sobie życie łatwiejszym – bez czekania na zielone światło z góry.

---

Nie każdy tool musi być w Javie, nie każde rozwiązanie musi być piękne.  
Czasem wystarczy coś, co **po prostu działa**.
