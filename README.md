# Prediction Store Sales with Time Series
## Overview
Our goal is to predict next month's daily sales. Accordingly, we will conduct experiments to find the best model for this task.
We will use the Mean Absolute Percentage Error (MAPE) as our evaluation metric.



## 📊 Dataset
We are given 5 years of store-item sales data, and asked to predict 3 months of sales for 50 different items at 10 different stores
The dataset contains historical demand data for products, including sales information, timestamps, stores, and products.
Link: https://www.kaggle.com/competitions/demand-forecasting-kernels-only/overview


## Exploratory Data Analysis (EDA)
- Analazing Sales Dynamics by Item
- Analazing Sales by Store for Each Item
- Analazing Daily Sales in all stores
- Analazing Sales Dynamics by Store

## Data Preprocessing
In this project, I predicted sales for one store and one product. I decomposed the time series using the additive model into trend, seasonality, and residuals with the statsmodels library. The plots were analyzed to identify how each component contributes to the overall time series, providing insights into the sales patterns of the product in the store.

- Conclusions: The sales chart shows that the series is quite variable, with consistent fluctuations throughout the entire period. The time series has an upward trend. Sales exhibit seasonality. The residuals represent noise or random variations that cannot be explained by the trend or seasonality. Also, i analyzed residuals: From the autocorrelation function (ACF) plot, we see that autocorrelation for some lags falls within the confidence interval, indicating a certain dependency in the residuals. However, other plots show that the residuals follow a normal distribution. Therefore, we can conclude that the additive model adequately describes the data.
There is seasonality of order 7

## Pipeline of project 
- NaiveSeasonal
- NaieDrift
- XBGModel
- ExponentialSmoothing
- ARIMA
- AutoARIMA
- Prophet
- RNNModel
- BackTest for the best model
- Analysing residuals

## Results 

<table>
  <tr>
    <th colspan="2">NaiveSeasonal</th>
    <th colspan="2">NaieDrift</th>
    <th colspan="2">XBGModel</th>
    <th colspan="2">ExponentialSmoothing</th>
    <th colspan="2">ARIMA</th>
    <th colspan="2">AutoARIMA</th>
    <th colspan="2">Prophet</th>
    <th colspan="2">RNNModel</th>
  </tr>
  <tr>
    <th>MAPE</th>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>
