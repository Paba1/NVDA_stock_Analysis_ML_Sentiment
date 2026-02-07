# Predicting NVIDIA Stock Movements: A Machine Learning Approach
### 📈 Project for Bachelor's Thesis Development | Quantitative Finance & AI

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![ML Framework: Scikit-Learn](https://img.shields.io/badge/ML-Scikit--Learn-orange)](https://scikit-learn.org/)
[![Optimization: Optuna](https://img.shields.io/badge/Optimization-Optuna-blueviolet)](https://optuna.org/)

## 📖 Opis Projektu
Projekt skupia się na predykcji kierunku ruchu cen akcji **NVIDIA (NVDA)** w 5-dniowym horyzoncie czasowym. Głównym celem było stworzenie systemu wspomagania decyzji inwestycyjnych, który wykracza poza proste regresje, stosując zaawansowane techniki inżynierii danych finansowych (Financial Data Science).

Jest to projekt bazowy pod moją **pracę licencjacką**, w której badam efektywność modeli ML w konfrontacji z Hipotezą Rynku Efektywnego oraz wpływem czynników behawioralnych.

## 🛠️ Stack Techniczny & Metodologia
* **Modele:** XGBoost, Random Forest (zoptymalizowane pod kątem *Long Bias*).
* **Etykietowanie:** **Triple Barrier Method** – zaawansowana metoda klasyfikacji uwzględniająca progi Take Profit, Stop Loss oraz barierę czasową.
* **Optymalizacja:** Automatyczne strojenie hiperparametrów za pomocą **Optuna**.
* **Walidacja:** `TimeSeriesSplit` (Cross-Validation dedykowana dla szeregów czasowych), zapobiegająca wyciekowi danych.
* **Interpretowalność (XAI):** Wykorzystanie wartości **SHAP** do analizy wpływu poszczególnych wskaźników technicznych na decyzje modelu.

## 📊 Wyniki i Analiza Ryzyka
W starciu z ogromną zmiennością spółki NVIDIA, modele wykazały się wyższą odpornością na spadki kapitału (drawdown) w porównaniu do strategii pasywnej.

| Metryka | Buy & Hold (B&H) | XGBoost (Active) | Random Forest |
| :--- | :---: | :---: | :---: |
| **Max Drawdown** | **-36.88%** | **-34.10%** | -36.88% |
| **Skuteczność (3 klasy)** | ~33% (Benchmark) | **36** | ~38-40% |


> **Wniosek:** Model XGBoost pozwolił na ograniczenie maksymalnego obsunięcia kapitału o **2.78 punktu procentowego** względem strategii "Kup i Trzymaj", co w profesjonalnym tradingu jest istotną przewagą w zarządzaniu ryzykiem.

## 🚀 Kierunki Rozwoju (Roadmap do Licencjatu)
Projekt jest obecnie w fazie rozszerzania o analizę sentymentu rynkowego:
1.  **Integracja FinBERT:** Zastosowanie modelu NLP wyspecjalizowanego w tekstach finansowych do analizy newsów i raportów giełdowych.
2.  **Weryfikacja Hipotezy Shillera:** Badanie, czy emocje inwestorów (sentyment) mają silniejszą moc predykcyjną w krótkim terminie niż klasyczna analiza techniczna.
3.  **Model Hybrydowy:** Połączenie cech technicznych (OHLCV) z cechami tekstowymi (Sentiment Score).

## 🗂️ Struktura Plików
* `Nvidia-ML.ipynb` - Pełny kod: od pobrania danych, przez inżynierię cech, po backtesting
* `raportproejtkuML.pptx` - Synteza wyników i uzasadnienie biznesowe projektu.

---
**Autor:** Paweł Baczkowski  
