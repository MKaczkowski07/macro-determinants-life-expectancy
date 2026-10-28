# Makroekonomiczne determinanty oczekiwanej długości życia

🌍 **Wersja internetowa:** [Zobacz wyrenderowany raport HTML](https://mkaczkowski07.github.io/macro-determinants-life-expectancy/Projekt.html)

Analiza ekonometryczna badająca zależności między czynnikami społeczno-ekonomicznymi, wydatkami na ochronę zdrowia, edukacją i jakością środowiska a oczekiwaną długością życia w państwach europejskich. Wykorzystuje model regresji liniowej estymowany klasyczną metodą najmniejszych kwadratów (KMNK).

## Cel projektu
Celem projektu jest identyfikacja czynników związanych z oczekiwaną długością życia w państwach europejskich oraz ocena siły i istotności statystycznej tych zależności. Analiza obejmuje przygotowanie danych, estymację i diagnostykę modelu regresji liniowej, weryfikację jego założeń, dobór specyfikacji oraz interpretację uzyskanych wyników.

## Kluczowe wnioski analityczne
* **Wysoka moc objaśniająca:** Ostateczny model tłumaczy blisko 80% (skorygowany R<sup>2</sup> = 0.79) zmienności oczekiwanej długości życia w Europie. Kluczową rolę odgrywają tu dwa czynniki: poziom zamożności (zlogarytmowane PKB per capita) oraz odsetek PKB przeznaczany na opiekę zdrowotną.
* **Zróżnicowany wpływ zamożności (efekt skali):** Uwzględnienie interakcji zamożności z przynależnością do OECD (`log_gdp_pc * oecd`) ujawniło wyraźne różnice między grupami państw. W krajach rozwijających się każdy dodatkowy wzrost PKB per capita przynosi skokowy przyrost oczekiwanej długości życia. Z kolei w zamożnych gospodarkach OECD dodatkowy wzrost dochodu wiąże się ze znacznie mniejszym przyrostem oczekiwanej długości życia. Wynik ten jest zgodny z prawem malejących przychodów, zgodnie z którym w państwach wysoko rozwiniętych dalszy wzrost zamożności przynosi coraz mniejsze korzyści w zakresie długości życia.
* **Odporność na obserwacje odstające:** Monako i Liechtenstein, mikropaństwa o specyficznej strukturze gospodarki, silnie odstawały od reszty próby i mogły zniekształcać linię regresji, dlatego wyłączyłem je z analizy. Z próby usunąłem też San Marino i Kosowo, w których występowały braki danych. Dzięki temu model opisuje zależności typowe dla europejskich gospodarek.

## Wykorzystane technologie
* R i R Markdown – cała analiza i generowanie raportu
* tidyverse, readxl, broom – wczytanie i przygotowanie danych
* lmtest, car – testy założeń modelu (Breusch-Pagan, RESET, VIF)
* stargazer, knitr, kableExtra – tabele w raporcie
* ggplot2, ggrepel, corrplot – wykresy

## Uruchomienie lokalne
Aby samodzielnie wygenerować raport na własnym środowisku:
1. Sklonuj repozytorium.
2. Otwórz projekt w RStudio używając pliku `Projekt.Rproj`.
3. Otwórz główny skrypt `Projekt.Rmd`.
4. Użyj opcji **Knit to HTML** (wymagane zainstalowane pakiety wymienione w nagłówku pliku).
