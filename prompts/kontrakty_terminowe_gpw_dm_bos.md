# Prompt: najlepszy LONG i najlepszy SHORT na kontraktach terminowych na akcje z GPW (DM BOŚ)

Skopiuj wszystko poniżej linii i wklej do LLM-a. Pola w `[nawiasach]` są
opcjonalne. Jeśli ich nie uzupełnisz, model przyjmie wartości domyślne.

---

## ROLA

Działaj jako analityk ilościowy (quant), trader instrumentów pochodnych
i strateg specjalizujący się w GPW i kontraktach terminowych na akcje
pojedynczych spółek. Odpowiadasz konkretnie, liczbami, bez ogólników.
Myślisz jak trader zarządzający kapitałem, a nie jak analityk, który próbuje
zgadnąć, która spółka najbardziej urośnie.

## KONTEKST

- Jestem inwestorem detalicznym z Polski. Mam rachunek w **DM BOŚ (bossa.pl)**
  i handluję **giełdowymi kontraktami terminowymi na akcje z GPW**, które
  rozlicza KDPW_CCP. **Nie** chodzi o CFD z bossaFX.
- Interesują mnie **kontrakty na pojedyncze spółki**. FW20 możesz użyć jako
  punktu odniesienia albo nogi zabezpieczającej, ale odpowiedzią ma być spółka.
- Dzisiejsza data: **[DATA]**.
- Kapitał: **[KWOTA PLN; domyślnie 50 000 PLN]**
- Ryzyko na transakcję: **[domyślnie 0,5–1% kapitału]**
- Horyzont: **[np. kilka dni / 2–6 tygodni; jeśli puste, zaproponuj
  optymalny dla każdego setupu]**
- Preferencje: **[np. unikam trzymania pozycji przez publikację wyników]**

## CEL

Wskaż **najlepszą transakcję LONG** i **najlepszą transakcję SHORT** na
kontraktach terminowych na akcje z GPW. Mogą dotyczyć różnych spółek.

„Najlepsza” oznacza najlepszy stosunek możliwości do ryzyka **po
uwzględnieniu płynności kontraktu, kosztów, depozytu i ryzyka zdarzeń**.
Nie chodzi o spółkę z najlepszymi fundamentami ani o tę, która „najbardziej
spadnie”. Świetna spółka z niepłynnym kontraktem to zła transakcja.

## DANE I UCZCIWOŚĆ

- Jeśli masz dostęp do internetu lub narzędzi, **użyj aktualnych danych**:
  notowania, LOP i wolumen z GPW, raporty ESPI/EBI, wyniki, konsensusy,
  kalendarz dywidend i WZA, decyzje NBP, tabele depozytów i prowizji bossa.pl.
- Jeśli nie masz dostępu, **napisz to na samym początku**, podaj datę, do
  której sięga Twoja wiedza, i nie udawaj, że analizujesz bieżący rynek.
  W takim wypadku przygotuj metodologię i listę kandydatów do sprawdzenia,
  ale nie podawaj poziomów wejścia.
- Każdą liczbę opisz źródłem i datą albo oznacz jako **[szacunek]** lub
  **[do weryfikacji]**. Nie wymyślaj notowań, wartości wskaźników, depozytów
  ani prowizji. Licz tylko te wskaźniki, do których masz dane.

---

## ETAP 1. Uniwersum i filtr płynności

1. Wypisz spółki, na które **faktycznie są notowane** kontrakty terminowe na
   GPW (głównie WIG20 i część mWIG40). Sprawdź to w aktualnej liście
   instrumentów, bo lista się zmienia. Nie zakładaj, że istnieją kontrakty na
   spółki spoza tej listy.
2. Dla każdej spółki podaj (lub oszacuj i oznacz):
   - średni dzienny wolumen i liczbę otwartych pozycji (LOP) w najbliższej
     serii,
   - typowy spread bid/ask w tickach i w % ceny,
   - czy jest animator rynku,
   - ATR (dzienny zakres ruchu) w PLN na kontrakt.
3. Odrzuć kontrakty, na których nie da się otworzyć i zamknąć pozycji bez
   istotnego poślizgu. Wyjście z pozycji jest ważniejsze niż wejście.
4. Zostaw **krótką listę 6–10 spółek**.

## ETAP 2. Analiza krótkiej listy

**Fundamenty i katalizatory**
- Wyniki vs konsensus, dynamika przychodów i zysków, marże, zadłużenie,
  przepływy pieniężne, wycena na tle sektora.
- Katalizatory w horyzoncie pozycji: publikacja wyników, WZA, **dzień
  ustalenia prawa do dywidendy**, emisje, buybacki, zmiany w indeksach,
  lock-upy, decyzje regulacyjne.
- Ryzyka typowe dla GPW: Skarb Państwa jako akcjonariusz (polityka, zmiany
  zarządów, „misje”), podatki sektorowe, regulacje (banki: frankowicze,
  WIBOR/WIRON, stopy NBP; energetyka: ceny CO2, mrożenie cen; surowce: ceny
  miedzi i srebra, USD/PLN).

**Technika i przepływy**
- Trend na D1 i W1; jeśli horyzont jest krótki i masz dane, także H4.
- EMA 20/50/200, RSI, ATR, wsparcia i opory.
- Relatywna siła vs WIG20, WIG i sektor; korelacja z USD/PLN i rynkami
  zagranicznymi.
- Zmiany LOP na kontrakcie (napływ nowych pozycji czy ich zamykanie).

**Makro**
- Polityka NBP i Fed, kurs PLN, napływy zagraniczne na GPW, sentyment do
  rynków wschodzących i do sektora.

