# Bitcoin Price Prediction using ARIMA

This project demonstrates end-to-end time series forecasting of Bitcoin prices using ARIMA and SARIMA models in Python.  
The notebook provides a complete workflow: data cleaning, feature engineering, decomposition, model selection, prediction, interactive visualization, and accuracy evaluation.

---

## Project Overview

The goal is to model and forecast Bitcoin's monthly price trends by leveraging statistical time series techniques.  
Key highlights include:
- Handling real-world minute-level price data
- Data resampling and creation of new features
- Trend and seasonality decomposition
- Stationarity and transformation
- Model parameter tuning and grid search
- Forecast visualization with Plotly

---

##  Dataset

- **Source:** [Bitcoin Historical Data (Kaggle)](https://www.kaggle.com/datasets/mczielinski/bitcoin-historical-data)
- **File:** `btcusd_1-min_data.csv`
- **Description:**  
  This dataset contains minute-by-minute OHLCV (Open, High, Low, Close, Volume) data for Bitcoin, starting from **January 1, 2012**.  
  It provides **over 13.5 years of continuous price and volume data**, making it one of the most detailed long-term Bitcoin datasets available for model training and evaluation.

---

## Workflow & Methodology

### 1. **Data Loading & Preparation**
   - Load raw CSV data.
   - Convert Unix timestamps to readable datetime.
   - Set timestamp as index for resampling.

### 2. **Feature Engineering**
   - Calculate Weighted Price: average of High, Low, and Close.
   - Compute VWAP (Volume Weighted Average Price) for daily, monthly, quarterly, and yearly periods.

### 3. **Visualization**
   - Use Plotly to visualize price trends over different timeframes.
   - Create interactive multi-panel charts for daily, monthly, quarterly, and yearly data.

### 4. **Trend & Seasonality Analysis**
   - Apply STL decomposition to split price series into trend, seasonality, and residuals.

### 5. **Data Transformation & Stationarity**
   - Apply Box–Cox transformation to stabilize variance.
   - Use differencing (seasonal and regular) to achieve stationarity, validated with Dickey-Fuller tests.

### 6. **Autocorrelation Analysis**
   - Plot ACF and PACF to inform ARIMA/SARIMA parameter selection.

### 7. **Model Selection & Fitting**
   - Grid search over possible ARIMA/SARIMA parameter combinations.
   - Select the best model based on AIC (Akaike Information Criterion).

### 8. **Model Diagnostics**
   - Analyze model residuals to ensure assumptions are met.

### 9. **Forecasting**
   - Generate predictions for future months (e.g., up to January 2026).
   - Apply inverse Box–Cox transformation to revert predicted values to their original scale.
   - Visualize actual vs. predicted prices.

### 10. **Model Evaluation**
   - Split data into training and testing periods.
   - Compute forecast accuracy using MAPE (Mean Absolute Percentage Error).

---

##  Usage

1. **Clone this repository** and open the notebook in Jupyter:
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   jupyter notebook Bitcoin Price Prediction.ipynb
