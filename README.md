# Stock Market Prediction Competition

## Overview

This Repository is our submission to the Data Analytics Hackathon, part of the Data Analytics Course 2023, PES University. 

Find a very well documented IPYNB, in which  we perform :
- Data preprocessing
- Exploratory data analysis
- Plot correllation plots, PACF-ACF plots, Time series analysis ,etc...
- MODEL 1 => Forecasting using SARIMAX
- MODEL 2 => XGBOOST REGRESSOR-CLASSIFIER COMBO
- MODEL 3 => XGBOOST CLASSIFIER - CLASSIFICATION
- Feature Engineering from existing data

Head to the IPYNB for more info!



## Problem Staement - Description

### Stock Market Prediction

Predicting stock market performance involves forecasting the future value of a specific stock, a particular sector, or the overall market. This service is highly sought after by companies looking to capitalize on their stock's trends for profit. However, it's a challenging task due to the stock market's sensitivity to various global factors, leading to its unpredictability and volatility. Investment banks play a crucial role in assisting companies, individuals, and governments in financial transactions.

### Your Task

Your team works at a very large investment firm called Dane Street. Your clients are High Net-worth Individuals (HNIs) looking to build wealth that will last them a lifetime and more.

Your team has identified a stock that seems to be performing well, and your clients want to know more before they commit their millions to your call. Thus your task is two-fold:
1. Predict the close prices of the stock in question.
2. Suggest the best strategy for your client on any given day: Buy, Hold, or Sell the stock.

Your team needs to suggest the best decision.

## Evaluation

### Evaluation Metric

This competition requires you to submit two variables: the close price and the strategy for that particular day (Buy, Sell, Hold). Each of these is evaluated differently.

#### Close Price Evaluation

The close price will be evaluated using the Symmetric Mean Absolute Percentage Error (SMAPE). 

The Symmetric Mean Absolute Percentage Error (SMAPE) is calculated as:

\[ \text{SMAPE} = \frac{100\%}{n} \sum_{t=1}^{n} \frac{|F_t - A_t|}{(|F_t| + |A_t|)} \]

To calculate this yourself, use the following piece of code:

```python
smape = np.mean(np.abs(y_pred - y_true) / (np.abs(y_pred) + np.abs(y_true)))
```

### Strategy Evaluation
The strategy will be evaluated using Accuracy. To calculate this yourself, use the following piece of code:

```python
accuracy = sklearn.metrics.accuracy_score(y_true, y_pred) * 100
```
However, the metric which we use will be (1 - Accuracy), which is effectively a loss metric. Make sure to measure yourself by 1 - Accuracy.

Final Score
The final score is a weighted sum of the two metrics. The lower the score, the better you're doing in the competition!
