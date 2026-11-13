# Najlepszy LONG i najlepszy SHORT na kontraktach na akcje z GPW (DM BOŚ)

**Analiza z piątku 13.11.2026, dane do ok. 10:45 CET.** Wykonanie promptu
`prompts/kontrakty_terminowe_gpw_dm_bos.md` (gałąź `claude/futures-gielda-prompt-f3obi8`).

**Dostęp do danych.** Analiza opiera się na bieżących danych z internetu:

- **Notowania, LOP i obroty:** biznesradar.pl (opóźnienie 15 min). Ostatni odczyt pobrano o 10:59, obejmuje transakcje do 10:44.
- **Depozyty:** plik SPAN KDPW_CCP `RPNJE_ZRS.xml` (utworzony 12.11.2026 o 18:28).
- **Prowizje i zasady depozytów:** bossa.pl (13.11.2026) i wyciąg z zarządzeń DM BOŚ (stan na 14.10.2026).
- **Wyniki i wydarzenia:** komunikaty spółek i serwisy finansowe (źródła na końcu).

Ograniczenia:

- Nie miałem arkusza zleceń, więc spread szacuję z transakcji **[szacunek]**.
- Nie miałem historii LOP, więc zmianę LOP oceniam tylko punktowo.
- Strony gpw.pl i stooq.pl były niedostępne. Listy animatorów i limitów wahań nie potwierdziłem **[do weryfikacji]**.

**Parametry (domyślne z promptu):**

- kapitał 50 000 zł;
- ryzyko 0,5–1% na transakcję, czyli 250–500 zł;
- horyzont dobrany do setupu;
- brak preferencji co do trzymania pozycji przez publikację wyników.

Skróty używane w tekście:

- **BR** – biznesradar.pl;
- **KDPW** – plik SPAN z 12.11;
- **obl.** – moje obliczenia na danych BR;
- **RT** – koszt wejścia i wyjścia (round trip).

---

## Werdykt w liczbach

| | LONG | SHORT |
|---|---|---|
| Zwycięzca | **Allegro, FALEZ26** (wynik 8,20/10) | **Orlen, FPKNZ26** (wynik 7,60/10) |
| Kurs teraz (BR, 10:44) | 65,71 (+2,2%), nowe 5-letnie maksimum | 134,65 (+0,8%), trzecia sesja odbicia |
| Decyzja | Zlecenia z limitem: 1 szt. po 65,00 i 1 szt. po 64,20. **Nie kupować po rynku** (R:R 1,45). | **Na razie nie wchodzić.** Short dopiero w strefie 137,5–139,5 (limit 138,50). |
| Stop | 62,40 | 142,60 |
| TP1 / TP2 | 68,00 / 70,50 | 130,20 / 125,80 |
| R:R | 2,1 dla drabinki; 3,5, jeśli wejdzie tylko zlecenie 64,20 | 2,0 do TP1, 3,1 do TP2 |
| Strata przy stopie (po kosztach) | −462 zł (0,92% kapitału) przy 2 szt. | −421 zł (0,84%) przy 1 szt. |
| Depozyt SPAN (= DM BOŚ) | około 1 000 zł/szt. (15,5%), dźwignia 6,5x | około 1 220 zł/szt. (8,8%), dźwignia 11,4x |
| Lepsza transakcja teraz? | **Tak.** Trend, katalizator i rynek są po tej samej stronie. | Słabsza. Najpierw kurs musi wzrosnąć o 2–4%. |

---

## Etap 1. Uniwersum i filtr płynności

Na GPW notowane są serie grudniowe (Z26) kontraktów na 46 spółek (BR i KDPW, 13.11). Poniżej 20 serii z największym obrotem.

**Kryteria filtra:**

- średni obrót co najmniej ~1,5 mln zł dziennie albo co najmniej 250 szt. dziennie;
- LOP co najmniej 1 000;
- brak dni bez obrotu w ostatnich 20 sesjach;
- spread efektywny najwyżej ~0,2%.

| Kontrakt | Mnożnik | Kurs 10:44 | LOP | Śr. wolumen 20 sesji (szt.) | Śr. obrót 20 sesji (mln zł) | Spread efektywny [szacunek] | ATR(14) na kontrakt (zł) | Depozyt SPAN (zł) | Filtr |
|---|---:|---:|---:|---:|---:|---|---:|---:|---|
| FKGHZ26 | 100 | 284,00 | 2 171 | 1 097 | 32,7 | 0,04–0,08% (10–22 zł) | 1 197 | 3 374 | ✅ (ale ATR na kontrakt bardzo duży) |
| FPKNZ26 | 100 | 134,65 | 3 197 | 640 | 9,2 | ~0,06% (~8 zł) | 474 | 1 176 | ✅ |
| FCDRZ26 | 100 | 277,76 | 7 764 | 229 | 6,1 | 0,08–0,10% (23–28 zł) | 764 | 3 557 | ✅ (duży ATR na kontrakt) |
| FPKOZ26 | 100 | 118,99 | 6 766 | 490 | 5,6 | 0,05–0,10% (6–12 zł) | 299 | 1 038 | ✅ |
| FMDVZ26 | 100 | 116,00 | 8 691 | 384 | 3,9 | 0,03–0,15% (4–17 zł) | 475 | 1 869 | ✅ |
| FPGEZ26 | 1000 | 16,45 | 786 | 186 | 3,1 | ~0,12% (~20 zł) | 616 | 2 006 | ⚠️ rezerwa (LOP < 1 000) |
| FTPEZ26 | 1000 | 9,48 | 2 113 | 286 | 2,7 | 0,11–0,19% (10–18 zł) | 286 | 1 060 | ✅ |
| FCPSZ26 | 100 | 13,24 | 17 219 | 1 563 | 2,3 | 0,11–0,15% (1–2 zł) | 73 | 124 | ✅ (mały nominał) |
| FOPLZ26 | 1000 | 16,68 | 1 009 | 129 | 2,1 | 0,18–0,29% (30–48 zł) | 557 | 1 398 | ❌ spread, mediana 68 szt./d |
| FALEZ26 | 100 | 65,71 | 23 540 | 323 | 1,9 | 0,09–0,12% (6–8 zł) | 173 | 996 | ✅ |
| FASBZ26 | 100 | 164,30 | 643 | 102 | 1,6 | ~0,30% (~50 zł) | 1 080 | 2 217 | ❌ spread, LOP |
| FXTBZ26 | 100 | 138,80 | 1 054 | 115 | 1,6 | ~0,23% (~31 zł) | 531 | 2 090 | ❌ 100 transakcji zajęło 4 dni |
| FPEOZ26 | 100 | 268,90 | 2 410 | 49 | 1,3 | 0,21–0,30% (56–80 zł) | 743 | 2 531 | ❌ około 50 szt./d |
| FDNPZ26 | 100 | 37,80 | 17 777 | 258 | 1,0 | 0,16–0,22% (6–8 zł) | 118 | 538 | ✅ (na granicy przez spread) |
| FLPPZ26 | 1 | 28 920 | 311 | 33 | 0,9 | 0,13–0,23% (36–66 zł) | 710 | 3 771 | ❌ LOP |
| FPZUZ26 | 100 | 75,75 | 743 | 119 | 0,9 | ~0,06% (~5 zł) | 129 | 560 | ⚠️ LOP, mała zmienność |
| FJSWZ26 | 100 | 27,33 | 4 354 | 305 | 0,9 | 0,06–0,11% (2–3 zł) | 118 | 440 | ✅ |
| FMBKZ26 | 10 | 1 744,50 | 559 | 52 | 0,8 | 0,13–0,20% (23–34 zł) | 570 | 2 080 | ❌ LOP, dni bez obrotu |
| FPCOZ26 | 100 | 49,53 | 681 | 124 | 0,6 | 0,13–0,35% (6–17 zł) | 153 | 764 | ❌ LOP, spread |
| FKTYZ26 | 10 | 1 339,00 | 1 245 | 42 | 0,5 | ~0,19% (~25 zł) | 339 | 1 152 | ❌ mediana 26 szt./d |

