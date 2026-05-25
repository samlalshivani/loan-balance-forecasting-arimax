# Time Series Forecasting of Aggregate Loan Balances

## Overview
This project forecasts monthly aggregate loan portfolio balances using time-series econometric methods in Python. Account-level loan balance data were aggregated into a total portfolio balance series, transformed for stationarity, and modeled using ARIMAX/SARIMAX specifications with macrofinancial exogenous variables.

The final model produces a 12-month forecast of aggregate loan balances and evaluates baseline, bear-case, and bull-case scenarios.

## Data
The original dataset contains monthly account-level loan balances from 2018 to 2022. These balances were aggregated by observation date to create a total monthly portfolio balance series.

## Methodology
- Aggregated account-level balances into monthly total loan balances
- Conducted exploratory time-series analysis
- Tested for stationarity using the Augmented Dickey-Fuller test
- Applied first differencing and log-differencing transformations
- Examined ACF and PACF plots
- Used STL decomposition to evaluate trend and seasonality
- Estimated SARIMAX/ARIMAX models with exogenous variables
- Selected the final model using AIC and diagnostic testing
- Generated 12-month baseline and scenario-based forecasts

## Final Model
The selected model was an ARIMAX(2,0,1) model with two exogenous variables:

- 3-month Treasury bill rate
- S&P 500 monthly log returns

The model captured both autoregressive dynamics and macrofinancial relationships in aggregate loan balances.

## Key Results
- The aggregate loan balance series showed a strong upward trend and non-stationarity in levels
- Log-differencing stabilized the variance and centered the series around zero
- The ARIMAX(2,0,1) model produced statistically significant macrofinancial coefficients
- Residual diagnostics showed no significant remaining autocorrelation
- Scenario analysis showed that loan balances were sensitive to equity market conditions

## Forecasting Scenarios
Three forecast paths were generated:

- **Baseline:** Neutral equity market returns and stable short-term interest rates
- **Bear Case:** Continued negative S&P 500 returns
- **Bull Case:** Persistent positive monthly S&P 500 returns

The scenario analysis highlights the loan portfolio’s exposure to broader macrofinancial risks.

## Tools Used
- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- FRED macroeconomic data

## Files
| File | Description |
|---|---|
| `Project Code.ipynb` | Python notebook containing data processing, modeling, diagnostics, and forecasting |
| `figures/` | Forecast plots, residual diagnostics, and transformation graphs |

## Author
Shivani Samlal  
M.S. Applied Economics — Johns Hopkins University
