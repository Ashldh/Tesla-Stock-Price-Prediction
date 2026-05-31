# Tesla-Stock-Price-Prediction
Comparative analysis of ARIMA and LSTM models for forecasting Tesla opening stock prices.
# Tesla Stock Opening Price Prediction using ARIMA and LSTM

## Overview

This project forecasts Tesla (TSLA) opening stock prices using both classical statistical methods and deep learning techniques.

A comparative study was conducted between ARIMA and Long Short-Term Memory (LSTM) networks to evaluate their effectiveness in modeling highly volatile financial time-series data.

---

## Objectives

* Forecast Tesla opening stock prices.
* Evaluate stationarity of stock price data.
* Build an ARIMA baseline model.
* Develop an LSTM-based deep learning model.
* Compare forecasting performance using RMSE and R² metrics.

---

## Dataset

Source: Yahoo Finance

Ticker: TSLA

Features:

* Open
* High
* Low
* Close
* Volume

Target Variable:

* Open Price

Total observations: 2956 trading days

---

## Methodology

### Data Preprocessing

* Date indexing
* Missing value handling
* Min-Max scaling
* 60-day lookback window generation

### Statistical Analysis

Augmented Dickey-Fuller (ADF) Test:

* Original Series p-value = 0.9967
* First Difference p-value = 1.96e-17

Result:

The original series was non-stationary and became stationary after first-order differencing.

### ARIMA Model

Best Order:

ARIMA(5,1,4)

Performance:

* RMSE = 573.47
* R² = -2.27

Observation:

ARIMA struggled to capture Tesla's nonlinear and highly volatile price behavior.

### LSTM Model

Architecture:

* LSTM (50 units)
* Dropout (0.2)
* LSTM (50 units)
* Dropout (0.2)
* Dense (25)
* Dense (1)

Training Configuration:

* Window Size = 60
* Batch Size = 32
* Epochs = 20
* Optimizer = Adam
* Loss = Mean Squared Error

Performance:

* RMSE = 60.37
* R² = 0.963

---

## Results

| Model        | RMSE   | R² Score |
| ------------ | ------ | -------- |
| ARIMA(5,1,4) | 573.47 | -2.27    |
| LSTM         | 60.37  | 0.963    |

The LSTM model significantly outperformed the ARIMA baseline, demonstrating the effectiveness of recurrent neural networks for financial time-series forecasting.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-Learn
* Statsmodels
* TensorFlow / Keras

---

## Future Improvements


* Transformer-based Time-Series Models
* Hyperparameter Optimization
* Sentiment Analysis Integration
* Multi-feature Forecasting

---

## Author

Ashish Kumar