Skąd te liczby:

- **Mnożnik:** z obrotu i wolumenu, potwierdzony polem `cvf` w pliku KDPW.
- **ATR:** liczony na akcji i pomnożony przez mnożnik (obl.).
- **Spread:** estymator Rolla oraz mediana skoków ceny z ostatnich 100 transakcji (BR, 12–13.11) [szacunek].
- **Pozostałe 26 serii:** obrót poniżej 0,5 mln zł dziennie, odrzucone bez analizy.

**Animator rynku.** GPW prowadzi program „SuperAnimator KONTRAKTY AKCYJNE”, przedłużony uchwałą 471/2026 z 26.03.2026. Listy animatorów dla poszczególnych serii nie potwierdziłem **[do weryfikacji na gpw.pl]**. Na FALE, FPKN, FPKO i FKGH transakcje płyną ciągle przy spreadzie ~0,05–0,1%, co pośrednio wskazuje na aktywne kwotowania.

**Krótka lista (10 spółek):**

- kandydaci LONG: ALE, MDV, CDR, PKO, TPE;
- kandydaci SHORT: PKN, KGH, CPS, JSW, DNP;
- rezerwa: PGE.

---

## Etap 2. Analiza krótkiej listy

### Technika (akcje, zamknięcie 12.11, obl. na danych BR)

| Spółka | Kurs | vs EMA20 | vs EMA50 | vs EMA200 | RSI(14) | ATR% | 1M | 3M | RS vs WIG20 1M | RS vs WIG20 3M | Beta 60d | Od szczytu 52t | Trend W1 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| ALE | 64,00 | +9,2% | +18,3% | +47,8% | 78 | 2,7% | +20,1% | +37,8% | +18,5% | +29,8% | 0,86 | −1,0% | wzrost |
| MDV | 113,45 | +13,1% | +18,5% | +15,4% | 72 | 4,2% | +22,0% | +22,4% | +20,4% | +15,3% | 1,12 | −20,6% | wzrost |
| CDR | 278,20 | +4,8% | +7,7% | +11,8% | 65 | 2,7% | +4,6% | +5,7% | +3,3% | −0,4% | 0,85 | −6,3% | wzrost |
| PKO | 117,90 | +1,8% | +1,9% | +11,6% | 54 | 2,5% | +1,1% | +6,1% | −0,2% | 0,0% | 1,27 | −6,1% | mieszany |
| TPE | 9,35 | +2,2% | +2,1% | −0,8% | 55 | 3,1% | −4,5% | +5,2% | −5,7% | −0,9% | 1,15 | −21,6% | mieszany |
| PKN | 132,34 | −7,0% | −10,1% | −4,3% | 34 | 3,6% | −14,1% | −13,0% | −15,2% | −18,1% | 0,55 | −19,4% | mieszany |
| KGH | 284,30 | −4,4% | −9,7% | −8,7% | 40 | 4,2% | −17,5% | −19,3% | −18,6% | −24,0% | 1,56 | −28,3% | mieszany |
| CPS | 13,17 | −9,5% | −15,5% | −12,9% | 35 | 5,6% | −25,6% | −23,7% | −26,5% | −28,2% | 1,24 | −29,0% | mieszany |
| JSW | 26,90 | −5,2% | −10,4% | −7,0% | 35 | 4,4% | −18,5% | −4,9% | −19,5% | −10,4% | 0,67 | −32,6% | mieszany |
| DNP | 37,82 | −0,2% | +3,3% | +6,6% | 51 | 3,1% | +3,6% | +16,7% | +2,3% | +9,9% | 0,54 | −11,4% | wzrost |

WIG20 na zamknięciu 12.11: 4 279,5 pkt, RSI 58. Indeks był o 0,3% poniżej rekordu 4 291 pkt, powyżej EMA50 (4 148) i EMA200 (3 807). Danych H4 i szeregu USD/PLN nie miałem, więc ich nie liczyłem.

### Fundamenty, katalizatory i kierunek

