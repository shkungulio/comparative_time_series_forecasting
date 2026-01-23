[![Project Cover](resources/cover.png)](comparative_time_series_forecasting.pdf)

# Comparative Time Series Forecasting of Major Technology Stocks

## Business Overview
This project presents a comparative time series forecasting analysis of four major U.S. technology stocks: Apple (AAPL), Microsoft (MSFT), Tesla (TSLA), and Amazon (AMZN). Using nearly a decade of historical market data sourced from Yahoo Finance (January 2016–January 2026), the analysis examines how differences in trend behavior, volatility regimes, and market dynamics affect short-term forecastability.

The project is structured end-to-end using the CRISP-DM methodology and emphasizes reproducibility, rigorous evaluation, and stakeholder-relevant insights. The primary goal is not only to generate forecasts, but to compare predictability across assets under a consistent modeling framework.

## Problem Statement
Historical stock prices of major technology companies exhibit distinct trends, volatility patterns, and market dynamics. Understanding these behaviors is essential for forecasting short-term price movements and assessing financial risk.

The objective of this project is to perform a comparative time series analysis of Apple, Microsoft, Tesla, and Amazon stock prices using daily adjusted closing prices. The analysis aims to identify trends, seasonality, and volatility across each stock and to evaluate forecasting models in terms of accuracy and reliability. Model performance is assessed to determine which stocks are more predictable and which exhibit higher uncertainty over short forecasting horizons.

## Exploratory Data Analysis & Key Trends
Exploratory analysis revealed strong long-term upward trends across all four stocks, confirming non-stationarity in price levels. Due to large differences in absolute price scales, prices were indexed to a common baseline (start = 100) to enable meaningful relative performance comparisons. This transformation highlighted substantial divergence in cumulative growth trajectories over time.

Daily log returns were analyzed to assess risk and volatility characteristics. Return distributions exhibited heavy tails and volatility clustering—features typical of financial time series. Rolling 20-day standard deviations showed that Tesla experienced the highest and most frequent volatility spikes, while Apple and Amazon displayed comparatively more stable behavior. Monthly decomposition further indicated that trend components dominate across all series, with weak and unstable seasonal effects.

## Models Explored and Results
Two benchmark forecasting approaches were evaluated for each stock using a fixed 60-day holdout window:

- Naive (Random Walk) Model – Serves as a strong financial baseline where the last observed value persists.
- ARIMA (auto.arima) – A classical statistical time series model that captures short-term autocorrelation and drift.

Model performance was assessed using RMSE, MAE, and MAPE. Results demonstrated that model effectiveness is asset-specific:

- ARIMA outperformed the naive baseline for Apple and Amazon
- The naive model performed equally well or better for Microsoft and Tesla

These findings reinforce an important practical insight: greater model complexity does not universally improve forecast accuracy, particularly in highly volatile or near-random-walk assets.

## Dashboard Preview
This project is designed to be deployment-ready. A reusable forecasting function was implemented to retrieve fresh market data, fit an ARIMA model, and generate short-term forecasts. This modular design enables seamless integration into Shiny dashboards, scheduled pipelines, or interactive analytics tools.

A future interactive dashboard could allow users to:

- Select a stock ticker
- Compare forecast models visually
- Inspect recent volatility and forecast uncertainty
- Generate on-demand short-horizon forecasts

<--![![Dashboard](resources/dashboard.png)](https://crispinsights.shinyapps.io/iris_clusters_dashboard/) -->


## Reflections & Lessons Learned
This analysis highlights that forecastability varies substantially even among similar large-cap technology stocks. Assets with smoother volatility regimes tend to be more predictable under classical time series models, while highly volatile stocks often limit the gains achievable beyond naive baselines.

Key takeaways include the importance of:

- Strong baselines in financial forecasting
- Asset-specific model selection
- Residual diagnostics to validate assumptions
- Comparative evaluation under a consistent framework

Future enhancements could incorporate alternative model families (e.g., state-space or machine-learning models), exogenous predictors, longer forecast horizons, and automated deployment pipelines.
