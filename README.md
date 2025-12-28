# Financial Volatility Analysis & Risk Forecasting
### Utilizing Time Series Models to Capture and Forecast Market Volatility

Github Code Contributors:
* Zi Fang/zf2258
* Yufei Jing/yj2640
* Zikun Dong/zd2268

### Section 1: Project Overview
This project investigates the adaptability of time series models in predicting abnormal financial market volatility caused by major social events, specifically the COVID-19 pandemic and the 2020 U.S. Presidential Election. By analyzing five S&P 500 sector ETFs (XLV, XLE, XLF, XLI, XLK), we implemented ARMA-GJR-GARCH models to capture asymmetric volatility and evaluated risk through Value-at-Risk (VaR) forecasting.

### Section 2: Methodology
1. Data Selection & Preprocessing
  Assets: Five industry-representative ETFs: Healthcare (XLV), Energy (XLE), Financial (XLF), Industrial (XLI), and Technology (XLK).

  Transformation: Daily closing prices were converted to log-returns to ensure stationarity, validated by Exploratory Data Analysis (EDA) and volatility clustering observations.

2. Model Specification
  The project follows a two-stage modeling approach for each sector:

  Mean Equation (ARMA): Optimized using auto.arima to filter autocorrelation. Models ranged from ARMA(0,0) to ARMA(6,6) depending on the sector.

  Volatility Equation (GJR-GARCH): A GJR-GARCH(1,1) model was selected for all sectors to specifically account for the leverage effect (asymmetric response to positive and negative shocks).

  Innovation Distributions: To address heavy tails and asymmetry, we utilized:

    Student-t Distribution (std): For XLV, XLI, and XLE.

    Skewed Student-t Distribution (sstd): For XLK and XLF.

3. Model Validation & Diagnostics
  Statistical Testing: Applied Weighted Ljung-Box Test and Weighted ARCH-LM Test on standardized residuals to confirm the absence of remaining serial correlation and ARCH effects.

  Information Criteria: Final models were selected based on the minimum AIC and BIC values.

4. Forecasting & Risk Assessment
  Volatility Forecasting: Performed 10-step out-of-sample forecasting for each sector.

  Value-at-Risk (VaR): Calculated and visualized 95% confidence interval coverage and VaR coverage to evaluate the models' performance in capturing downside risk during volatile periods.

### Section 3: Key Findings
  Leverage Effect: All five sectors exhibited significant asymmetric volatility, where negative shocks had a greater impact on future volatility than positive shocks.

  Sector Differences: The Energy (XLE) and Industrial (XLI) sectors showed higher volatility persistence and heavier tails compared to Healthcare (XLV) during the pandemic.

  Distribution Accuracy: Incorporating Skewed Student-t distributions for Tech and Financial sectors significantly improved the model's fit and risk estimation accuracy.

### Section 4: Tech Stack
  Language: R

  Key Libraries: rugarch, tseries, forecast, ggplot2

  Keywords: GJR-GARCH, Time Series Analysis, Value-at-Risk (VaR), Volatility Clustering, Leverage Effect.

### Section 5: Repository Final Results
  5261_group20.pdf: The complete technical report containing mathematical formulations and result plots.
  
  5261 Presentation_Group20.pdf: The final Powerpoint used for presentation.
