# 📊 Volatility Forecasting using GARCH & EGARCH Models

## Overview
This project explores volatility modeling and forecasting in financial markets using the GARCH family of models. The goal is to estimate and predict stock volatility and compare econometric models (GARCH, EGARCH) against a simple historical benchmark (rolling volatility).

Assets analyzed:
- AAPL (Apple)
- JPM (JPMorgan Chase)
- SKY

---

## Objective
- Model volatility clustering in financial returns
- Capture asymmetric volatility effects (leverage effect)
- Forecast short-term volatility (10-day horizon)
- Compare model performance against a rolling volatility benchmark

---

## Dataset
- Source: Yahoo Finance (via `yfinance`)
- Frequency: Daily adjusted closing prices
- Time period: ~10 years
- Transformation: Log returns  
  \[
  r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)
  \]

---

## Models Used

### 1. GARCH(1,1)
$\[
\sigma_t^2 = \omega + \alpha r_{t-1}^2 + \beta \sigma_{t-1}^2
\]$

Captures:
- Volatility clustering
- Persistence in shocks

---

### 2. EGARCH(1,1)
\[
\log(\sigma_t^2) = \omega + \alpha |z_{t-1}| + \gamma z_{t-1} + \beta \log(\sigma_{t-1}^2)
\]

Captures:
- Volatility clustering
- Asymmetric response to shocks (leverage effect)

---

## Key Findings

### 📌 GARCH Performance (MAE / RMSE)
- AAPL: MAE = 0.497, RMSE = 0.749  
- JPM: MAE = 0.388, RMSE = 0.507  
- SKY: MAE = 1.152, RMSE = 1.288  

---

### 📌 EGARCH Performance (MAE / RMSE)
- AAPL: MAE = 0.565, RMSE = 0.777  
- JPM: MAE = 0.459, RMSE = 0.550  
- SKY: MAE = 1.795, RMSE = 1.947  

---

### 📌 Rolling Volatility Benchmark (Best Performer)
- AAPL: MAE = 0.043, RMSE = 0.093  
- JPM: MAE = 0.040, RMSE = 0.094  
- SKY: MAE = 0.092, RMSE = 0.242  

---

## Diebold–Mariano Test Results
Statistical comparison of forecast accuracy:

- AAPL: DM = 9.09, p < 1e-10  
- JPM: DM = 11.91, p < 1e-10  
- SKY: DM = 25.46, p < 1e-10  

👉 Conclusion: Rolling volatility significantly outperforms GARCH/EGARCH forecasts.

---

## Key Insights
- GARCH models effectively capture **volatility clustering**
- EGARCH captures **leverage effects (negative shocks increase volatility more)**
- However, **simple rolling volatility outperforms both models in short-term forecasting**
- Model complexity does not guarantee better predictive performance

---

## Tools & Libraries
- Python
- pandas, numpy
- matplotlib
- arch (GARCH/EGARCH models)
- scipy (statistical tests)
- yfinance (data collection)

---

## Conclusion
This project demonstrates that while GARCH-family models are powerful for understanding volatility dynamics, simpler rolling window methods can outperform them in short-horizon volatility forecasting.

---

## Author
Kishan Patel
