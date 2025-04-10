---
title: "⚗️ Alchemia kodu – czyli jak pozłacać nic i ogłaszać sukces"
date: 2025-04-10
lang: pl
layout: post
categories: [QA]
tags: [qaRealTalk, itMadness, testingWilderness, qaTherapy]
---

> _IT zgubiło najważniejszy krok w wytwarzaniu oprogramowania: wymagania._

Bo przecież po co definiować, co chcemy zbudować, skoro możemy:

* zacząć pisać kod,
* potem go testować,
* a na końcu dorzucić kogoś, kto udaje, że wie, co to miało robić.

Kod bez wymagań to jak **kleik ryżowy bez soli** – miękki, mętny i kompletnie bez smaku. Ale nie przeszkadza to nikomu w ogłaszaniu sukcesu na sprint review.

> _Projekt rusza, bo musi ruszyć.
Terminy są. Plan jest.
Treść? Dopisze się w locie._

Wchodzimy w chore odwrócenie TDD:

**RED**: nie mamy wymagań

**GREEN**: testy działają, bo nie wiemy, co testujemy

**REFACTOR**: na koniec dorzucamy BA z helikoptera i modlimy się, że rozrysuje flow zanim scope się zmutuje

A ja?
Ja siedzę w QA i mam ochotę krzyknąć przez cały kanał Teams:

> _Czy leci z nami jeszcze Product Owner?
Bo chyba odleciał na Księżyc razem z sensownym backlogiem._

**To nie jest Agile.** 
To nawet **koło Kaizena nie stało.**
To teatr metryk, commitów i pseudozwinności, gdzie:
* zamiast jakości mamy **szybkość**,
* zamiast backlogu mamy **czat z devami**,
* a zamiast sensu mamy **kolorowe tablice i wykresy pokrycia.**

I potem QA ma testować...

Nie funkcje.
Nie logikę biznesową.
Tylko **pozłacane gówno**.

Z zewnątrz lśniący, bo:
* metryki 90% coverage
* tickety w "done"
* dashboardy pulsują zielenią

A wewnątrz?  
Zduplikowane dane, powielony kod, zależności na sznurku, brak rollbacku i losowość w CI.


Ale na demo się da pokazać, więc...
**Zamieniliśmy ołów w złoto.**

QA wie, że to nie działa.
Dev wie, że to nie działa.
BA się domyśla, ale nikt go nie pyta.

Ale PO nie ma, bo:

> _**W tym sprincie nie było go w planie.**_

Dalej?
Zrobimy dalej.
Zbudujemy kolejne warstwy pozłocenia.
Zrobimy CI na testy, które nic nie sprawdzają.
Zrobimy daily, na którym nikt nic nie powie.
Zrobimy scope planning po release.

A jak się coś sypnie?  
To QA. Zawsze QA.

Bo przecież **ktoś musiał patrzeć.**  
Bo przecież **ktoś mógłby zgłosić.**  
Bo przecież **ktoś to testował.**

 **I to jest QA.
 Ostatni alchemik w świecie, gdzie złoto to tylko filtr na dashboard.** 