| Spółka | Fakty (źródło, data) | Kierunek |
|---|---|---|
| **ALE** | III kw. (Allegro, 12.11): GMV grupy +17,8% r/r, GMV w Polsce +14,7% (najszybciej od 2022), skorygowana EBITDA +22,9%, zysk netto 574,7 mln zł. Pierwsze tygodnie IV kw.: GMV w Polsce +16%. Prognoza na 2026 podniesiona: GMV grupy +15–16%, skorygowana EBITDA grupy +22–24%. Walne 18.11: podniesienie limitu ceny skupu z 50 do 65 zł; program to 1,6 mld zł, w fazie II zostaje około 800 mln zł. Wycena: C/Z 27,4, EV/EBITDA 13,5 (branża 15,0) (BR). Następny raport okresowy dopiero w 2027. | **LONG** |
| **MDV** | Szacunki III kw. (6.11): przychody około 3,2 mld zł (+11%), skorygowana EBITDA około 450 mln zł, wzrost kursu do najwyższego poziomu od miesięcy. Spółka mocno shortowana (rejestr KNF), krótkie pozycje maleją (Parkiet, 9.11). Pełny raport 27.11. EV/EBITDA około 18 przy branży około 7 (BR), zapasy około 5 mld zł. | LONG (słabszy) |
| **CDR** | Brak nowego katalizatora poza raportem III kw. 24.11. C/Z około 33 (BR). | LONG, ale ATR na kontrakt za duży |
| **PKO** | III kw. (5.11): zysk netto 2 933 mln zł (+3,4% r/r), 4,1% powyżej konsensusu. RPP (4.11): stopy bez zmian (referencyjna 3,75%), a projekcja NBP pokazuje gorsze perspektywy inflacji, więc stopy dłużej zostaną wysokie. C/WK 2,58 (branża 2,19). | LONG (umiarkowany) |
| **TPE** | Szacunki III kw. (2.11): EBITDA 1 821 mln zł przy konsensusie 1 565 mln. Pełny raport 18.11. Rekomendacje „trzymaj” i „redukuj” z celami 9,0–9,2 zł (BOŚ, Noble). | Brak przewagi |
| **PKN** | III kw. (5.11): EBITDA LIFO 14,7 mld zł przy konsensusie 15,2–15,3 mld, zysk netto 5,6 mld zł przy konsensusie 7,3 mld, odpisy około 1,6 mld zł. Projekt 10-procentowej daniny od przychodów netto największych importerów gazu, z której rząd chce sfinansować maksymalną cenę gazu w 2027; Orlen ma być największym płatnikiem (Parkiet, 10.11) [kwota i etap legislacyjny do weryfikacji]. Litewski windfall tax uderzy głównie w Orlen Lietuva (12.11). Na plus: wypowiedzenie drogiej umowy LNG z QatarEnergy (10.11), EV/EBITDA 4,3, C/WK 1,15 (BR), dywidenda 8 zł wypłacona w czerwcu. Kapitalizacja spadła o 44 mld zł od szczytu (bankier.pl, 9.11). | **SHORT** |
| **KGH** | Miedź na LME spadła 3.11 do 13 883 USD/t, a zapasy LME wzrosły do 312 tys. t, najwyżej od 4 miesięcy (Mysteel). Raport III kw. 18.11. W II kw. zysk netto 2,05 mld zł. C/Z 7,6 (BR). | SHORT, ale kontrakt za duży |
| **CPS** | Strategia z końca października: EBITDA segmentu TMT ma spadać o 2–3% rocznie do 2029, dywidenda najwcześniej około 2030, dług netto do EBITDA 3,6x (cel poniżej 2,5x w 2030). Od 4.11 spółka analizuje refinansowanie ponad 12 mld zł i 506 mln EUR długu. Raport III kw. 18.11. C/WK 0,70 (BR). | SHORT (słabszy) |
| **JSW** | Strata netto w II kw. 428 mln zł (BR). Umowa pożyczki z ARP do 1,066 mld zł (9.11), nowy p.o. prezesa (3.11). Raport III kw. 24.11. | SHORT (ryzyko squeeze) |
| **DNP** | III kw. (6.11): przychody +10,8%, EBIT −0,3% r/r, zysk netto +0,2%, czyli presja na marże. Kurs spadł o 6,1% w dniu wyników, potem stoi w miejscu. C/Z 22 (BR). | Brak przewagi |

**Makro:**

- **RPP i NBP (4.11):** stopy bez zmian. Projekcja NBP jest jastrzębia, a podwyżki są możliwe w 2027. To wspiera banki i szkodzi spółkom zadłużonym (CPS).
- **Fed:** posiedzenie 8–9.12. Nastroje są jastrzębie (spadki na Wall Street 10.11). Wycenę podwyżki w grudniu oznaczam jako **[do weryfikacji]**.
- **USA:** w wyborach połówkowych 3.11 Demokraci zdobyli obie izby, a rynki odreagowały 4.11.
- **Ryzyka z USA:** Nvidia straciła ponad 7% 12.11 (wg analizy z 12.11), a 6.11 była wyprzedaż spółek technologicznych (Mysteel).
- **PLN:** kontrakty FUSDZ26 3,98 i FEURZ26 4,41 (BR, 13.11) wskazują na stabilnego złotego.
- **GPW:** 12.11 Warszawa była najsilniejszym rynkiem w Europie (bankier.pl).

**LOP:**

- FALEZ26 spadł 12.11 z 23 852 do 23 524 szt., czyli część wzrostu to zamykanie shortów (dane z analizy z 12.11). Dziś LOP wzrósł o 16 szt.
- FPKNZ26: 3 196 rano i 3 197 o 10:44, bez zmian.
- Dla pozostałych serii nie miałem historii LOP.

---

## Etap 3. Ranking z wagami

Wagi kryteriów: płynność 25%, teza i katalizator 20%, R:R 15%, zmienność 10%, koszty 10%, technika 10%, ryzyko zdarzeń 10%. Skala 1–10. W kryterium ryzyka zdarzeń wyższa ocena oznacza mniejsze ryzyko.

### TOP 5 LONG

| # | Kontrakt | Płynność | Teza | R:R | Zmienność | Koszty | Technika | Ryzyko zdarzeń | **Wynik** |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | **FALEZ26** | 9 | 9 | 7 | 9 | 7 | 8 | 7 | **8,20** |
| 2 | FPKOZ26 | 9 | 6 | 6 | 8 | 8 | 6 | 6 | 7,15 |
| 3 | FMDVZ26 | 8 | 6 | 6 | 6 | 9 | 7 | 5 | 6,80 |
| 4 | FCDRZ26 | 8 | 5 | 4 | 3 | 8 | 7 | 6 | 6,00 |
| 5 | FTPEZ26 | 7 | 5 | 4 | 7 | 7 | 5 | 6 | 5,85 |

**ALE (FALEZ26)**

- **Płynność 9.** Największy LOP wśród kontraktów na akcje (23,5 tys.), około 320 szt. dziennie i spread około 0,1%.
- **Teza 9.** Świeży katalizator: wyniki III kw. powyżej oczekiwań, podniesiona prognoza, GMV w IV kw. +16% w Polsce, a od 18.11 skup z nowym limitem 65 zł.
- **R:R 7.** Z limitu 64,2–65,0 R:R wynosi 2,1–3,5, ale po cenie rynkowej tylko 1,45.
- **Zmienność 9.** ATR to około 173 zł na kontrakt, więc dwa kontrakty mieszczą się w 0,9% ryzyka.
- **Koszty 7.** Prowizja 6 zł i spread około 7 zł, razem około 7,5% ATR.
- **Technika 8.** Trend wzrostowy na D1 i W1, 5-letnie maksimum, przewaga nad WIG20 +18,5% w miesiąc. Jednocześnie RSI 78 oznacza wykupienie.
- **Ryzyko zdarzeń 7.** Do lutego nie ma wyników, a dawne fundusze private equity nie mają już powyżej 5% akcji. Główne ryzyko to korekta rynku.

