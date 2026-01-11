# Factor Exposure Analyzer  
Applied Machine Learning for Financial Time Series

## Overview
This project implements an applied machine learning system to analyze how individual stocks are exposed to different underlying risk factors over time.

Instead of relying on pre-built factor ETFs, the model constructs engineered statistical and time-series features directly from raw price data. This makes the framework flexible, interpretable, and applicable across different equity markets such as the US and India (NSE/BSE).

The project emphasizes feature engineering, interpretability, and time-series modeling rather than black-box prediction.

---

## Problem Statement
Stock returns are influenced by multiple latent forces such as market movement, momentum, volatility, trend persistence, and mean reversion.

The objective of this project is to answer:
Which factors are driving a stock’s returns, and how do these exposures evolve over time?

---

## Engineered Factors
All factors are derived directly from historical price data.

| Factor | Description |
|------|------------|
| Market | Broad market return (NIFTY 50 or S&P 500 proxy) |
| Momentum | 6-month rolling average of stock returns |
| Volatility | 6-month rolling standard deviation of returns |
| Trend | Rolling linear regression slope of returns |
| Mean Reversion | Z-score of price relative to its rolling mean |

These engineered features demonstrate applied machine learning and statistical reasoning rather than reliance on external factor datasets.

---

## Methodology
1. Download historical price data using Yahoo Finance.
2. Compute log returns for the stock and market index.
3. Engineer time-series features representing momentum, volatility, trend, and mean reversion.
4. Fit a multi-factor linear regression model:

   r_stock = alpha  
             + beta_1 * Market  
             + beta_2 * Momentum  
             + beta_3 * Volatility  
             + beta_4 * Trend  
             + beta_5 * MeanReversion  
             + error

5. Estimate rolling factor betas using a sliding time window.
6. Visualize factor exposures using bar charts, radar charts, and rolling time-series plots.

---

## Tech Stack
- Python
- Pandas, NumPy
- Statsmodels (OLS regression)
- Matplotlib and Plotly
- Yahoo Finance API (via yfinance)
- Jupyter Notebook

---

## Outputs
The system produces:
- Factor exposure coefficients (betas)
- Alpha and model fit statistics (R²)
- Rolling factor exposures
- Visual analytics:
  - Factor exposure bar chart
  - Factor exposure radar chart
  - Rolling beta time-series plots

---
