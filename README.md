# Financial Volatility Analysis & Risk Forecasting via ARMA-GARCH Project
## Utilizing Time Series Models to Capture and Forecast Different Markets’ Volatility

Github Code Contributors:
* Zi Fang/zf2258
* Yufei Jing/yj2640
* Zikun Dong/zd2268

## SECTION 1: Project Overview
This project investigates the impact of unprecedented global events (e.g., COVID-19 pandemic, 2020 Presidential Election) on financial market volatility. By analyzing five key sector ETFs (XLV, XLE, XLF, XLI, XLK) from the S&P 500, we developed sophisticated ARMA-GARCH models to capture volatility clustering and leverage effects, ultimately evaluating the model's efficacy in Value-at-Risk (VaR) forecasting.

## SECTION 2: Core Workflow
1. Sector-Specific Data Analysis
Target Assets: Healthcare (XLV), Energy (XLE), Financial (XLF), Industrial (XLI), and Technology (XLK) ETFs.

Data Scope: Captured the critical transition period (2019–2021) to analyze market regime shifts during the pandemic.

Preprocessing: Log-return transformation and stationarity testing (ADF test).

2. Model Specification & Fitting
To account for the "heavy tails" and "asymmetry" of financial data, we implemented:

Mean Equation: ARMA(p,q) to filter linear dependencies.

Volatility Equation: Compared multiple GARCH variants:

Standard GARCH: For baseline volatility clustering.

GJR-GARCH & eGARCH: To capture the leverage effect (the tendency for negative shocks to increase volatility more than positive shocks).

GARCH-M (In-mean): To analyze the risk-return trade-off.

Innovation Distribution: Utilized Student-t and Skewed-t distributions to better model the leptokurtic nature of market returns.

3. Rigorous Model Validation
Diagnostic Checking: Conducted Ljung-Box and ARCH-LM tests on standardized residuals to ensure no remaining autocorrelation or conditional heteroscedasticity.

Performance Metrics: Evaluated models using AIC/BIC for parsimony and log-likelihood for goodness-of-fit.

Risk Validation: - Interval Coverage: Verified the accuracy of confidence interval predictions.

VaR Backtesting: Assessed the reliability of Value-at-Risk forecasts at 95% and 99% levels.

## SECTION 3: Key Insights
Asymmetric Impact: Energy (XLE) and Tech (XLK) sectors exhibited significant asymmetric volatility during market crashes.

Distribution Matters: Models assuming a Skewed-t distribution significantly outperformed Gaussian-based models in predicting extreme downside risk.

Sector Volatility: Technology showcased a faster "volatility mean-reversion" compared to the prolonged volatility seen in the Energy sector.

## SECTION 4: Tech Stack
Language: R (primarily using rugarch, tseries, and forecast libraries)

Quantitative Methods: Time Series Analysis, Maximum Likelihood Estimation (MLE), Volatility Modeling, Risk Management.

## SECTION 5: Repository Structure
5261_group20.pdf: Full technical report with mathematical derivations and visualization.

/scripts: R/Python scripts for model training and backtesting.

/data: Processed CSV files for the 5 sector ETFs.

