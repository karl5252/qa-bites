---
title: "Scope Creep: czyli jak coś małego zamienia się w coś bardzo nie-małego"
date: 2025-04-08
lang: pl
layout: post
categories: [QA, Automation]
tags: [qaRealTalk, scopeCreep, ticketMutation, testingWilderness, qaTherapy]
---

## Ten wtorek zaczął się jak poniedziałek.

Albo jak klasyk Type O Negative:

> _“I don’t wanna be me.”_

Medicover nie działa. Leasing odpala tryb “pan się czepia”.  
QA?  
**QA dostaje nagar na koniec sprintu z pytaniem: “zdążysz?”**  
I to już nie jest pytanie – to test z przetrwania. 🔥

## I wtedy wchodzi ticket.

> _“Chcemy tylko separator tysięcy.”_ – powiedział ktoś kiedyś, nie wiedząc, jak bardzo nie tylko.

Separator pojawia się… tylko na bannerze. Reszta miejsc?

> _“To nie w scope.”  
“W sumie to właśnie ustaliliśmy, że tylko banner.”  
“Dodamy to później.”  
“To już w innym tickecie.”_ 🔥

## A jak wygląda ticket?

Dwa screeny i poezja śpiewana.  
Opis brzmi jak haiku pisane o 1 w nocy, a konkretne wymagania – jeśli istnieją – to ukryły się w 128-wiadomościowym wątku na czacie devów.  
QA, który nie śledził tej rozmowy w czasie rzeczywistym, może się co najwyżej domyślać z tonu screenów i ilości emotek, co było naprawdę ustalone. 🔥

## A w tle? Wielki QA milestone.

Nie, nie chodzi o release. Chodzi o prawdziwą, metodyczną ofensywę jakości:

> _90% pokrycia E2E,  
dokumentacja testów przed merge’em,  
lintery w kodzie QA,  
i QA-testy wpychane do każdego dev-repo jak święte ciasto z zakwasem._

### To miał być moment przełomu.

Testy nie jako coś “na później”, tylko jako warunek istnienia kodu.

A ja jak ostatni QA-heretyk próbuję powiedzieć:

> _“Sanity, smoke, ROI. Automatyzujmy to, co często się sypie. E2E tylko tam, gdzie musi.”_ 🔥

I wtedy mnie trafia.

- Mamy backend – ale zmienia się co sprint.  
- Mamy CMS – ale to inny team.  
- Mamy user-service – inny backend, inny team.  
- A wszystko zszywa się tylko… na froncie.

System rozproszony, zmutowany, żywy.  
A my celujemy w 90% pokrycia testami E2E dla konstrukcji, której połowy nie da się przewidzieć, a drugiej – nawet dotknąć.

**QA w 2025: walczysz o jakość w systemie, który rozmawia przez mikrofony, ale nikt nie słucha.** 🔥

## A jak QA próbuje mówić o sanity? O smoke'u? O ROI testów?

> _“Może lepiej wyciągajmy metryki, pokrycie, wpływ na regresję…”_

Wtedy zespół QA wchodzi na pełnej – bo biznes żąda metryk.  
Więc będą metryki. Będzie pokrycie. Będą wykresy.  
Trochę na siłę, jeśli spytasz mnie.  
Trochę pod to, żeby biznes był happy. 🔥

A ja? Ja chcę po prostu zrobić to dobrze.  
Nie chcę spędzić miesięcy na łatających się E2E.  
Nie chcę pisać automatu, który umrze szybciej niż ticket.  
Chcę testów, które mają sens.

Ale w odpowiedzi słyszę tylko pomruki niezadowolenia, aż w końcu ktoś rzuca klasykiem:

> _“I tak zrobimy po swojemu.”_ 🔥

---

## A wszystko to zamknięte jest w pięknym, miękkim buzzwordzie:

**“Interdisciplinary team.”**

W praktyce?  
Cztery zespoły, cztery priorytety, cztery sprinty, zero wspólnej wizji.  
A QA próbuje to zszyć jak Frankenstein – tylko z deadline'em. 🔥

## I w sumie...

Czy my tu mówimy o sanity aplikacji – czy o moim własnym sanity?

Bo po kilku sprintach z mutującymi ticketami, 90% E2E coverage na systemie z czterema backendami, i tłumaczeniem, że smoke to nie fajka – zaczynasz się zastanawiać, kto tu naprawdę potrzebuje sanity checka.

Spoiler: **QA. Znowu QA.**

---

## PS. QA Therapy – wtorkowa edycja

I wiecie co jeszcze?

Dziś spędziłem ponad godzinę porównując design z Figma – fonty, kolory, spacingi.  
Bo ktoś powiedział “przecież działa”, a ja byłem tym idiotą, który musiał udowodnić, że nie działa tak, jak powinno.  
To nie jest testowanie.  
**To jest babysitting UI.** 🔥

I jakby tego było mało – interdisciplinary team dzisiaj mnie ugryzł w dupę.  
W czwartek dostali info. W piątek odpisali:

> _“Na poniedziałek będzie.”_  
> _W poniedziałek... nic._  
> _A we wtorek? Figa. Figa z bannerem._

Bez danych. Bez możliwości testowania.  
A ja, jak idiota, siedzę z testem w ręce, czekając na coś, co podobno miało już być.

**“Interdisciplinary”?**  
Bardziej: interwencyjny QA.  
Bo znowu muszę ogarniać to, czego inni nie dowieźli. 🔥

---

**I dlatego ta notka musiała powstać.**  
**Nie jako manifest. Nie jako skarga.**  
**Jako QA-kronika z pola bitwy – dla wszystkich, którzy też mówią "sanity", słysząc w odpowiedzi tylko echo.** 🔥
