---
layout: post
title: "Jak przypadkiem zrobiłem grę – od rzutnika kością do apki na Flasku"
date: 2025-04-07
lang: pl
categories: [Python, TDD, Game Dev, Projekty z nudów]
tags: [python, flask, game dev, tdd, projekty hobbystyczne, super farmer]
---

> „To miał być tylko rzut kością…”  
> – Ja, naiwny.  

---

## 🎲 Wszystko zaczęło się od... Super Farmera

Graliśmy z córką.  
Było fajnie, nostalgicznie, ale coś mnie tknęło:

**„A może by tak zrobić to w Pythonie? Przecież to banalne.”**

Tak, jasne. *Proste jak konstrukcja cepa.*  
Tylko że potem tym cepem sam się walnąłem w łeb.

---

## 🐍 Zaczęło się niewinnie...

Plan był prosty:  
Napisać mały CLI do rzutów kostką.  
Taki na dwie funkcje, dla zabawy.

...a potem dopisałem logikę zwierząt.  
...a potem pojawiło się API.  
...a potem Flask, bo skoro już mam backend, to czemu nie frontend?

Zanim się zorientowałem, miałem mini-gierkę z panelem do debugowania.

---

## 🧪 TDD uratowało mi tyłek

Kiedy zacząłem pisać testy przed kodem, nagle przestałem się gubić w chaosie.  
Testy dawały mi sanity-check.  
I wierz mi – **debugowanie ekonomii królików i lisów to nie zabawa.**

---

## 💡 Czy wszystko ma sens? A kogo to obchodzi

Niektóre elementy projektu są... delikatnie mówiąc, „twórcze”.

Był taki moment, że zamiast tworzyć osobny system kolejkowania zdarzeń,  
po prostu wykorzystałem istniejący obiekt, który do tego nie pasował.

Ale działało.  
Testy przechodziły.  

A jak wiadomo:

> **Jak testy przechodzą, to kod „jest gotowy”™.**

---

## 🔧 Co tam siedzi pod maską

- Backend w Pythonie na Flasku
- REST API do logiki gry
- Dynamiczna talia, rzuty, zwierzęta, ataki wilków i lisów
- TDD od samego początku
- Błędy z poczuciem humoru (bo czemu nie)

Repo? Proszę bardzo:  
👉 [github.com/karl5252/SuperPythonsFarmer](https://github.com/karl5252/SuperPythonsFarmer)

---

## 🚀 Po co to wszystko?

Bo mogłem.  
Bo mnie to bawiło.  
Bo łatwiej debugować w kodzie niż szukać zagubionego żetonu pod stołem.

Niektóre projekty po prostu się dzieją.  
Ten narodził się z nostalgii, zbudował z chaosu i... **działa.**

---

**Jeśli kiedykolwiek też przypadkiem zrobisz grę – nie walcz z tym.  
Po prostu dodaj testy.** 🐺🐰🦊
