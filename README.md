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
    <th colspan="2">38.17%</th>
    <td>38.17%</td>
    <td>39.91%</td>
    <td>23.38%</td>
    <td>39.01%</td>
    <td>37.83%</td>
    <td>33.30%</td>
    <td>23.80%</td>
    <td>31.73%</td>
  </tr>
</table>


## Future Work
I would train a separate model for each product in each store, resulting in a total of 500 models (50 products * 10 stores). This approach allows for capturing the specific characteristics of sales for each product in each store, which will improve the accuracy of the forecasts.
I would use models like XGBoost or Prophet, as they have shown the best performance. Additionally, I would fine-tune each model to achieve better results and reduce the percentage of error. From the residual analysis, we also see that there are lags that contain information not accounted for by the model.
