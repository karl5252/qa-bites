---
layout: post
title: "QA Van Damme w Świecie IT Freak Circus"
date: 2025-05-21 11:00:00 +0200
categories: [QA]
tags: [realtalk, frustration]
lang: pl
excerpt: Load testy? Zrobione. Procesy? Ustawione. A i tak pytają, czy znam JMeter. Manifest frustracji QA, który jeszcze klika approve… ale już wie, że w kolejnym projekcie będzie RC.
---

## 🥁 Akt 0 – A co ja się tam znam

Zrobiłem testy – Locust, realistyczny load, 5 userów.  
Czas odpowiedzi? **50 sekund.**  
Overhydration, duplikaty requestów, wszystko się dławi.

Wyniki? Są. Wykresy? Gotowe.

> – Ale czy znasz JMeter?

Tak, znam. Ale **zrobiłem to dobrze, a nie „jak było kiedyś”**.

Okazało się, że „kiedyś”:

– nie było asercji (bo nie przechodziły),  
– endpointy były z czapy,  
– i nikt nie spojrzał na raport.

Ale przecież **co ja się znam**.  
Jestem tu tylko dwa lata.  
Nie to co R – **pół roku w firmie i już ustala milestone’y**.

Ja tylko:

– ogarnąłem proces w miesiąc,  
– napisałem pierwsze automaty,  
– wziąłem się za backlog,  
– i testuję to, co devsi wys*ają.

Ale spoko.  
> „W dupie byłeś, g**wno widziałeś.” 
Liczy się tylko jedno:  
> *„Bo tak było w starym planie.”*

Witaj w **projekcie, który ma wszystko, oprócz rozumu.**

Nie ma RC.  
Nie ma wizji.  
Nie ma ludzi, tylko role, które **są obecne głównie na papierze.**  
QA?  
QA to splitujący ninja z deploymentem w jednej ręce i regressionem w drugiej.

---

## 🧟‍♂️ Akt I – Bestiariusz Projektowy (czyli mój zespół w pełnej krasie)

### 🧠 Lider – QA Teoretyk z Uczelni i PowerPointa  
Nie z trzech startupów.  
Z **jednego** – i **dziewięciu lat w akademii**.  
Człowiek, który wie, co to jest test wielowymiarowy i jak wygląda macierz pokrycia…  
…ale **nie wie, co znaczy POC.**

Tak.  
Zapytany o POC odpowiedział:

> *„I don't understand. Please explain what is POC.”*

I wtedy wiedziałem, że jestem sam.  
**To nie lider. To Google Translate do korpomowy.**

Nie testuje.  
Nie rozumie fazy RC.  
Ale zaprojektuje ci roadmapę do testów z milestone’ami.  
I zapyta, czy QA już wszystko kliknął.

---

### 🧻 Senior QA – Lord ThanksTeam  
Zniknięty od rana, ale o 17:30 pisze *„Thanks team :)”*.  
Nie testuje.  
Nie tłumaczy.  
**Nie robi nic, poza udawaniem zajętego.**

---

### 📬 Release Managerka – Królowa Approva  
Jej supermoc to **skanowanie Slacka w poszukiwaniu słowa „approve”**.  
QA kliknie?  
Super – można deployować.  
A jak pytasz, kto będzie na piątkowym release’ie?

> *„Nie wiem, ja mam wtedy wolne.”*

Jak produkcja się wywali:  
> *„Czy QA testował?”*

**A ty właśnie debugujesz bug, którego nawet nie było w scope.**

---

### 👻 Menedżer Widmo  
Kiedy trzeba coś zatwierdzić – **niedostępny**.  
Kiedy trzeba kogoś opierdzielić – **obecny**.  
Strategia?

> *„To trzeba przegadać z zespołem.”*

A zespół?  
Też nie wie, co się dzieje.  
I nie chce wiedzieć.

---

### 🪤 Juniorka 4-letnia – Patronka Ślepego Optymizmu  
W projekcie od lat.  
Zawsze *wszystko jej działa*.  
Frontend się topi, logi płoną, overflow na stronie jak tsunami?  
> *„U mnie wszystko OK :)”*

Zgłoszenia od QA?  
Ignorowane.  
Bo przecież działało.  
A jak coś nie działa – to wina środowiska. Albo Karola.

---

## 💣 Akt II – QA vs Absurd

Brak RC?  
Nie szkodzi.  
Po co ustandaryzować cokolwiek, skoro **QA zawsze się dopasuje**.

Zaproponowałeś sensowny model:

- QA testuje **tylko** na `test`,  
- robi sanity **na `acc`**,  
- `dev` i `ephemeral`? → niech sobie devowie testują **swoje rzeczy**.  

Ale nie.  
Bo przecież w tym projekcie:

