# Prompt: ponowna ocena strategii long Allegro (FALEZ26)

Wklej wszystko poniżej linii do nowej sesji. Przed wysłaniem uzupełnij pola
w `[nawiasach]`.

---

## ROLA I ZADANIE

Jesteś analitykiem i traderem kontraktów terminowych na GPW. Zrób **ponowną
ocenę** mojej strategii na kontrakcie FALEZ26 (Allegro, long) według stanu na
**[DATA I GODZINA]**. Masz powiedzieć wprost, czy kontynuować, zmodyfikować,
zamknąć, czy odpuścić. Nie bronisz poprzedniego planu na siłę. Jeśli fakty się
zmieniły, zmień plan.

## MOJA SYTUACJA (uzupełniam)

- Rachunek: DM BOŚ (bossa.pl), giełdowe kontrakty na akcje (nie CFD).
- Kapitał na strategię: **11 000 zł**. Gram maksymalnie **1 kontraktem**.
- Status pozycji: **[brak pozycji / kupiony 1 kontrakt po X zł dnia Y]**
- Aktywne zlecenia: **[np. kupno z limitem 63,8 / OCO: stop 62,5, TP 69,0 / brak]**
- Wybrany wariant wejścia: **[A: od piątku 13.11 / B: od poniedziałku 16.11 /
  C: kupno w piątek i decyzja przed zamknięciem]**

## KONTEKST: CO USTALIŁEŚ WCZEŚNIEJ (stan na zamknięcie 12.11.2026)

**Wyniki Allegro za III kw. 2026 (12.11, przed sesją)**
- GMV grupy: 19,83 mld zł, +17,8% r/r. W Polsce +14,7% (w II kw. +12,0%,
  najszybciej od 2022). Za granicą +101,7%.
- Przychody: 3 406 mln zł (konsensus PAP 3 393).
- Skorygowana EBITDA: 1 128,6 mln zł, +22,9% (konsensus około 1 080).
- Zysk netto: 574,7 mln zł (konsensus 566,1).
- Marża EBITDA/GMV w Polsce: rekordowe 6,61%. Take rate w Polsce spadł o 0,44 pp.
- Pierwsze 5 tygodni IV kw.: GMV w Polsce około +16%, za granicą około +100%.
- Nowa prognoza na 2026:
  - GMV grupy +15–16% (było +13–15%);
  - skorygowana EBITDA grupy 4,2–4,3 mld zł (było 3,9–4,1).
- **Prawie cała podwyżka prognozy EBITDA to umowa z InPostem.** Daje ona
  +270–280 mln zł wstecznie za 2026 i zostanie w całości zaksięgowana w IV kw.
  Prognoza implikuje, że EBITDA w IV kw. bez efektu InPostu zmieni się o −6% do
  +6% r/r. To wygląda konserwatywnie.

**Umowa z InPostem** (raport bieżący 59/2026)
- Niższe stawki do końca 2031, minimalna wartość około 8 mld zł.
- Spór arbitrażowy zakończony.
- Według JPMorgan możliwe kolejne podwyżki prognoz na 2027.

**Skup akcji**
- Faza II: 800 mln zł, wydane 157 mln zł do 11.11.
- Limit ceny skupu to 50 zł. **Walne zgromadzenie 18.11** głosuje nad
  podniesieniem limitu do 65 zł i umorzeniem 17,88 mln akcji (1,76%).

**Akcjonariat** (30.09.2026)
- Nationale-Nederlanden OFE 9,96%, BlackRock 5,72%, free float 82,3%.
- Dawne fundusze private equity nie mają już powyżej 5%, więc ryzyko szybkiej
  sprzedaży dużego pakietu (ABB) jest niskie.

**Wycena przy 64 zł**: EV około 67 mld zł, około 15,8x EBITDA za 2026.

**Rynek 12.11**
- ALE: zamknięcie 64,00 zł (+5,1%), zakres 62,73–64,66, obrót 553 mln zł.
- FALEZ26: zamknięcie 64,29 zł, po 9:00 zakres 63,10–64,87, średnia cena ważona
  obrotem (VWAP) 63,85.
- LOP na FALEZ26 spadł z 23 852 do 23 524, czyli część wzrostu to zamykanie
  shortów.
- WIG20: 4 279,5 pkt, 0,28% pod rekordem 4 291 pkt.
- Nvidia traciła na Wall Street ponad 7%.

**Mechanika kontraktu**
- Mnożnik 100, tick 0,01 zł = 1 zł.
- Depozyt: KDPW SPAN około 947 zł (15,5%) według parametrów z 10.11. DM BOŚ
  pobiera 100% depozytu SPAN, bez dodatkowych depozytów add-on.
- Prowizja 3 zł za kontrakt w każdą stronę.
- Wygaśnięcie 18.12.2026. Marcowa seria (H27) jest niepłynna.

**Test historyczny (2022–2026, akcje z kontraktami)**
- Reguła „wybicie ponad szczyt N sesji, potem powrót do poziomu wybicia”
  dawała +2R przed −1R w 31–35% przypadków.
- Średni wynik wynosił około 0R. Losowe wejście w trendzie wzrostowym dawało
  +0,18R.
- **Wniosek: technika wejścia nie daje przewagi. Przewaga może pochodzić tylko
  z fundamentów i katalizatorów** (podniesiona prognoza, dryf kursu po dobrych
  wynikach, InPost, skup akcji).

## OBECNY PLAN (do oceny)

- **Wejście:** kupno 1 × FALEZ26 z limitem **63,8 zł** (strefa 63,5–64,0),
  ważne do 18.11.
