# 🏛️ Congressional Voting Classification

## 📌 O projekcie
Projekt polega na przewidywaniu przynależności partyjnej kongresmenów USA (Demokraci vs Republikanie) na podstawie ich głosowań w Izbie Reprezentantów. Jest to klasyczny problem klasyfikacji binarnych na wielowymiarowym zbiorze danych z dziedziny nauk społecznych. 

Głównym wyzwaniem w projekcie była obsługa brakujących danych (kongresmeni wstrzymujący się od głosu/nieobecni) oraz selekcja kluczowych cech, które najbardziej polaryzują obie partie.

## 📊 Dane
Wykorzystano zbiór danych **1984 United States Congressional Voting Records** z repozytorium UCI Machine Learning. 
- **Liczba instancji (kongresmenów):** 435
- **Liczba cech:** 16 (wyniki kluczowych głosowań, np. zamrożenie opłat za leczenie, wsparcie dla Salwadoru, wydatki na edukację)
- **Problem badawczy:** Klasyfikacja do dwóch klas (Demokrata / Republikanin).

## 🛠️ Wykorzystane technologie i algorytmy
- **Język:** Python
- **Analiza i obróbka danych:** `pandas`, `numpy`
- **Wizualizacja:** `matplotlib`, `seaborn`
- **Modele Machine Learning (`scikit-learn`):**
  - Decision Tree Classifier (Drzewo decyzyjne)
  - Logistic Regression (Regresja Logistyczna)
- **Techniki:** Imputacja modą (`SimpleImputer`), kodowanie kategoryczne, badanie korelacji cech.

## 📈 Najważniejsze wnioski
1. **Wysoka polaryzacja partii:** Modele osiągnęły bardzo wysoką skuteczność (ponad 92% dla Drzewa i **96% dla Regresji Logistycznej**). Udowadnia to, że sposób głosowania jest niemal bezpośrednio sprzężony z przynależnością partyjną.
2. **Kluczowa ustawa:** Analiza korelacji wykazała, że głosowanie nad ustawą *'physician-fee-freeze'* niemal idealnie oddziela obie frakcje (korelacja bliska 1.0).
3. **Odporność modeli:** Regresja logistyczna poradziła sobie lepiej w wychwytywaniu specyficznych przypadków i błędów (wyższa czułość/recall), wykazując przy tym dużą odporność na sztuczne uzupełnianie braków w danych. Zbudowany *pipeline* bez problemu radzi sobie z klasyfikacją nowych, surowych rekordów zawierających luki.

## 🚀 Jak uruchomić projekt lokalnie?
1. Sklonuj to repozytorium: `git clone https://github.com/IgorPszczola/congress-voting-classification.git`
2. Upewnij się, że posiadasz folder z danymi `congressional+voting+records/house-votes-84.data` w tym samym folderze.
3. Uruchom notatnik `congressional_voting_analysis.ipynb` (wymagany np. Jupyter Notebook lub środowisko w VS Code).
