# Analiza Szeregów Czasowych: Chevron (CVX) vs Valero Energy (VLO)

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Time Series](https://img.shields.io/badge/Time_Series-ARIMA-orange?style=for-the-badge)

Projekt realizujący analizę porównawczą oraz modelowanie szeregów czasowych dla cen akcji dwóch gigantów sektora energetycznego: **Chevron Corporation (CVX)** oraz **Valero Energy (VLO)**.

## Zakres danych
Analiza obejmuje notowania giełdowe (ceny zamknięcia) z okresu:
**01.01.2022 – 20.01.2026**

## Cele projektu
Głównym celem projektu było zbadanie dynamiki cen akcji oraz budowa modeli prognostycznych. Główne etapy prac obejmowały:
 
 1. **Analizę wizualną** przebiegu cen i identyfikację trendów.
 2. **Porównanie podejścia deterministycznego** (wielomiany) z podejściem **stochastycznym** (ARIMA).
 3. **Weryfikację stacjonarności** szeregów czasowych.
 4. **Diagnostykę reszt** w celu oceny jakości dopasowania modeli (test Ljunga-Boxa).

## Technologie i Biblioteki
Projekt został wykonany w środowisku **R/RStudio** przy użyciu następujących bibliotek:

 - `quantmod` – pobieranie danych finansowych z Yahoo Finance.
 - `forecast` – modelowanie ARIMA i prognozowanie.
 - `tseries` – testy stacjonarności (ADF, KPSS).
 - `lmtest` & `FinTS` – testy diagnostyczne.

## Metodologia i Kluczowe Wnioski

W ramach projektu przeprowadzono rygorystyczną analizę ekonometryczną, która doprowadziła do następujących konkluzji:

### 1. Analiza Trendu
Początkowa próba modelowania trendu za pomocą wielomianów (wybór stopnia metodą AIC wskazał na wielomian 10. stopnia) okazała się niewystarczająca. Analiza reszt wykazała silną autokorelację, co sugeruje, że ceny akcji nie podążają za deterministyczną ścieżką.

### 2. Badanie Stacjonarności
Przeprowadzono Rozszerzony Test ADF, który wykazał, że:

 - Logarytmiczne stopy zwrotu (pierwsze różnice) są **stacjonarne**.
 - Szeregi są zintegrowane w stopniu pierwszym – **I(1)**.

### 3. Modelowanie ARIMA
Dla obu spółek (CVX i VLO) algorytmy doboru modelu wskazały na model **ARIMA(0,1,0)**.

### Wniosek końcowy:
Ceny akcji obu spółek zachowują się zgodnie z modelem **Błądzenia Losowego (Random Walk)**. Oznacza to, że najlepszą prognozą ceny na okres $t+1$ jest cena z okresu $t$, a rynek w badanym okresie wykazuje cechy efektywności informacyjnej (słaba forma efektywności rynku).

## Autorzy
Projekt wykonali:
 - Damian Spodar
 - Tomasz Hanusek