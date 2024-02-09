+++
title = 'Supply Chain Demand Forecasting'
date = 2023-10-22
draft = false
tags = ['python', 'forecasting', 'supply', 'ml']
description = 'How to implement demand forecasting in the supply chain using python'
ShowToc = true
+++

Predict future demand based on historical data
## Forecasting Techniques

### Time-Series Forecasting
Uses past data to predict future demand.
Assumes that the future will follow the same pattern as the past.
Most common method is the **Moving Average Method**.

#### Moving Average Method
Calculated the average of the past n observations, where n is a user defined parameter.
The forecast for the next period is then calculated by taking the average of the last n observations.

### Regression Analysis

Regression analysis is  a statistical method used to determine the 
relationship between a dependent variable and a one or more independent
variables.

Used to determine the relationship between demand and factors such as price, promotions, and seasonality.
Most common regression is the **linear regression model**.

### Machine Learning
Machine learning algorithms can be used to predict future demand based on historical data and other factors such as seasonality, promotions, and weather.
Most common machine learning algorithms are: **decision trees**, **random forests**, and **neural networks**.

[Credit](https://houtman80.medium.com/how-to-implement-demand-forecasting-in-the-supply-chain-using-python-849fa835bd9f)