**PKO (FPKOZ26)**

- **Płynność 9.** LOP 6,8 tys., 5,6 mln zł obrotu dziennie, spread 0,05–0,1%.
- **Teza 6.** Wyniki powyżej konsensusu i jastrzębia RPP, ale katalizator minął 5.11.
- **R:R 6.** Wybicie z konsolidacji 109–118,6. Wejście z 118,3, stop 115,4 i cel 125,5 dają około 2,5R.
- **Zmienność 8.** ATR około 300 zł; jeden kontrakt to około 0,6% ryzyka.
- **Koszty 8.** Około 5% ATR.
- **Technika 6.** Kurs nad EMA20, EMA50 i EMA200, ale tygodniowy trend jest boczny, a RSI 54 jest neutralny.
- **Ryzyko zdarzeń 6.** Beta 1,27 przy WIG20 pod rekordem, do tego ryzyka regulacyjne sektora.

**MDV (FMDVZ26)**

- **Płynność 8.** LOP 8,7 tys., 3,9 mln zł obrotu dziennie.
- **Teza 6.** Dobre szacunki i zamykanie krótkich pozycji, ale drogo (EV/EBITDA około 18), a zapasy wynoszą około 5 mld zł.
- **R:R 6.** Po wzroście o 25% w 6 sesji wejść można dopiero na korekcie do 110–112; stop około 106, cel 125–128, czyli około 2R.
- **Zmienność 6.** ATR około 475 zł; jeden kontrakt przy stopie 1 ATR to blisko 1% ryzyka.
- **Koszty 9.** Około 3,4% ATR.
- **Technika 7.** Kurs nad wszystkimi EMA, RSI 72.
- **Ryzyko zdarzeń 5.** Raport 27.11, a w ciągu roku kurs wahał się od 71,6 do 142,8 zł.

**CDR (FCDRZ26)**

- **Płynność 8.** 6,1 mln zł obrotu dziennie, spread 23–28 zł.
- **Teza 5.** Brak twardego katalizatora poza raportem 24.11.
- **R:R 4.** Stop pod 266 to około 1 200 zł na kontrakt przy celu 297, czyli około 1,6R.
- **Zmienność 3.** ATR około 760 zł; jeden kontrakt przy stopie 1,5 ATR to ponad 2% kapitału.
- **Koszty 8.** Około 4% ATR.
- **Technika 7.** Trend wzrostowy, opory 280,8 i 297.
- **Ryzyko zdarzeń 6.** Raport 24.11 i newsy branżowe działają w obie strony.

**TPE (FTPEZ26)**

- **Płynność 7.** 2,7 mln zł obrotu dziennie, spread do 0,19%.
- **Teza 5.** Zaskoczenie wynikami jest już znane, a nad sektorem wisi ryzyko polityczne.
- **R:R 4.** Opór 9,78–9,85 jest blisko, R:R około 1,5.
- **Zmienność 7.** ATR około 290 zł.
- **Koszty 7.** Około 7% ATR.
- **Technika 5.** Kurs przy EMA200, RSI 55.
- **Ryzyko zdarzeń 6.** Raport 18.11.

### TOP 5 SHORT

| # | Kontrakt | Płynność | Teza | R:R | Zmienność | Koszty | Technika | Ryzyko zdarzeń | **Wynik** |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | **FPKNZ26** | 9 | 7 | 7 | 7 | 9 | 7 | 6 | **7,60** |
| 2 | FKGHZ26 | 10 | 5 | 5 | 2 | 10 | 7 | 5 | 6,65 |
| 3 | FCPSZ26 | 7 | 6 | 5 | 8 | 5 | 6 | 4 | 6,00 |
| 4 | FJSWZ26 | 6 | 5 | 6 | 8 | 7 | 6 | 4 | 5,90 |
| 5 | FDNPZ26 | 6 | 4 | 5 | 8 | 4 | 3 | 7 | 5,25 |

**PKN (FPKNZ26)**

- **Płynność 9.** 9,2 mln zł obrotu dziennie, około 640 szt., spread około 0,06%.
- **Teza 7.** Wyniki poniżej konsensusu, odpisy, projekt daniny od importerów gazu i podatek na Litwie.
- **R:R 7.** Wejście z 138,5 (luka 130,1–140,7, EMA20 142,3) ze stopem 142,6 daje 2,0R do TP1 i 3,1R do TP2.
- **Zmienność 7.** ATR około 475 zł; jeden kontrakt to 0,84% ryzyka.
- **Koszty 9.** Około 3% ATR.
- **Technika 7.** Kurs pod EMA20, EMA50 i EMA200, niższe szczyty od września. Obecne odbicie o 6% jest ruchem przeciwnym do trendu.
- **Ryzyko zdarzeń 6.** Państwo może złagodzić daninę, a niska wycena i dywidenda przyciągają kupujących.

**KGH (FKGHZ26)**

- **Płynność 10.** Najpłynniejszy kontrakt na akcje: 32,7 mln zł obrotu dziennie.
- **Teza 5.** Miedź się koryguje, ale ceny metali i zyski wciąż są wysokie, a raport wypada 18.11.
- **R:R 5.** Short z 290–293 ze stopem 299 daje około 2,5R, ale ryzyko to około 700 zł na kontrakt.
- **Zmienność 2.** ATR około 1 200 zł; jeden kontrakt to 1,4–2,4% kapitału, więc nie mieści się w limicie 1%.
- **Koszty 10.** Około 2% ATR.
- **Technika 7.** Kurs pod wszystkimi EMA, niższe szczyty.
- **Ryzyko zdarzeń 5.** Raport 18.11, beta 1,56.

**CPS (FCPSZ26)**

