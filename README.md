# SALES FORECASTING 
# Overview
```bash
This project builds a complete pipeline for sales forecasting and analysis using advanced machine learning models.
It extracts and processes transactional sales data from SQL databases, applies feature engineering
and encoding, and trains regression models (XGBoost and LightGBM) to predict future sales.
The workflow emphasizes data-driven decision making for marketing, supply chain optimization, and discount strategies.
```
# Key Features 
``` bash
 - Automated Data Extraction from PostgreSQL using SQLAlchemy with .env for credentials.
 - Comprehensive Preprocessing including missing value handling, categorical encoding, and scaling.
 - Feature Engineering for temporal trends, discounts, and outlet-specific performance.
 - Regression Models: XGBoost and LightGBM tuned with GridSearchCV.
 - Performance Evaluation using MSE, RMSE, and R² metrics.
 - Visualization Dashboards for sales trends and forecast comparisons.
 - Branch & Brand-Level Forecasts to support hyper-local decision making.
```
# System Architecture 

<img width="1375" height="847" alt="diagram-export-8-29-2025-11_26_59-PM" src="https://github.com/user-attachments/assets/e00222b7-df40-4a63-9c1d-e430c27236c2" />

# Installation 
```bash
git clone <repo_url>
cd <repo_name>
```

# Workflow
1. Data Collection & Preprocessing
   - Gather sales, discounts, orders, AOV, weather, holidays, and temporal features.
   - Clean & transform (handle missing data, apply Box-Cox for skewed features).
2. Feature Engineering
   - Create lag features (last 7/14/30 days sales).
   - Add temporal features (day of week, month, season, holidays).
   - Integrate weather and event data.
 3. Model Training
    - Train ML models (XGBoost, LightGBM, LSTM, or ensemble).
    - Optimize with hyperparameter tuning.
4. Validation & Backtesting
   - Use rolling window backtesting to simulate real-world forecasting.
   - Evaluate using RMSE, MAPE, and business KPIs (forecast accuracy vs. demand planning).
5. Forecast Generation
   - Predict daily/weekly sales at city, zone, or outlet level.
   - Generate forecasts for both total sales and discounted vs. organic sales.
6. Business Integration
   - Feed forecasts into supply chain planning, discount strategy, and workforce allocation.
   - Compare actual vs. forecast for continuous improvement.

# Result and Performance 
# Sales Trends 
<img width="1721" height="702" alt="Screenshot 2025-05-27 183025" src="https://github.com/user-attachments/assets/17d3712d-aa5a-4cad-9bd5-b5158129e737" />

# Model Results 
The models provide highly accurate outlet-level forecasts.
Examples:
 - Wraps Kathi Roll (Nfc) – Predicted: 14,166, Actual: 13,972 (≈1.4% error).
 - BBK Amritsar North Punjab – Predicted: 31,022, Actual: 31,603 (≈1.8% error).
![WhatsApp Image 2025-08-30 at 00 05 32_b70409a7](https://github.com/user-attachments/assets/02cf33d8-1242-4fb9-abff-fe672de35d2e)

# Performance Metrics 
 - Mean Squared Error (MSE): Low values across branches show minimal variance between predicted and actual sales.
 - Root Mean Squared Error (RMSE): Within an acceptable error band, indicating reliable short-term forecasts.
 - R² Score (Coefficient of Determination): Close to 0.9+, showing the models explain a large portion of sales variance.

# Future Improvements 
1. Real-Time Forecast Adjustments
   - Shift from batch daily forecasts to near real-time updates (e.g., during big events or promotions).
   - Business Value: Dynamic discount and fleet allocation to capture demand spikes.
2. Profit-Weighted Forecasting
   - Instead of just predicting sales, predict profitability-adjusted sales.
   - Business Value: Ensures forecasts guide decisions that actually improve margins, not just volumes.
3. Forecast Explainability
   - Use SHAP or feature importance plots to show why sales will increase/decrease.
   - Business Value: Builds trust with decision-makers by linking forecast to drivers (e.g., “Rainy weather + Friday = +12% demand”).