- QA testuje na `dev`,  
- QA testuje na `test`,  
- QA testuje na `acc`,  
- QA testuje na `ephemeral`,  
- QA **aprobuje wszystko, co się da kliknąć**.

Bo jak coś wycieknie na produkcję, to zawsze będzie jedno pytanie:
> *„Karol, a ty to testowałeś?”*

Nieważne gdzie.  
Nieważne czy miałeś dostęp.  
**Nieważne, czy to było twoje zadanie.**

---

## 🔥 Akt III – JMeter kontra Rzeczywistość

Zrobiłeś testy w Locust.  
Debugowalne, czytelne, rozszerzalne.

Ale nie.  
> *„Ma być w JMeter.”*

Bo to już było wcześniej.  
Bo ktoś kiedyś kliknął „Add Thread Group” i uznał, że tak już będzie do końca czasów.

JMeter się sypie?  
Wywala się na pustym headerze?  
Debug to XML-owy horror z piekła?  
**Nieważne.**  
Bo to jest „oficjalne”.  
Bo **„ktoś kiedyś coś tam robił”**.
Bo pipeline jest zielony!
Szkoda tylko, że dla GraphQl nikt nie pomyślał o dodaniu asercji i przeczytaniu raportu...

---

## 🚨 Akt IV – QA i Approve na Produkcję

DevOps nie ma?  
Nie szkodzi.  
QA kliknie. QA zrobi release.  
QA nie musi czekać, bo przecież **„w DevOps każdy robi wszystko”**, nie?

**OTÓŻ NIE.**

DevOps to odpowiedzialność.  
DevOps to podział ról i zaufanie do kompetencji.  
A nie „wrzućcie to na produkcję, bo nie ma komu”.

Ale Release Managerka już pobłogosławiła:  
> *„Super, że QA to ogarnia, szybciej pójdzie!”*

Tylko QA potem zostaje z logami, krzyczącym BA, rollbackiem i pytaniem:
> *„Dlaczego to poszło?”*

---

## 🧩 Akt VI – QA w Świecie Wielu Klientów (czyli Matrix w Matrixie)
R mówi:

„Nie może być tak, że każdy klient chce inaczej. Trzeba pogadać z BA.”

A ja już mam:
– framework z flagami dla funkcji per kraj,
– sanity testy różnicujące zachowanie,
– mocki pod 3 wersje środowisk,
– i wiedzę, że BA nie przekona klienta, który płaci.

Bo Grass Valley mnie nauczyło jednego:

* klient A pracował na legacy 3.6 (i nie chciał ruszyć),
* klient B chciał nowe security,
* klient C nie chciał nic, bo „lubi jak jest”.

Więc automaty?
3.6 – dla umarłych,
3.9 – dla nieufnych,
3.11 – dla świętych z OAuth-em i tokenami.

Ale co ja się tam znam.
R w firmie pół roku i już wie, że wszystko da się „przegadać z BA”.
A ja wiem jedno: nic nie jest bardziej stałe niż klient, który mówi „chcę to inaczej”.

---
## 🧘 Akt V – Split, Burnout i Ninja Logout

Już nawet nie robię szpagatu.  
Już po prostu **leżę na scenie tego cyrku i czekam, aż się zawali.**

Piszę testy,  
piszę sanity,  
klikam approve,  
robię deploy,  
debuguję cudzy kod,  
i jeszcze pytają, czy znam JMeter.

---


## 🏁 QA Van Damme kończy pokaz  

Jeszcze nie rzuciłem klawiaturą.  
Jeszcze się loguję.  
Jeszcze debuguję błędy, które nie są moje.

Ale to już nie praca.  
To **egzorcyzm kariery.**

  
I tylko jedno wiem na pewno:  
**Mój kolejny projekt będzie miał RC.  
I nie będę jedynym, który klika approve.**

---

## 🎬 Scena po napisach – Regresja jednego kraju

R kończy regresję w 15 minut.  
Jakim cudem? Ponieważ klika **jeden kraj z pięciu.**  
„Flagowy kraj,” jak twierdzi.  
A reszta? *„Używamy CMS, jest dobrze.”*

Ja przeklikuję każdy.  
Bo wiem:  
– co działa na DE, sypie się na FR,  
– co ładuje się dla UK, wyrzuca błędy dla PL,  
– a CMS? CMS to miejsce, gdzie bugi idą się schować.

Kiedy sprawdzam wszystko –  
**pojawiają się pęknięcia na fasadzie.  
Puzzle w końcu układają się w całość.**

Ale hej, R „skończył regresję” do lunchu.  
A ja wciąż walczę z wiatrakami o 16:00.

---

*QA Frustracja Vol. 5 – spisana 2025-05-21 przez człowieka, który wie, czym jest POC, ale już nie wie, dlaczego wciąż tu siedzi.*