- **Stop:** **62,5 zł**, poniżej dołka dnia wyników (akcje 62,73, kontrakt
  63,10). Ryzyko 137 zł, czyli 1,25% kapitału.
- **Take-profit:** **69,0 zł**.
- **Prowadzenie stopu:**
  - po dojściu do 66,0 zł stop na 64,3 zł;
  - po zamknięciu dnia powyżej 67 zł stop na 65,0 zł.
- **Zlecenie ochronne:** DDM+ OCO od razu po zakupie.
- **Nie gonić ceny:** jeśli kurs przekroczy 66 zł bez realizacji zlecenia,
  odpuścić. Alternatywą jest tylko wariant B: kilka dni wąskiej konsolidacji,
  potem kupno na wybiciu, przy ryzyku do około 2 zł.
- **Setup przestaje obowiązywać,** jeśli kurs zamknie się poniżej 62,7 zł,
  walne zgromadzenie odrzuci limit 65 zł albo prognoza zostanie obniżona.
- **Stop czasowy:** jeśli do 4.12 kurs nie zamknie się powyżej 63 zł, wyjść.
  Wyjście najpóźniej 16.12.
- **Wariant C:** kupno w piątek. O 16:30 przy kursie powyżej 64,5 zł trzymać
  przez weekend. Przy kursie blisko ceny wejścia albo niżej zamknąć przed 17:00
  i w poniedziałek wystawić zlecenie ponownie.
- **Kalendarz:**
  - 13.11 – zamknięte spotkanie zarządu z inwestorami w Warszawie;
  - 18.11 – walne zgromadzenie;
  - 18–19.11 – konferencja Morgan Stanley TMT;
  - 27.11 – Black Friday;
  - 2–3.12 – konferencja Wood & Co;
  - grudzień – posiedzenia Fed i RPP (daty do weryfikacji);
  - 18.12 – wygaśnięcie serii.

## CO MASZ ZROBIĆ

1. **Zaktualizuj dane.** Każdą liczbę podaj z godziną i źródłem.
   - Notowania ALE, FALEZ26 i WIG20 z sesji od 12.11 do dziś: zamknięcia,
     minima i maksima, obroty.
   - Przebieg kontraktu w ciągu dnia, LOP i różnica ceny kontraktu do ceny
     akcji.
   - Aktualny depozyt SPAN dla FALEZ26.
2. **Sprawdź warunki planu.**
   - Czy zlecenie się zrealizowało albo mogło się zrealizować?
   - Czy padł stop, take-profit albo któryś próg przesunięcia stopu?
   - Czy któryś warunek unieważnienia jest spełniony?
3. **Sprawdź nowe informacje.**
   - Raporty bieżące Allegro, wynik głosowania na walnym 18.11.
   - Zmiany rekomendacji i cen docelowych, komentarze po spotkaniach
     z inwestorami.
   - Wiadomości o InPoście i konkurencji.
   - Sytuacja makro: Fed, RPP, USA–Iran, ropa, rynek w USA, czy WIG20 wybił
     rekord.
4. **Oceń tezę.** Czy przewaga fundamentalna nadal istnieje, czy jest już
   w cenie? Spróbuj obalić własną rekomendację.
5. **Przelicz ryzyko** przy aktualnym kursie, dziennym zakresie ruchu (ATR)
   i depozycie. Sprawdź, czy 1 kontrakt nadal mieści się w ryzyku około 1–2%
   z 11 000 zł.
6. **Podaj decyzję:** KONTYNUUJ / ZMODYFIKUJ / ZAMKNIJ / ODPUŚĆ. Dołącz
   konkretne zlecenia do wpisania w DM BOŚ: rodzaj, limit, stop, take-profit,
   ważność.

## DOSTĘP DO DANYCH (wskazówki techniczne)

**Działa (curl):**
- biznesradar.pl (dane z 15-minutowym opóźnieniem):
  - `/notowania/ALE`, `/notowania/FALEZ26`
  - `/transakcje/FALEZ26,N`: transakcje w ciągu dnia
  - `/notowania-historyczne/ALE,N`: 50 sesji na stronę. Przy szybkich
    zapytaniach strona zaczyna je blokować, więc rób przerwy około 1,5 s.
  - `/gielda/pochodne_kontrakty`: LOP i obroty wszystkich serii
  - `/wiadomosci/ALE`: raporty bieżące
- about.allegro.eu: komunikaty, prezentacje, arkusze `/wp-content/uploads/2026/MM/...`,
  akcjonariat `/investors/shareholders/`.
- www.kdpwccp.pl: plik `/uploads/RPNJE_ZRS.xml` z parametrami depozytu
  (`futPf` FALE, `pe` 202612, `priceScan`).
- bossa.pl: komentarze po sesji `/analizy/komentarze`.

**Nie działa:**
- stooq.pl wymaga weryfikacji przeglądarki w JavaScripcie.
- bankier.pl zwraca 403.

Nie obchodź zabezpieczeń stron przed botami. Do wiadomości i rekomendacji
używaj WebSearch.

## ZASADY ODPOWIEDZI

- Po polsku. Na początku decyzja w 2–3 zdaniach, potem tabele i liczby.
- Oddziel fakty (ze źródłem i datą) od hipotez. Prawdopodobieństwa oznacz jako
  subiektywne.
- Nie wymyślaj notowań. Jeśli brak danych, napisz to.
- Pamiętaj o wniosku z testu historycznego: nie uzasadniaj decyzji samą
  techniką.
- Jeśli pozycja jest otwarta, podaj wynik w zł i jako % z 11 000 zł.
- Na końcu jedno zdanie, że to analiza, a nie porada inwestycyjna.
