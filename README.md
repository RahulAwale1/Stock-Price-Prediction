# 📈 Stock Price Prediction: ARIMA vs LSTM

## 🔍 Project Overview
This project demonstrates **time series forecasting** on Tesla (TSLA) stock prices using both **classical statistical methods** and **deep learning**.  
The goal is to compare **ARIMA** (Auto-Regressive Integrated Moving Average) with **LSTM** (Long Short-Term Memory networks) and evaluate their ability to predict stock price movements.

---

## 📊 Dataset
- Source: [Yahoo Finance](https://pypi.org/project/yfinance/)
- Stock: Tesla Inc. (TSLA)
- Period: 2018-01-01 → 2023-12-31
- Column used: **Closing Price**

---

## ⚙️ Methods

### 1. ARIMA (Classical Forecasting)
- Parameters: (p=5, d=1, q=0)
- Trained on 80% of the historical data
- Forecasted the next 20% (test set)
- **Result:**
  - RMSE ≈ **43.25**
  - Forecast flattened around mean → struggled with Tesla's volatility

### 2. LSTM (Deep Learning)
- Preprocessed with MinMax scaling (0–1)
- Lookback window: 60 days → predict next day
- Model architecture:
  - 2 × LSTM layers (50 units each)
  - Dropout (0.2) for regularization
  - Dense output layer (1 neuron)
- **Result:**
  - RMSE ≈ **13.19**
  - Predictions closely followed actual price movements
  - ~70% improvement compared to ARIMA

---

## 📉 Results & Visualization

### ARIMA Forecast vs Actual
![ARIMA Forecast](cfbd3c5b-a52f-4aff-a435-4afcfb3b62c4.png)

### LSTM Forecast vs Actual
![LSTM Forecast](080435a0-4b11-49ad-9a80-ae53801c19c2.png)

---

## ✅ Key Insights
- ARIMA is useful as a baseline but limited in capturing high volatility.
- LSTM significantly reduced error and modeled non-linear stock movements better.
- Deep learning models are powerful for financial time series, but they require careful tuning and more data.

---

## 🚀 Future Work
- Try other stocks (AAPL, AMZN) for generalization
- Deploy with **Streamlit** or **Hugging Face Spaces**
- Explore hybrid models (ARIMA + LSTM)

---

## 🛠️ Tech Stack
- Python
- yfinance, pandas, numpy
- statsmodels (ARIMA)
- TensorFlow/Keras (LSTM)
- Matplotlib
- Scikit-learn

---

