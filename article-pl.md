# 🔒 NFC Fraud: Proof-of-Concept, który nie daje spać

**Autor: Rafał Konieczek**  
**Data: 02.07.2025** 
**Wesprzyj autora:** [Postaw kawę ☕](https://www.buymeacoffee.com/rafal)

---

## ✨ Wstęp – „zadziałało czy nie zadziałało?”

W świecie, w którym „zbyt mało danych” oznacza „niebezpiecznie spokojnie”, czasem warto zadać pytanie:  
**czy wszystko, co nie wywołuje alarmu — naprawdę jest bezpieczne?**

Ten materiał to nie „proof of hack”, nie kod exploita.  
To **proof-of-concept słabości modelu zaufania** – w pełni zgodny z zasadami działania NFC i systemów płatniczych.

---

## 🎯 Cel koncepcji

Pokażę Ci, jak można:

- uzyskać **autoryzację płatniczą offline** (w pełni legalnie),
- **przenieść ją w czasie lub przestrzeni**,
- i **sfinalizować transakcję**, gdy ofiary już dawno nie ma — i nawet nie wie, że do czegoś doszło.

Bez złamania PIN-u.  
Bez przechwytywania danych.  
Bez ingerencji w kartę.

---

## 🧪 Scenariusz: cichy atak offline

Wyobraź sobie, że:

1. Ofiara przykłada kartę do terminala (np. parkometru), który **nie ma natychmiastowego połączenia z siecią**.
2. System NFC przyjmuje autoryzację, ale nie finalizuje jej – buforuje ją lokalnie.
3. Z jakiegoś powodu transakcja nie przechodzi. Użytkownik odchodzi, myśląc, że „coś nie działało”.
4. W międzyczasie:
   - autoryzacja nadal istnieje w pamięci lokalnej (lub jej sygnatura),
   - atakujący może ją **wyciągnąć, zapisać, przesłać lub sklonować**,
   - i użyć jej „gdzie indziej” lub „później”, o ile system pozwala.

W niektórych modelach terminali offline to... **działa**.

---

## ⚙️ Dlaczego to w ogóle jest możliwe?

Systemy płatności kartą bezstykową (NFC) mają wiele trybów działania — **online, offline, fallback, z limitem bez PIN-u, itp.**.  
W zależności od konfiguracji:

- terminal **może zaakceptować autoryzację bez natychmiastowej weryfikacji online**,
- niektóre implementacje **buforują transakcje** (np. parkomaty, automaty biletowe),
- a karta **nie „wie”, że ktoś ją ponownie emuluje lub że jej dane zostały wykorzystane później**.

Czy to luka?  
Nie.  
To **architektura zaufania** oparta na tym, że *ludzie są uczciwi*, a *czas i miejsce mają znaczenie*.

---

## 📉 Dlaczego to jest niebezpieczne?

Bo:

- autoryzacja = zgoda,
- brak potwierdzenia = brak alarmu,
- a czas + miejsce + intencja = nikt nie zauważa nieprawidłowości.

Z punktu widzenia banku:  
„Transakcja wygląda OK.”  
Z punktu widzenia terminala:  
„Płatność zaakceptowana wcześniej.”  
Z punktu widzenia użytkownika:  
„Nic się nie stało, nie zadziałało.”

A tymczasem:  
**ktoś użył Twojej autoryzacji — tylko gdzie indziej.**

---

## 🧠 Wnioski

- Nie chodzi o przechwytywanie kart.
- Nie chodzi o exploity.
- Chodzi o **przerwanie ciągłości między miejscem, czasem a intencją**.
- To atak na model zaufania, a nie na protokół.

Banki?  
One są gotowe – ale kalkulują ryzyko.  
Ten scenariusz **jest tak niszowy**, że statystycznie nie opłaca się z nim walczyć.

Ale jeśli ktoś chce...  
To nie będą ofiary „techniczne”.  
To będą ofiary „statystyczne”.

---

## 🧩 Co dalej?

📦 Repozytorium zawiera pełny tekst koncepcji (`nfc-fraud-proof.txt`) oraz artykuły w wersji polskiej i angielskiej.  
Możesz:

- skomentować, rozwinąć lub zakwestionować w Issues,
- pokazać to swojemu CISO,
- albo... zastanowić się, czy Twoja karta offline też by to „kupiła”.

> Dzięki za przeczytanie.  
> — Rafał Konieczek
