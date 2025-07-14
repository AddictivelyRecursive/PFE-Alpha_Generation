# 📈 Machine Learning-Based Trading Strategy on Pfizer (PFE)

This repository implements a Machine Learning-driven Long/Short trading strategy on Pfizer (PFE) stock from **2010-01-01 to 2025-04-16**, taking a daily position of USD 1 Million based on predictive signals.

The objective is to outperform a passive long strategy, while strictly avoiding any lookahead bias.  
A detailed methodology is provided in the *Trexquant_writeup.pdf*

---

## Methods Used

### 1. **PCA + VAR**  
A simple statistical baseline using Principal Component Analysis (PCA) followed by Vector AutoRegression (VAR) to predict next-day returns.

### 2. **SARIMAX + PCA**  
Incorporates seasonal patterns and exogenous variables derived via PCA to model time series structure and noise.

### 3. **XGBoost Regressor**  
A tree-based non-linear regression model trained to predict next-day returns using a wide set of engineered features.

---

## Key Highlights

- **No lookahead bias**: All features and predictions use only past data.
- **Out-of-sample testing**: From `2022-01-01` to `2025-04-16`.
- **Rolling-window normalization** for price/volume-based features.
- **Custom features** built beyond standard price/volume indicators.
- **Cumulative PnL visualization** for strategy performance.

---

## Contents

- `Trexquant.ipynb` — Full pipeline: data prep, feature engineering, model training, evaluation  
- `Trexquant_writeup.pdf` — Detailed explanation of methodology and results  
- `README.md` — Project overview
---

## PnL Calculation

Profit & Loss (PnL) is computed using daily close-to-close return multiplied by the current position (Long or Short). Corporate actions and dividends are ignored as per the problem definition.

---
