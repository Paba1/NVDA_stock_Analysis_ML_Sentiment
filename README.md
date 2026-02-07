# NVIDIA Stock Price Movement Prediction using Machine Learning

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-Latest-green)](https://xgboost.ai/)

Projekt zrealizowany w ramach przedmiotu **Podstawy Sztucznej Inteligencji**, skupiający się na predykcji kierunku ruchu cen akcji spółki **NVIDIA (NVDA)**. System klasyfikuje ruchy rynkowe w 5-dniowym horyzoncie czasowym, wykorzystując zaawansowane metody inżynierii cech oraz algorytmy uczenia zespołowego.

## 🚀 Key Features

* **Triple Barrier Method**: Nowoczesne podejście do etykietowania danych (zamiast prostych zwrotów logarytmicznych), uwzględniające dynamiczne poziomy *Take Profit* i *Stop Loss*.
* **Multi-class Classification**: Klasyfikacja ruchu jako: Spadek (0), Neutralny (1), Wzrost (2).
* **AutoML & Optimization**: Automatyczne strojenie hiperparametrów przy użyciu biblioteki **Optuna**.
* **Explainable AI (XAI)**: Analiza istotności cech przy użyciu wartości **SHAP**, pozwalająca zrozumieć, co kieruje decyzjami modelu.
* **Technical Analysis Integration**: Wykorzystanie biblioteki `TA-Lib` do generowania wskaźników (RSI, MACD, Bollinger Bands, ATR).

## 📊 Methodology

### Data Engineering
Dane zostały pobrane za pomocą `yfinance`. W procesie przygotowania danych zaimplementowano:
* Wskaźniki trendu, pędu oraz zmienności.
* Lagowanie cech (Lags) w celu uchwycenia zależności czasowych.
* Normalizację i obsługę brakujących danych specyficznych dla szeregów czasowych.

### Models
W projekcie porównano dwa główne modele:
1.  **Random Forest**: Klasyfikator bazowy, dobrze radzący sobie z szumem giełdowym.
2.  **XGBoost**: Zaawansowany model gradient boostingu, zoptymalizowany pod kątem precyzji.

### Validation Strategy
Zastosowano **TimeSeriesSplit** (Cross-Validation dla szeregów czasowych), aby uniknąć wycieku danych (*data leakage*) i zapewnić rzetelną ocenę zdolności generalizacji modelu.

## 📈 Results

Modele osiągnęły skuteczność na poziomie **~38-40% Accuracy** (przy 3 zbalansowanych klasach i dużej losowości rynku NVDA), co stanowi istotną przewagę nad modelem losowym (33%).

| Model | Max Drawdown | Risk Management |
| :--- | :--- | :--- |
| **Buy & Hold** | -36.88% | Brak |
| **XGBoost Active** | -34.10% | Aktywne zarządzanie pozycją |

## 🛠 Installation & Usage

1. Sklonuj repozytorium:
   ```bash
   git clone [https://github.com/twoj-uzytkownik/nvidia-ml-prediction.git](https://github.com/twoj-uzytkownik/nvidia-ml-prediction.git)
