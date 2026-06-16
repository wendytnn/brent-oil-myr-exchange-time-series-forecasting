# Brent Crude Oil & MYR/USD Time Series Forecasting

## Project Overview

This project investigates the forecasting performance of statistical and deep learning models on two financially significant Malaysian market indicators:

* **Brent Crude Oil Prices (BZ=F)**
* **MYR/USD Exchange Rate (MYR=X)**

Using daily business-day data from **March 2019 to March 2026**, the study evaluates the ability of **ARIMA**, **SARIMA**, and **Feedforward Neural Networks (FNN)** to generate accurate 30-day forecasts under both stable market conditions and periods of major economic disruption.

The project was completed as part of the **Time Series Analysis (COMPC8136)** module at Dundalk Institute of Technology.

---

## Objectives

* Perform end-to-end time series analysis on financial market data.
* Compare traditional statistical forecasting methods with deep learning approaches.
* Evaluate model performance during structural shocks such as COVID-19 and geopolitical events.
* Generate 30-business-day forecasts and assess predictive accuracy.

---

## Dataset

Data was collected using the Yahoo Finance API (`yfinance`).

### Brent Crude Oil

* Ticker: `BZ=F`
* Unit: USD per barrel
* Frequency: Business Day

### MYR/USD Exchange Rate

* Ticker: `MYR=X`
* Unit: Malaysian Ringgit per US Dollar
* Frequency: Business Day

### Study Period

* Start: 21 March 2019
* End: 20 March 2026
* Observations: 1,827 business days

---

## Methodology

### Data Preparation

* Missing value treatment
* Business-day frequency alignment
* Outlier analysis using IQR method
* Time series reindexing and forward filling

### Exploratory Data Analysis

* Time series visualization
* Rolling mean and volatility analysis
* Distribution analysis
* Correlation analysis
* Classical decomposition
* STL decomposition

### Stationarity Testing

* Augmented Dickey-Fuller (ADF)
* KPSS Test
* First-order differencing

### Forecasting Models

#### ARIMA

* Box-Jenkins methodology
* Auto-ARIMA model selection
* AIC/BIC comparison

#### SARIMA

* Seasonal modeling with weekly seasonality
* Auto-SARIMA optimization

#### Feedforward Neural Network (FNN)

* TensorFlow/Keras implementation
* 20-day lag window
* ReLU activation
* L2 Regularization
* Dropout (0.2)
* Early Stopping

---

## Model Evaluation

Models were evaluated on a held-out test set consisting of the final 30 business days using:

* MAE (Mean Absolute Error)
* RMSE (Root Mean Squared Error)
* MAPE (Mean Absolute Percentage Error)

### Key Findings

#### Brent Crude Oil

| Model  | RMSE  | MAPE   |
| ------ | ----- | ------ |
| ARIMA  | 20.88 | 15.36% |
| SARIMA | 18.58 | 13.19% |
| FNN    | 6.37  | 5.58%  |

**Best Model:** Feedforward Neural Network

The neural network successfully captured the strong upward momentum associated with the 2026 geopolitical oil price shock.

#### MYR/USD Exchange Rate

| Model  | RMSE   | MAPE  |
| ------ | ------ | ----- |
| ARIMA  | 0.0338 | 0.72% |
| SARIMA | 0.0954 | 1.89% |
| FNN    | 0.0377 | 0.85% |

**Best Model:** ARIMA(1,1,1)

The exchange rate exhibited relatively stable dynamics, making ARIMA the most effective forecasting approach.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Statsmodels
* pmdarima
* TensorFlow / Keras
* Scikit-learn
* Jupyter Notebook

---

## Repository Structure

```text
├── CA2_tsa_PeiWenTanWendy_d00253240.ipynb
├── CA2_TSA_Final_Project_Report_PeiWenTan_D00253240.pdf
├── brent_crude_2019_2026.csv
├── usdmyr_2019_2026.csv
└── README.md
```

---

**Pei Wen Tan (Wendy)**
First Class Honours Graduate
BSc (Hons) Mathematics & Data Science
Dundalk Institute of Technology

