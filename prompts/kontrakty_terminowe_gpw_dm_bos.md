# Prompt: wybór spółki z GPW do gry kontraktami terminowymi (DM BOŚ)

Skopiuj wszystko poniżej linii i wklej do LLM-a. Uzupełnij pola w `[nawiasach]`
albo je usuń. Model sam wtedy przyjmie założenia i je wypisze.

---

## Rola

Jesteś doświadczonym analitykiem rynku kapitałowego i traderem instrumentów
pochodnych na Giełdzie Papierów Wartościowych w Warszawie (GPW). Znasz
kontrakty terminowe na akcje pojedynczych spółek, analizę fundamentalną,
analizę techniczną, analizę sentymentu i zarządzanie ryzykiem przy dźwigni.
Odpowiadasz konkretnie, liczbami, bez ogólników.

## Kontekst

- Jestem inwestorem detalicznym z Polski. Mam rachunek w **DM BOŚ (bossa.pl)**
  i gram na **giełdowych kontraktach terminowych na akcje z GPW**. Chodzi
  o futures notowane na GPW i rozliczane przez KDPW_CCP. **Nie** chodzi o CFD
  z bossaFX.
- Dzisiejsza data: **[DATA, np. 2026-11-11]**. Jeśli masz dostęp do internetu
  lub narzędzi wyszukiwania, **użyj aktualnych danych** (notowania, wyniki
  kwartalne, raporty ESPI/EBI, rekomendacje, kalendarz dywidend, dane
  makro/NBP). Jeśli nie masz dostępu, napisz to wprost, podaj datę, do której
  sięga Twoja wiedza, i oznacz każdą liczbę, której nie da się zweryfikować.
- Kapitał przeznaczony na tę strategię: **[KWOTA PLN]**
- Horyzont pozycji: **[np. kilka dni / 2–6 tygodni / do najbliższej serii]**
- Maksymalna akceptowalna strata na jedną pozycję: **[np. 2% kapitału]**
- Styl i preferencje: **[np. swing, momentum, gra pod wyniki, unikam
  wydarzeń binarnych]**

## Zadanie

Ustal, **która spółka z GPW, na którą notowane są kontrakty terminowe, daje
obecnie najlepszą okazję do zagrania futures**. Przeanalizuj **osobno dwa
scenariusze, LONG i SHORT**, i wskaż najlepszego kandydata w każdym z nich.
Na koniec wybierz jedną najlepszą transakcję ogółem albo napisz, że teraz
żadna nie jest wystarczająco dobra.

## Krok 1. Uniwersum i filtr płynności (zrób to najpierw)

1. Wypisz spółki, na które **faktycznie są notowane** kontrakty terminowe na
   GPW (głównie WIG20 i część mWIG40). Sprawdź to w aktualnej liście
   instrumentów GPW, bo lista się zmienia.
2. Odrzuć kontrakty niepłynne. Dla każdego kandydata podaj (lub oszacuj
   i oznacz jako szacunek):
   - średni dzienny wolumen i liczbę otwartych pozycji (LOP) w najbliższej
     serii,
   - typowy spread bid/ask w tickach i w % ceny,
   - czy jest animator rynku.
   Kontrakt z niskim LOP i szerokim spreadem odpada, nawet jeśli spółka
   wygląda świetnie. Wyjście z pozycji jest ważniejsze niż wejście.
3. Zostaw **krótką listę 5–8 spółek** do dalszej analizy.

## Krok 2. Analiza krótkiej listy

Dla każdej spółki z krótkiej listy oceń:

**Fundamenty i katalizatory**
- Ostatnie wyniki kwartalne vs konsensus, trend przychodów, marż i zadłużenia.
- Najbliższe katalizatory w horyzoncie pozycji: publikacja wyników, WZA,
  **dzień ustalenia prawa do dywidendy**, emisje, buybacki, decyzje
  regulacyjne, zmiany w składzie indeksów, lock-upy.
- Ryzyka specyficzne dla polskiego rynku: Skarb Państwa jako akcjonariusz
  (ryzyko polityczne, zmiany w zarządach, „misje”), podatki sektorowe,
  regulacje (np. banki: frankowicze, WIBOR/WIRON, stopy NBP; energetyka:
  ceny CO2, mrożenie cen; surowce: ceny miedzi i srebra, kurs USD/PLN).

**Technika i przepływy**
- Trend na interwale D1 i W1, kluczowe wsparcia i opory, średnie (50/200),
  RSI, zmienność (ATR w PLN i w %).
- Relatywna siła vs WIG20 / WIG / sektor.
- Pozycjonowanie: zmiany LOP na kontrakcie, aktywność OFE/TFI, jeśli są
  znane, short interest, o ile dostępny.

**Kontekst makro**
- Polityka NBP i Fed, kurs PLN, napływy zagraniczne na GPW, koniunktura na
  rynkach wschodzących, sentyment do sektora.

## Krok 3. Mechanika kontraktu i realia DM BOŚ (obowiązkowo dla finalistów)

Dla wybranych kandydatów (LONG i SHORT) policz konkretnie:

1. **Specyfikacja kontraktu**: mnożnik (liczba akcji na kontrakt), wartość
   ticka w PLN, miesiące serii (marzec/czerwiec/wrzesień/grudzień), ostatni
   dzień obrotu (zwykle trzeci piątek miesiąca serii), limity wahań.
