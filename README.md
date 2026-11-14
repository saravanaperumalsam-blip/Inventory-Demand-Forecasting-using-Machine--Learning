# Inventory Demand Forecasting using Machine Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white) ![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter&logoColor=white) ![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-F7931E?logo=scikitlearn&logoColor=white)

A machine learning project that predicts future product demand from historical sales data, so a business can keep the right amount of stock: enough to avoid running out, without tying up money in excess inventory.

> **Status:** work in progress. The notebook and dataset are being added. Sections marked _TODO_ will be filled in with the final results.

## Problem

Retailers and warehouses have to decide how much of each product to hold. Ordering too little leads to stock-outs and lost sales; ordering too much increases storage costs and waste. This project uses past sales to forecast demand per product (and per store) for upcoming days, which can then drive reorder decisions.

## Dataset

_TODO: add the dataset name, source link and size._

Expected columns:

| Column | Description |
|---|---|
| `date` | Day of the sale |
| `store` | Store ID |
| `item` | Product ID |
| `sales` | Units sold that day (target) |

## Approach

1. **Exploratory data analysis**: sales trends over time, seasonality by weekday and month, differences between stores and items.
2. **Feature engineering**
   - Date features: year, month, day, day of week, weekend flag, holidays
   - Lag features: sales 7, 14 and 28 days earlier
   - Rolling statistics: moving averages and standard deviations
3. **Train / validation split by time**: the model is validated on the most recent period, never on data from before its training window, to avoid leakage.
4. **Models compared**
   - Baseline: last value / moving average
   - Linear Regression
   - Random Forest Regressor
   - Gradient boosting (XGBoost / LightGBM)
5. **Evaluation metrics**: MAE, RMSE and MAPE on the validation period.

## Results

_TODO: replace with the final numbers from the notebook._

| Model | MAE | RMSE | MAPE |
|---|---|---|---|
| Baseline (moving average) | – | – | – |
| Linear Regression | – | – | – |
| Random Forest | – | – | – |
| XGBoost / LightGBM | – | – | – |

_TODO: add a chart of actual vs. predicted demand and the most important features._

## Project structure

```
├── Inventory_Demand_Forecasting_using_Machine_Learning_Python.ipynb   # Main notebook (TODO: add)
├── data/                                                              # Dataset (TODO: add or link)
├── app.py                                                             # Placeholder for a prediction app
├── requirements.txt                                                   # Python dependencies (TODO: add)
└── README.md
```

## Getting started

```bash
git clone https://github.com/saravanaperumalsam-blip/Inventory-Demand-Forecasting-using-Machine--Learning.git
cd Inventory-Demand-Forecasting-using-Machine--Learning
pip install pandas numpy scikit-learn xgboost matplotlib seaborn jupyter
jupyter notebook
```

Then open the notebook and run all cells.

## Tech stack

- **Python**: pandas, NumPy
- **Visualisation**: Matplotlib, Seaborn
- **Machine learning**: scikit-learn, XGBoost / LightGBM
- **Environment**: Jupyter Notebook

## Future improvements

- Time-series models such as Prophet or SARIMA for comparison
- Hyperparameter tuning with time-series cross-validation
- A simple web app (`app.py`) where a user picks a store and item and sees the forecast
- Turning forecasts into reorder-point and safety-stock recommendations

## Author

**Saravanaperumal**: [GitHub](https://github.com/saravanaperumalsam-blip)
