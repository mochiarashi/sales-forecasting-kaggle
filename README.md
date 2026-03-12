# sales-forecasting-kaggle
Time series forecasting using ETS, CatBoost, MLP, and ensemble models on the Kaggle Predict Future Sales dataset
# Retail Sales Forecasting (Kaggle Predict Future Sales)

## Project Overview
This project tackles the Kaggle “Predict Future Sales” challenge, which requires forecasting the next month’s sales for every item–store combination using historical retail data.

The dataset contains daily sales records from January 2013 to October 2015. Because the prediction target is monthly sales, the data was aggregated into monthly time series.

The project evaluates multiple forecasting approaches and demonstrates how hybrid modeling can improve prediction accuracy.

## Dataset
The dataset includes:

- Historical daily sales records
- Item IDs
- Shop IDs
- Item categories

Due to extreme sparsity in item–shop sales combinations, missing combinations were explicitly filled with zero values to maintain time-series continuity.

## Feature Engineering
Several features were engineered to improve predictive performance:

- Lag features (1–3 months)
- Rolling averages (3-month and 6-month)
- Rolling maximum values
- Time features (year, month, day-of-year)
- Category-level and shop-level aggregated sales

Target values were clipped at 20 according to Kaggle competition guidelines.

## Models Implemented

### 1. ETS Model
A classical Exponential Smoothing model applied to aggregated total monthly sales.

### 2. CatBoost Model
A gradient boosting decision tree model well-suited for tabular data and categorical variables.

### 3. MLP Neural Network
A feedforward neural network trained on scaled numerical features.

### 4. Ensemble Model
A hybrid model combining CatBoost and MLP predictions with equal weights.

## Results

Model comparison on validation data:

| Model | RMSE | MAE |
|------|------|------|
| ETS | 6432.19 | 5310.79 |
| CatBoost | 8.10 | 1.76 |
| MLP | 8.31 | 1.37 |
| Ensemble | **7.90** | **1.25** |

The ensemble model achieved the best performance, demonstrating that combining machine learning and neural models improves forecasting accuracy.

## Key Insights

- Classical time series models capture seasonality but lack item-level granularity.
- Tree-based models perform well on sparse retail data.
- Neural networks provide smoother predictions.
- Hybrid ensembles combine the strengths of both approaches.

## Skills Demonstrated

- Python
- Time Series Forecasting
- Feature Engineering
- CatBoost
- Neural Networks (MLP)
- Ensemble Modeling
- Retail Data Analytics

## Files

- `sales_forecasting.ipynb` – full modeling pipeline
- `Chenhuan Ji pafinal.pptx` – project presentation

## Author

Chenhuan Ji  
Boston College  
MS Applied Economics & Applied Analytics