- **Płynność 7.** Duży LOP, ale nominał kontraktu to tylko około 1 300 zł, a obrót 2,3 mln zł dziennie.
- **Teza 6.** Rozczarowująca strategia, wysokie zadłużenie i refinansowanie przy jastrzębiej RPP.
- **R:R 5.** Wejście 13,4–13,6, stop 14,1, cel 12,2–11,7, czyli 2–3R. Jednak od 3.11 kurs buduje bazę.
- **Zmienność 8.** ATR około 75 zł, łatwo dobrać liczbę kontraktów.
- **Koszty 5.** Około 10% ATR, bo prowizja 3 zł jest duża przy tak małym kontrakcie.
- **Technika 6.** Kurs pod wszystkimi EMA, ale od 3.11 nie ma nowych dołków.
- **Ryzyko zdarzeń 4.** Raport 18.11 przy niskich oczekiwaniach może dać odbicie z ulgi; są też ryzyka transakcji właścicielskich [hipoteza].

**JSW (FJSWZ26)**

- **Płynność 6.** Obrót tylko około 0,9 mln zł dziennie.
- **Teza 5.** Spółka ma straty, ale pożyczka z ARP zdejmuje ryzyko utraty płynności.
- **R:R 6.** Wejście 27,8–28,3, stop 29,1, cel 25,7, około 2,3R.
- **Zmienność 8.** ATR około 118 zł.
- **Koszty 7.** Około 7% ATR.
- **Technika 6.** Kurs pod EMA, ale od 2 tygodni w konsolidacji.
- **Ryzyko zdarzeń 4.** Państwo, związki zawodowe i mało płynne akcje sprzyjają gwałtownemu squeeze.

**DNP (FDNPZ26)**

- **Płynność 6.** Obrót 1,0 mln zł dziennie, spread do 0,22%.
- **Teza 4.** Presja na marże, ale nowego katalizatora nie będzie do marca.
- **R:R 5.** 1,7–2,4R.
- **Zmienność 8.** ATR około 118 zł.
- **Koszty 4.** Około 11% ATR.
- **Technika 3.** Kurs nad EMA50 i EMA200, RSI 51; technika nie wspiera shorta.
- **Ryzyko zdarzeń 7.** Spółka defensywna.

### Dodatkowe sprawdzenie shortów

| Spółka | Wezwanie lub przejęcie | Skup akcji | Short squeeze | Dywidenda w serii Z26 |
|---|---|---|---|---|
| PKN | Mało prawdopodobne (Skarb Państwa ~49,9%) | Brak programu [do weryfikacji] | Niskie (kapitalizacja około 155 mld zł) | Brak (8 zł wypłacone w czerwcu 2026) |
| KGH | Nie (Skarb Państwa ~31,8%) | Brak | Niskie | Brak (1,50 zł w czerwcu 2026) |
| CPS | Niezerowe przy C/WK 0,7 i skoncentrowanym akcjonariacie [hipoteza] | Brak | Średnie | Brak (ostatnia dywidenda w 2022) |
| JSW | Nie (Skarb Państwa ~55%) | Brak | Wysokie przy newsach politycznych | Brak |
| DNP | Nie (założyciel ~51%) | Brak [do weryfikacji] | Niskie | Brak |

---

## Etap 4. Mechanika kontraktu i realia DM BOŚ

| Element | FALEZ26 (LONG) | FPKNZ26 (SHORT) |
|---|---|---|
| Seria | FALEZ26 (grudzień 2026) | FPKNZ26 |
| Mnożnik | 100 akcji (KDPW, `cvf` 100) | 100 akcji |
| Krok notowania i wartość ticka | 0,01 zł = 1 zł na kontrakt (z transakcji) | 0,01 zł = 1 zł na kontrakt |
| Ostatni dzień obrotu | 18.12.2026, piątek (KDPW `setlDate` 20261218) | 18.12.2026 |
| Limity wahań | Giełdowe **[do weryfikacji w specyfikacji GPW]**. DM BOŚ odrzuca zlecenia powyżej 100 szt. i z limitem odchylonym o ponad 25% od kursu zamknięcia. | jw. |
| Wartość nominalna | 65,71 × 100 = 6 571 zł | 134,65 × 100 = 13 465 zł (przy 138,50: 13 850 zł) |
| Depozyt KDPW_CCP (SPAN) | 996,50 zł na kontrakt, czyli 15,5% ceny rozliczeniowej 64,29 z 12.11. Przy cenie 65 około 1 008 zł. | 1 175,68 zł, czyli 8,8% ceny 133,60. Przy 138,50 około 1 219 zł. |
| Depozyt DM BOŚ | Równy 100% depozytu SPAN, bez add-onów KDPW (zarządzenie Dyrektora DM BOŚ, wyciąg na 14.10.2026) | jw. |
| Efektywna dźwignia | Około 6,5x | Około 11,4x |
| Prowizja DM BOŚ | 3,00 zł za kontrakt przy wejściu i tyle samo przy wyjściu (bossa.pl, 13.11). Rozliczenie przy wygaśnięciu też 3 zł. | jw. |
| Spread [szacunek] | 6–8 zł na kontrakt | Około 8 zł na kontrakt |
| Ile ticków pokrywa koszty | Około 13 ticków na wejście i wyjście (6 zł prowizji + około 7 zł spreadu), czyli 0,13 zł ceny | Około 14 ticków |
| Basis i dywidenda | Kontrakt około +0,35 zł nad akcją (różne godziny notowań). Teoretycznie około +0,24 zł (3,75% przez 35 dni) [szacunek]. Allegro nie płaci dywidendy. | Około +0,7 zł nad akcją, teoretycznie około +0,48 zł. Dywidendy w serii Z26 nie ma, więc zbieżność basis daje shortowi około 48 zł na kontrakt. |
| Rolowanie | Niepotrzebne, bo wyjście najpóźniej 16.12. Seria H27 jest niepłynna (LOP 63). | Niepotrzebne; H27 ma LOP 70. |
| Mark-to-market | Rozliczenie dzienne. Trzymaj co najmniej około 2 800 zł na 2 szt.: depozyt około 2 000 zł, ruch do stopu 440 zł, luka o 1 ATR około 350 zł. KDPW przelicza depozyty codziennie, więc wezwanie może przyjść bez dojścia do stopu. | Co najmniej około 2 100 zł na 1 szt.: depozyt 1 220 zł, ruch do stopu 410 zł, luka około 470 zł. |
| Ryzyko luki | 12.11 była luka +5% na wynikach. Przy luce stop zrealizuje się po otwarciu, możliwe 1–2 zł gorzej (100–200 zł na kontrakt). Weekend też jest ryzykiem. | 6.11 była luka −7,5% na wynikach. Ryzyko luki w górę, jeśli rząd złagodzi daninę. |

---

## Etap 5. Plany transakcyjne

### LONG: Allegro, FALEZ26

