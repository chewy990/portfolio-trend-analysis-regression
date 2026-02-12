# Portfolio Trend Analysis using Linear & Polynomial Regression

## Overview
This project analyses long-term trends in a diversified equity portfolio using historical financial time-series data.  
The goal is to evaluate whether **linear regression** is suitable as a baseline model for capturing portfolio growth over time, and to compare it against a **polynomial regression** model.

---

## Dataset
Historical daily price data (2015–2025) sourced from Yahoo Finance:
- S&P 500 Index
- NASDAQ-100 Index
- Apple Inc. (AAPL)
- Microsoft Corporation (MSFT)

Adjusted closing prices were used to account for stock splits and dividends.

---

## Methodology
1. **Data acquisition** using `yfinance`
2. **Data cleaning & transformation**
   - Converted multi-file dataset into a single First Normal Form (1NF) table
   - Forward-filled missing values due to differing trading calendars
3. **Portfolio construction**
   - Normalised all assets to a base value of 100
   - Weighted portfolio:
     - S&P 500: 45%
     - NASDAQ: 25%
     - AAPL: 15%
     - MSFT: 15%
4. **Exploratory statistical analysis**
   - Mean, median, standard deviation
   - Skewness and kurtosis
5. **Modelling**
   - Linear regression as a baseline trend model
   - Polynomial regression to capture non-linear behaviour
6. **Validation**
   - Train–test split without shuffling (time-series safe)
   - 5-fold cross-validation

---

## Key Results
- Linear regression captures the **long-term upward trend** but fails to model short-term volatility.
- Polynomial regression significantly improves performance:
  - Lower RMSE
  - Positive R² score
- Diversification reduces volatility and improves model stability.

---

## Tools & Libraries
- Python
- Pandas, NumPy
- Matplotlib
- scikit-learn
- yfinance

---

## What I Learned
- How to structure real-world time-series data pipelines
- Why train–test shuffling causes data leakage in time-series problems
- Trade-offs between interpretability and model accuracy
- Importance of validation beyond a single split

---

## Files
- `/notebook/` – Full Jupyter Notebook analysis
- `/data/` – Raw historical price data