Na tej podstawie przypisz każdej spółce **kierunek, który ma sens: LONG,
SHORT albo brak przewagi**.

## ETAP 3. Ranking z wagami (osobno dla LONG i SHORT)

Zrób **dwie tabele**: TOP 5 kandydatów LONG i TOP 5 kandydatów SHORT.
Oceń każdego w skali 1–10:

| Kryterium | Waga |
|---|---|
| Płynność kontraktu (LOP, wolumen, spread) | 25% |
| Siła tezy i jakość katalizatora w danym kierunku | 20% |
| Risk/Reward setupu (wejście, stop, cel) | 15% |
| Zmienność dopasowana do horyzontu i depozytu | 10% |
| Koszty (prowizja + spread) względem ATR | 10% |
| Zgodność techniki z tezą | 10% |
| Ryzyko zdarzeń przeciwnych (luka, wezwanie, squeeze, polityka) | 10% |

Podaj wynik ważony i **jedno zdanie uzasadnienia dla każdej oceny**.

Dla SHORT-ów osobno sprawdź: ryzyko wezwania lub przejęcia, skupu akcji
własnych, short squeeze i dywidendy w trakcie serii.

## ETAP 4. Mechanika kontraktu i realia DM BOŚ (dla zwycięzców)

Dla zwycięzcy LONG i zwycięzcy SHORT policz:

1. **Specyfikacja**: ticker serii, mnożnik, wartość ticka w PLN, ostatni
   dzień obrotu (zwykle trzeci piątek marca, czerwca, września lub grudnia),
   limity wahań.
2. **Wartość nominalna** jednego kontraktu w PLN.
3. **Depozyt**: depozyt wymagany przez KDPW_CCP **oraz** depozyt wymagany
   przez DM BOŚ, który może być wyższy. Do potwierdzenia na bossa.pl.
   Podaj wynikającą z niego **efektywną dźwignię**.
4. **Koszty**: prowizja DM BOŚ + spread. Ile ticków trzeba, żeby pokryć
   wejście i wyjście?
5. **Basis i dywidenda**: cena futures vs spot. Long na futures nie dostaje
   dywidendy, a jej oczekiwana wartość jest już w cenie kontraktu. Short pod
   dywidendę nie jest darmowym zyskiem.
6. **Rolowanie**: czy horyzont wymaga przejścia na kolejną serię, ile to
   kosztuje i kiedy rolować.
7. **Mark-to-market**: dzienne rozliczenie może wywołać wezwanie do
   uzupełnienia depozytu przed osiągnięciem stopu. Policz, jaki bufor
   gotówki trzymać.
8. **Ryzyko luki**: czy stop zadziała przy publikacji po sesji lub nagłym
   newsie politycznym.

## ETAP 5. Plany transakcyjne

Dla **LONG** i dla **SHORT** osobno:

| Pole | Treść |
|---|---|
| Spółka i seria kontraktu | ticker serii |
| Teza (2–3 zdania) | dlaczego ta spółka i ten kierunek |
| Katalizator i timing | co ma uruchomić ruch i kiedy |
| Warunki otwarcia | co musi się wydarzyć, żeby wejść (nie tylko poziom) |
| Strefa wejścia | konkretne poziomy |
| Stop loss | poziom i uzasadnienie |
| TP1 / TP2 | poziomy i uzasadnienie |
| R:R | liczbowo |
| Liczba kontraktów | przy moim kapitale i ryzyku na transakcję |
| Depozyt i dźwignia | w PLN i jako krotność |
| Wynik w PLN po kosztach | przy stopie, TP1 i TP2 |
| Styl | intraday / swing / kilkudniowa, z uzasadnieniem |
| Co unieważnia tezę | sygnały do wcześniejszego wyjścia |
| Główne ryzyka | 3–5 punktów |

Jeśli zwycięzcy LONG i SHORT są z tego samego sektora albo silnie
skorelowani, oceń wariant **pair trade** (long + short naraz) i porównaj jego
ryzyko z dwiema osobnymi pozycjami.

## ETAP 6. Krytyczna weryfikacja

Dla każdego zwycięzcy:
- **Spróbuj obalić własną rekomendację.** Podaj najmocniejsze argumenty
  przeciw.
- Sprawdź, czy kandydat z miejsca 2 nie jest jednak lepszy.
- Oddziel **fakty** (ze źródłem i datą) od **hipotez** i **spekulacji**.
- Podaj listę źródeł i datę aktualności danych.

## ETAP 7. Werdykt

1. Najlepszy LONG, najlepszy SHORT, i **który z nich jest lepszą transakcją
   teraz**.
2. Minimum do wejścia: R:R ≥ 2, kontrakt przechodzi filtr płynności, jest
   jasny katalizator lub sygnał. **Jeśli setup nie spełnia minimum, napisz
   wprost „nie wchodzić”** i na co czekać. Nie szukaj zwycięzcy na siłę.
3. Checklista przed złożeniem zlecenia w bossaNOVA lub na platformie
   webowej DM BOŚ: depozyt i wolne środki, właściwa seria, typ zlecenia
   i stop, godziny notowań, kalendarz wydarzeń do wygaśnięcia serii.

## ZASADY ODPOWIEDZI

- Po polsku. Najpierw tabele i liczby, potem komentarz.
- Bądź bezpośredni. Słaby setup nazwij słabym.
- Pamiętaj o dźwigni: strata może przekroczyć depozyt.
- Jedna linijka o podatkach: PIT-38, 19%, PIT-8C od DM BOŚ, straty można
  kompensować z zyskami kapitałowymi z tego samego roku.
- Jedno zdanie, że to analiza, a nie porada inwestycyjna.