| Pole | Treść |
|---|---|
| Spółka i seria | Allegro.eu (ALE), **FALEZ26** |
| Teza | Najlepsza od 2022 dynamika GMV przy rekordowych marżach, przyspieszenie w IV kw. i podniesiona prognoza dają paliwo do dryfu kursu po wynikach. Od 18.11 skup akcji z limitem 65 zł tworzy kupującego poniżej 65 zł. Spółka bije WIG20 o 18,5% w miesiąc przy płynnym kontrakcie. |
| Katalizator i timing | 18.11: walne zgromadzenie (głosowanie nad limitem 65 zł); 18–19.11: konferencja Morgan Stanley TMT [do weryfikacji]; 27.11: Black Friday; podnoszenie cen docelowych przez analityków po wynikach. Horyzont 1–4 tygodnie. |
| Warunki otwarcia | Korekta do 64–65 zł bez złych wiadomości. WIG20 nie traci więcej niż ~2% w dniu wejścia. Kurs nie zamyka dnia poniżej 62,70. **Nie gonić:** nie kupować po rynku i nie podnosić limitów. |
| Strefa wejścia | Zlecenie A: kupno 1 szt. z limitem **65,00**. Zlecenie B: kupno 1 szt. z limitem **64,20**. Oba ważne do 27.11. |
| Stop loss | **62,40** dla obu kontraktów, poniżej dołka dnia wyników (akcje 62,73, kontrakt po 9:00 63,10). To około 1,3 ATR od średniej ceny wejścia. |
| TP1 / TP2 | **TP1 68,00**: przy dwóch kontraktach zamknij jeden, a stop drugiego przesuń na 64,60; przy jednym kontrakcie tylko przesuń stop na cenę wejścia. **TP2 70,50**: zasięg ruchu (fala 44,1→59,5 dodana do dołka 57,0 daje około 72,4), cel ustawiony konserwatywnie niżej. |
| Prowadzenie stopu | Po zamknięciu dnia powyżej 67 przesuń stop na 65,00. |
| R:R | Oba kontrakty (średnio 64,60): 1,55 do TP1, 2,68 do TP2, **2,11 łącznie**. Tylko zlecenie A: 2,12 do TP2. Tylko zlecenie B: 2,11 do TP1, 3,50 do TP2. |
| Liczba kontraktów | **2** przy 50 000 zł i ryzyku 0,5–1% (1 szt., jeśli wejdzie tylko zlecenie A) |
| Depozyt i dźwignia | Około 2 000 zł (2 × około 1 000 zł). Dźwignia na pozycji 6,5x. Nominał 12 920 zł, czyli 26% kapitału. |
| Wynik po kosztach (2 szt.) | Stop: **−462 zł (−0,92%)**. TP1 i reszta na stopie z ceną wejścia: **+328 zł**. TP1 i TP2: **+918 zł (+1,84%)**. Obie sztuki na TP2: +1 168 zł (+2,34%). |
| Styl | Swing 1–4 tygodnie. Przewaga pochodzi z fundamentów (dryf po wynikach, skup), nie z sygnału technicznego. |
| Stop czasowy | Jeśli do 4.12 nie będzie TP1, a kurs jest poniżej 65, wyjdź. Najpóźniej wyjdź 16.12. Jeśli kurs dojdzie do 68 przed realizacją zleceń, anuluj je i oceń setup od nowa. |
| Co unieważnia tezę | Zamknięcie dnia poniżej 62,70. Walne odrzuca limit 65 zł. Obniżenie prognozy albo sprzedaż dużego pakietu (ABB). Spadek WIG20 o ponad 5% w kilka sesji. |
| Główne ryzyka | 1. Wykupienie (RSI 78) i realizacja zysków po 100% wzroście w pół roku. 2. Podniesienie prognozy w dużej części wynika z jednorazowego efektu umowy z InPostem (+270–280 mln zł w IV kw., wg analizy z 12.11) [do weryfikacji]. 3. Korekta rynku: WIG20 pod rekordem, wyprzedaż technologii w USA, jastrzębi Fed. 4. Luki nocne i weekendowe. 5. Wycena około 16x EBITDA 2026 może skłonić analityków do obniżek rekomendacji. |

### SHORT: Orlen, FPKNZ26 (warunkowy)

| Pole | Treść |
|---|---|
| Spółka i seria | Orlen (PKN), **FPKNZ26** |
| Teza | Wyniki III kw. poniżej konsensusu, odpisy, nowa danina na importerów gazu i windfall tax na Litwie pokazują, że państwo przerzuca na spółkę koszty polityki. Trend spadkowy (niższe szczyty od września, kurs pod EMA20, EMA50 i EMA200). Odbicie od 125,9 traktuję jako korektę do strefy luki 130,1–140,7. |
| Katalizator i timing | Prace nad daniną gazową (przyjęcie projektu przez rząd lub Sejm) [termin do weryfikacji]. Kurs ropy i gazu. Horyzont 1–3 tygodnie od wejścia. |
| Warunki otwarcia | Wzrost do strefy 137,5–139,5 **bez** pozytywnego newsa fundamentalnego (np. wycofania daniny). Jeśli wzrost wynika z takiej wiadomości, nie wchodź. Lepiej, jeśli w strefie widać słabość: knot górny albo powrót poniżej 137. |
| Strefa wejścia | Sprzedaż 1 szt. z limitem **138,50** (strefa 137,5–139,5), ważna do 27.11 |
| Stop loss | **142,60**, nad szczytem z 5.11 (142,0) i nad EMA20 (142,3). To około 0,9 ATR. |
| TP1 / TP2 | **TP1 130,20**, dół luki z 6.11. Po jego osiągnięciu przesuń stop na 134,00. **TP2 125,80**, dołki z 9–10.11 (124,6–125,8). |
| R:R | **2,02 do TP1, 3,10 do TP2.** Dla porównania short po rynku z 134,65 daje tylko 1,11, dlatego teraz nie wchodzić. |
| Liczba kontraktów | **1** (przy 2 szt. ryzyko wyniosłoby 1,7%) |
| Depozyt i dźwignia | Około 1 220 zł. Dźwignia 11,4x. Nominał 13 850 zł, czyli 28% kapitału. |
| Wynik po kosztach | Stop: **−421 zł (−0,84%)**. TP1: **+824 zł (+1,65%)**. TP2: **+1 264 zł (+2,53%)**. |
| Styl | Swing 1–3 tygodnie z wejściem na odbiciu do oporu |
| Stop czasowy | Jeśli zlecenie nie wejdzie do 27.11, anuluj. Jeśli po wejściu do 7.12 kurs nadal jest powyżej 135, wyjdź. Najpóźniej wyjdź 16.12. |
| Co unieważnia tezę | Zamknięcie dnia powyżej 142,6. Rząd wycofuje albo łagodzi daninę. Orlen ogłasza skup akcji albo wyższą dywidendę. Silne wybicie WIG20 powyżej 4 300 pkt z Orlenem w roli lidera. |
| Główne ryzyka | 1. Polityka: rząd może złagodzić daninę albo pozwolić przenieść koszt na taryfy. 2. Niska wycena (EV/EBITDA 4,3, C/WK 1,15) i dywidenda przyciągają inwestorów szukających wartości. 3. Odbicie o 6% w 3 sesje może przejść w dłuższą korektę wzrostową. 4. Rynek jest w trendzie wzrostowym. 5. Wahania cen ropy, gazu i marż rafineryjnych. |

