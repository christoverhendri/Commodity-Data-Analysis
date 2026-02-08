# 🛒 Commodity Price Prediction: Statistical & Machine Learning Approach

This project provides a comprehensive framework for analyzing and forecasting the prices of essential food commodities. By combining classical statistical models (ARIMA, SARIMAX) with modern machine learning algorithms (XGBoost, Random Forest, and LightGBM), this repository aims to mitigate the risks associated with food price volatility.

## 📈 Project Overview
Food price fluctuations significantly impact inflation and economic stability. This study provides accurate forecasts to assist policymakers, businesses, and consumers in decision-making and supply chain risk management.

## 📊 Exploratory Data Analysis (EDA) & Insights
Based on the analysis of the commodity dataset, several key patterns were identified:
* **Temporal Dependency**: Commodity prices exhibit strong seasonal trends and daily fluctuations.
* **Regional Disparity**: The same commodity often shows vastly different price floors and ceilings depending on the geographical location.
* **Data Consistency**: Identified specific price ranges (minimum and maximum boundaries) for each unique commodity to detect market anomalies.
* **Missing Value Management**: Addressed significant gaps in reporting through a systematic `ffill` (forward fill) strategy to maintain time-series continuity.



## 🛠️ Data Preprocessing Pipeline
* **Automated Integration**: Unified fragmented CSV files from multiple regional sources into a master dataset (`merged_commodities.csv`).
* **Feature Engineering**: Extracted temporal features and handled outliers by capping prices based on identified commodity-specific ranges.
* **Cleaning & Validation**: Developed a dedicated cleaning script for test data to ensure alignment with the training schema (`test_clean.csv`).

## 🧠 Model Architecture
The project leverages a hybrid approach to capture both linear trends and complex non-linear relationships:
1. **Statistical Models**: ARIMA and SARIMAX for capturing auto-regressive properties and seasonality.
2. **Machine Learning**: XGBoost and Random Forest to capture multi-dimensional relationships within the data.
3. **Ensemble Strategy**: The final prediction is generated through a **Multi-Model Ensemble** that averages results from four distinct sub-models to ensure stability and reduce variance.

## 📉 Results & Outputs
* **Ensemble Averaging**: Combined sub-model predictions using an arithmetic mean while skipping missing values to maintain robustness.
* **Final Refinement**: Performed post-ensemble imputation to ensure a 100% complete prediction set for the final output.
* **Artifacts**: The process successfully generates a `submission_final_ensemble.csv` containing the optimized price forecasts.
