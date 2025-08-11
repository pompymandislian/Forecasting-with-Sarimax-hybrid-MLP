# Hybrid Forecasting Model Approach

This forecasting framework leverages a hybrid model combining **SARIMAX** and **MLP** to capture both linear and nonlinear patterns in time series data.

- **SARIMAX** is employed to model the linear and stationary components of the series, effectively handling trends, seasonality, and exogenous variables. However, SARIMAX assumes linearity and may not fully capture complex nonlinear dynamics.

- To address this limitation, the **MLP (Multi-Layer Perceptron)** model is trained on the residuals (errors) from the SARIMAX predictions. This step allows the MLP to learn and model the nonlinear relationships and patterns that SARIMAX cannot represent.

## Summary of Results

The hybrid model demonstrates strong performance on training and validation datasets, but underfitting is observed on the test set. This highlights the challenges of generalization and the complexity of the underlying data. The primary objective here is to illustrate the concept and methodology of hybrid modeling for time series forecasting.

## Implementation Steps

1. Fit the SARIMAX model to the original time series data and extract the residuals (difference between actual and predicted values).  
2. Train the MLP model using these residuals as the target, allowing it to capture the nonlinear components.  
3. Combine the SARIMAX predictions with the MLP’s residual forecasts to produce the final hybrid forecast.