### Pair trade (ALE long + PKN short)

Spółki są z różnych sektorów, a korelacja dziennych stóp zwrotu z 60 sesji wynosi **−0,02** (obl.), więc pozycje nie zabezpieczają się wzajemnie. Razem obniżają ekspozycję na WIG20: beta razy nominał daje +11,1 tys. zł dla ALE i −7,6 tys. zł dla PKN, czyli netto około +3,5 tys. zł zamiast +11,1 tys. zł. Ryzyka specyficzne się jednak sumują: jeśli oba stopy zostaną trafione, strata wyniesie **−883 zł (1,77%)**. **Wniosek:** traktuj je jako dwie niezależne transakcje i nie otwieraj shorta PKN jako zabezpieczenia longu ALE.

---

## Etap 6. Krytyczna weryfikacja

### Próba obalenia LONG ALE

1. Kurs podwoił się w pół roku. Wycena (około 16x EBITDA 2026) wyprzedza stare ceny docelowe analityków, np. 37 zł od BM mBank z listopada 2025.
2. Przy podniesieniu prognozy chodzi głównie o jednorazowe pieniądze z InPostu. Bez nich IV kw. może być płaski r/r, a rynek może to w końcu zauważyć.
3. RSI 78, kurs 12% nad EMA20 i dwie mocne sesje z rzędu: na tym etapie zwykle przychodzi konsolidacja, a zlecenia z limitem mogą się nie zrealizować.
4. LOP na FALE spadł w dniu wyników, więc wzrost napędzało też zamykanie shortów. To paliwo jednorazowe.

**Czy miejsce 2 (PKO) jest lepsze?** PKO ma lepszą płynność i niższą zmienność, ale jego katalizator minął 5.11, a trend tygodniowy jest boczny. ALE wygrywa świeżym katalizatorem i lepszym R:R z limitu. Jeśli ALE nie wróci do 64–65 zł do 27.11, rozsądnym zamiennikiem jest **PKO**: kupno 1 × FPKOZ26 na teście wybicia 118,0–118,6 (np. 118,30), stop 115,40 i TP 125,50. Daje to około 2,5R przy ryzyku około 300 zł (0,6%).

### Próba obalenia SHORT PKN

1. Złe wiadomości mogą być już w cenie: spadek o 24% od szczytu (164→125), EV/EBITDA 4,3 i dywidenda 8 zł.
2. Wypowiedzenie drogiej umowy LNG obniża koszty, a odbicie o 6,4% w trzy sesje może oznaczać, że dołek z 9.11 to dno.
3. Danina to na razie projekt. Rząd ma powody, by jej nie zaostrzać, bo Orlen jest „narodowym czempionem”.
4. Shortowanie podczas hossy (WIG20 pod rekordem) ma statystycznie słabsze szanse.

**Czy miejsce 2 (KGH) jest lepsze?** Technicznie jest czystszy i najpłynniejszy, ale przy 50 tys. zł jeden kontrakt to około 700 zł ryzyka (1,4%), a raport 18.11 to zdarzenie zero-jedynkowe. Dla tego kapitału KGH odpada. CPS (miejsce 3) ma tani kontrakt, ale koszty sięgają około 10% ATR, a raport 18.11 przy niskich oczekiwaniach grozi odbiciem.

### Fakty, hipotezy, spekulacje

**Fakty (źródło i data):**

- Allegro: wyniki i prognoza (komunikat z 12.11) oraz uchwała o limicie 65 zł na walnym 18.11 (dokumenty walnego).
- Orlen: wyniki poniżej konsensusu (5.11), wypowiedzenie umowy LNG (raport bieżący 39/2026 z 10.11), projekt daniny (Parkiet, 10.11).
- Depozyty: KDPW, 12.11. Prowizje: bossa.pl, 13.11. Depozyt równy 100% SPAN: wyciąg z zarządzeń DM BOŚ na 14.10.
- Kursy, LOP i obroty: BR, 13.11 (opóźnienie 15 min).

**Hipotezy:**

- Dryf po wynikach Allegro i skup akcji poniżej 65 zł utrzymają kurs nad 62,7.
- Strefa luki 137,5–140,7 zatrzyma odbicie Orlenu.

**Spekulacje:**

- Cele 70,50 (ALE) i 125,80 (PKN) to zasięgi techniczne.
- Założenie, że danina wejdzie w proponowanym kształcie.

---

## Etap 7. Werdykt

1. **Najlepszy LONG:** Allegro, FALEZ26 (8,20). **Najlepszy SHORT:** Orlen, FPKNZ26 (7,60). **Lepsza transakcja teraz: LONG ALE**, ale wyłącznie ze zleceń z limitem 65,00 i 64,20.
2. **Minimum do wejścia** (R:R ≥ 2, filtr płynności, katalizator):
   - **ALE: spełnione tylko z limitu.** Po cenie rynkowej (65,7) R:R wynosi 1,45, więc **nie kupować po rynku**.
   - **PKN: teraz nie wchodzić** (R:R 1,11). Czekać na wzrost do 137,5–139,5 bez pozytywnego newsa, zlecenie ważne do 27.11.