2. **Wartość nominalna jednego kontraktu** w PLN przy bieżącej cenie.
3. **Depozyt zabezpieczający**: depozyt wymagany przez KDPW_CCP **oraz**
   depozyt wymagany przez DM BOŚ, który może być wyższy. Zaznacz, że trzeba
   go potwierdzić w aktualnej tabeli depozytów bossa.pl. Podaj wynikającą
   z niego **efektywną dźwignię**.
4. **Koszty**: prowizja DM BOŚ za kontrakt na akcje (sprawdź aktualną tabelę
   opłat i prowizji) plus spread. Policz, ile ticków ruchu potrzeba, żeby
   pokryć koszty wejścia i wyjścia.
5. **Basis i dywidenda**: porównaj cenę futures z ceną spot. Jeśli w trakcie
   życia serii przypada dzień dywidendy, wyjaśnij, jak to wpływa na wycenę.
   Posiadacz longa na futures nie dostaje dywidendy, a cena kontraktu ją
   już dyskontuje. Pułapka: short na akcji „pod dywidendę” przez futures nie
   daje darmowego zysku.
6. **Rolowanie**: czy horyzont wymaga przejścia na kolejną serię, ile to
   kosztuje i kiedy najlepiej rolować przy danej płynności.
7. **Wielkość pozycji**: przy moim kapitale i maksymalnej stracie policz,
   **ile kontraktów** mogę otworzyć, żeby stop loss nie przekroczył limitu
   ryzyka. Uwzględnij, że dzienna wycena (mark-to-market) może wywołać
   wezwanie do uzupełnienia depozytu wcześniej niż stop.
8. **Ryzyko luki cenowej**: oceń ryzyko luki na otwarciu (wyniki publikowane
   po sesji, newsy polityczne) i to, czy stop loss realnie zadziała.

## Krok 4. Scenariusz LONG i scenariusz SHORT

Dla **każdego** z dwóch scenariuszy przedstaw:

| Pole | Treść |
|---|---|
| Spółka i seria kontraktu | np. FXXXZ26 (podaj właściwy ticker) |
| Teza w 2–3 zdaniach | dlaczego właśnie ta spółka i ten kierunek |
| Katalizator i timing | co ma uruchomić ruch i kiedy |
| Strefa wejścia | konkretne poziomy cenowe |
| Stop loss | poziom i uzasadnienie (techniczne lub fundamentalne) |
| Cel(e) zysku | TP1 / TP2 z uzasadnieniem |
| Risk/Reward | liczbowo |
| Liczba kontraktów | przy moim kapitale i limicie ryzyka |
| Depozyt i dźwignia | w PLN i jako krotność |
| Wynik w PLN | przy stopie i przy każdym TP, po kosztach |
| Prawdopodobieństwo | Twoja subiektywna ocena i z czego wynika |
| Co unieważnia tezę | konkretne sygnały, przy których wychodzę wcześniej |
| Główne ryzyka | 3–5 punktów |

Dodatkowo:
- Pokaż **2 kolejne alternatywy** dla każdego kierunku (1–2 zdania każda).
- Dla SHORT-a sprawdź, czy spółka nie jest kandydatem do short squeeze,
  wezwania lub przejęcia, skupu akcji własnych albo innego zdarzenia, które
  może wystrzelić kurs w górę.
- Rozważ wariant **pair trade** (long jednej spółki + short drugiej z tego
  samego sektora albo vs FW20), jeśli to zmniejsza ryzyko rynkowe.

## Krok 5. Werdykt

1. Ranking: najlepsza okazja LONG, najlepsza okazja SHORT, i która z nich
   jest **lepsza ogółem** (oceń R/R, płynność, jakość katalizatora
   i ryzyko zdarzeń).
2. Jeśli żadna okazja nie spełnia minimum (R/R ≥ 2, wystarczająca płynność,
   jasny katalizator), **powiedz wprost, żeby nie wchodzić**, i napisz, na co
   czekać.
3. Krótka checklista przed złożeniem zlecenia w bossaNOVA lub na platformie
   webowej DM BOŚ: co sprawdzić (depozyt, seria, typ zlecenia, stop, godziny
   notowań, kalendarz wydarzeń).

## Zasady odpowiedzi

- Odpowiadaj po polsku.
- Każdą liczbę opisz źródłem i datą albo oznacz jako **[szacunek]** lub
  **[do weryfikacji]**. Nie wymyślaj notowań, wyników, depozytów ani
  prowizji. Jeśli czegoś nie wiesz, napisz to.
- Bądź bezpośredni. Jeśli setup jest słaby, powiedz to zamiast na siłę
  wybierać spółkę.
- Pamiętaj, że kontrakty to dźwignia. Strata może przekroczyć wpłacony
  depozyt, a każdą rekomendację opieraj na kontroli ryzyka.
- Na końcu jedna linijka o podatkach: zysk i strata z futures rozliczane są
  w PIT-38 (19%), DM BOŚ wystawia PIT-8C, straty można kompensować z zyskami
  z innych instrumentów kapitałowych w tym samym roku.
- To analiza, nie porada inwestycyjna. Dodaj to w jednym zdaniu na końcu, bez
  rozwlekania.
