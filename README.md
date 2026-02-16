# Time-Series Demand Forecasting

## Overview
This task focuses on forecasting daily sales demand for a store–item combination using historical time-series data. Reliable demand prediction helps businesses plan inventory, allocate resources, and avoid stock shortages or overstocking.  The goal is to analyze past sales patterns and predict the next 14 days of demand using both baseline and advanced forecasting models.

---

## Dataset
The dataset contains daily sales records with the following fields:

- **date** – transaction date  
- **store** – store identifier  
- **item** – product identifier  
- **sales** – number of items sold on that day  

For modeling, a single store–item pair was selected to study time-series behaviour clearly.

---

## Data Preparation
The following preprocessing steps were applied:

- Converted the date column into datetime format and sorted chronologically
- Created a continuous daily timeline to detect missing dates
- Filled missing values using interpolation
- Set date as index for time-series analysis

---

## Exploratory Time-Series Analysis

The dataset was analyzed to understand trend and seasonal patterns.

### Steps performed
- Demand visualization over time
- Seasonal decomposition with weekly seasonality
- Observation of repeating demand cycles

### Findings
- The series shows clear weekly seasonality
- Demand fluctuates regularly rather than randomly
- Suitable for seasonal forecasting models

---

## Models Implemented

### 1. Naive Forecast (Baseline)
Assumes future demand equals the last observed value.  
Used as a benchmark to compare improvements.

### 2. Moving Average Model
Uses a 7-day rolling mean to smooth short-term fluctuations and capture local trends.

### 3. SARIMA Model (Improved Model)
Seasonal AutoRegressive Integrated Moving Average  
**SARIMA(1,1,1)(1,1,1,7)**

This model captures:
- trend
- seasonality
- temporal dependence

---

## Model Evaluation

Performance was measured using:
- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)

| Model | MAE | RMSE |
|------|------|------|
| Naive | 6.85 | 8.08 |
| Moving Average | 4.24 | 5.47 |
| SARIMA | 3.93 | 5.28 |

The SARIMA model achieved the lowest error and was selected as the final model.

---

## Future Forecast
The final model was trained on the full dataset and used to forecast the next 14 days of demand.  
Forecast plots are available in the notebook for visualization and interpretation.

---

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn

---

## Repository Contents
- Jupyter Notebook with complete workflow
- Dataset (train.csv)
- Model evaluation outputs
- Forecast visualizations
- README file

---

## Conclusion
Time-series demand forecasting improves significantly when seasonal behavior is modeled.  
Baseline methods provide a reference point, while SARIMA captures real patterns in sales data and produces more reliable predictions.  
Such forecasting can support operational planning and inventory management in real-world systems.