3. **Checklista przed złożeniem zlecenia w bossaNOVA lub na platformie webowej DM BOŚ:**
   - **Depozyt i wolne środki.** ALE 2 szt.: około 2 000 zł depozytu + około 800 zł bufora. PKN 1 szt.: około 1 220 zł + około 900 zł. Sprawdź aktualny depozyt w bossaNOVA, bo KDPW przelicza go codziennie.
   - **Właściwa seria.** FALEZ26 i FPKNZ26, nie H27 (LOP 63 i 70).
   - **Typ zleceń.**
     - Wejście: zlecenie z limitem ważne do daty (27.11).
     - Zaraz po realizacji: stop jako zlecenie z limitem aktywacji typu PKC (żeby wykonało się przy luce) albo DDM+ OCO (stop + TP).
     - Wolumen zleceń ochronnych musi odpowiadać pozycji.
   - **Godziny notowań.** Notowania ciągłe około 8:45–16:50, fixing na zamknięcie około 17:00 [do weryfikacji w bossaNOVA].
   - **Limity DM BOŚ.** Maksymalnie 100 szt. w zleceniu, limit ceny najwyżej 25% od kursu zamknięcia.
   - **Kalendarz do wygaśnięcia serii:**
     - **18.11:** walne Allegro o 14:00; raporty KGHM, Cyfrowego Polsatu i Tauronu.
     - **18–19.11:** konferencja Morgan Stanley TMT [do weryfikacji].
     - **24.11:** raporty CD Projektu, PGE i JSW.
     - **27.11:** Black Friday i raport Modivo.
     - **2–3.12:** konferencja Wood & Co [do weryfikacji].
     - **Początek grudnia:** posiedzenie RPP [data do weryfikacji].
     - **8–9.12:** FOMC.
     - **16.12:** ostatni planowany dzień wyjścia.
     - **18.12:** wygaśnięcie Z26.
   - **Jeśli grasz kapitałem 11 000 zł i maksymalnie jednym kontraktem** (jak w planie z 12.11):
     - pasuje tylko 1 × FALEZ26 z 64,20 (ryzyko około 191 zł, czyli 1,7%);
     - kupno z 65,00 to 2,5% ryzyka;
     - short 1 × FPKNZ26 to około 3,8% ryzyka, czyli za dużo.

**Relacja do planu FALEZ26 z 12.11** (limit 63,8, stop 62,5, TP 69,0): ta analiza niezależnie wybrała Allegro jako najlepszy LONG. Kurs uciekł jednak ponad 65 zł, czyli powyżej proponowanego limitu skupu, więc skup wesprze kurs dopiero poniżej 65 zł. Dlatego strefa wejścia rośnie do 64,2–65,0, a cel dzielę na 68,0 i 70,5. Zasada „nie gonić” obowiązuje dalej.

**Dźwignia:** strata może przekroczyć wpłacony depozyt.

**Podatki:** PIT-38, 19% od dochodu, PIT-8C wystawi DM BOŚ. Straty z kontraktów kompensują się z zyskami kapitałowymi z tego samego roku (i można je odliczać przez 5 kolejnych lat).

*To analiza, a nie porada inwestycyjna. Decyzja i ryzyko należą do Ciebie.*

---

## Źródła (z datą dostępu 13.11.2026, chyba że zaznaczono inaczej)

- biznesradar.pl:
  - [lista kontraktów, LOP i obroty](https://www.biznesradar.pl/gielda/pochodne_kontrakty) (10:36 i 10:59 CET);
  - historia notowań akcji i kontraktów (do 12.11);
  - transakcje (12–13.11);
  - strony spółek z datami raportów okresowych;
  - [wskaźniki wartości rynkowej](https://www.biznesradar.pl/wskazniki-wartosci-rynkowej/ALE);
  - [zestawienie rekomendacji](https://www.biznesradar.pl/rekomendacje/ALE);
  - wiadomości spółek (bankier.pl, Parkiet, PAP, XYZ, Puls Biznesu).
- KDPW_CCP: [plik parametrów SPAN RPNJE_ZRS.xml](https://www.kdpwccp.pl/uploads/RPNJE_ZRS.xml) (12.11.2026, 18:28).
- DM BOŚ:
  - [opłaty i prowizje](https://bossa.pl/oferta/oplaty-i-prowizje);
  - [wyciąg z zarządzeń – rynek derywatów](https://online.bossa.pl/bossa/pdfdocument?name=APXPDF055) (stan na 14.10.2026);
  - [tabela opłat – derywaty](https://online.bossa.pl/bossa/pdfdocument?name=APXPDF035);
  - [FAQ kontrakty](https://bossa.pl/oferta/pytania-i-odpowiedzi?category=kontrakty).
- Allegro:
  - [komunikat prasowy za III kw. 2026](https://about.allegro.eu/wp-content/uploads/2026/11/Press-release.Allegro.Q3.pdf) (12.11.2026);
  - [uchwały walnego 18.11.2026](https://about.allegro.eu/wp-content/uploads/2026/10/2.-Resolutions-and-justifications-OGM_EGM-2026.pdf).
- Orlen:
  - [wyniki III kw. vs konsensus (xyz.pl)](https://xyz.pl/?p=272756);
  - [konsensus Orlen IR](https://www.orlen.pl/en/investor-relations/investors/consensus);
  - [mechanizm daniny (globenergia.pl)](https://globenergia.pl/maksymalna-cena-gazu-dla-gospodarstw-domowych-w-2027-roku-rzad-szykuje-nowe-przepisy/);
  - [Parkiet o zyskach i dywidendzie Orlenu](https://www.parkiet.com/rekomendacje/art44889281-zyski-orlenu-znow-moga-wzrosnac-podobnie-jak-dywidenda).
- Cyfrowy Polsat:
  - [strategia (xyz.pl)](https://xyz.pl/?p=269333);
  - [refinansowanie (grupapolsatplus.pl)](https://grupapolsatplus.pl/en/archive/commencement-works-analysis-possibility-refinancing-polsat-plus-groups-debt).
- Makro:
  - [RPP 4.11.2026 (bank.pl)](https://bank.pl/?p=564307);
  - [FOMC grudzień 2026](https://fedratecalc.com/fomc-meeting-schedule/december-2026/);
  - [miedź, listopad 2026 (Mysteel)](https://www.mysteel.net/analysis/5147737-trending-coppers-decline-reflects-collapsing-expectations-not-deteriorating-fundamentals);
  - [odrzucenie podwyżki CIT przez Sejm (superbiz.se.pl)](https://superbiz.se.pl/wiadomosci/dziura-w-budzecie-na-62-mld-zl-sejm-zablokowal-wyzszy-podatek-cit-aa-qps9-jDTd-Q68f.html).
- Modivo: [comparic.pl](https://comparic.pl/modivo-dino-pge-pko-bp-cd-projekt-pepco-kto-zyska-a-kto-straci-wyniki-wybicia-shorty-i-prognozy-dla-gigantow-gpw/).
- GPW (program animatorów): [uchwała 471/2026](https://www.gpw.pl/pub/GPW/uchwaly/2026/471_2026.pdf).
