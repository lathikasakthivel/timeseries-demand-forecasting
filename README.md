# Time-Series Demand Forecasting
## Overview
In this task, we will be estimating how much a particular combination of store and item will sell each day based on previous daily sales numbers over time. Accurate estimating will allow a business to manage their inventory, use their resources effectively and minimize the risk of experience stock-outs or carrying excess inventory. The objective of this project is to utilize existing historical product sales data to forecast the next two weeks of daily sales for the same product using both basic and advanced methodologies.
## Dataset
The dataset contains daily sales records with the following fields:
- date:transaction date  
- store:store identifier  
- item:product identifier  
- sales:number of items sold on that day  
## Data Preparation
The following preprocessing steps were applied:
   ->Converted the date column into datetime format and sorted chronologically
   ->Created a continuous daily timeline to detect missing dates
   ->Filled missing values using interpolation
   ->Set date as index for time-series analysis
## Exploratory Time-Series Analysis
The dataset was analyzed to understand trend and seasonal patterns.
Steps performed
  Demand visualization over time,
  Seasonal decomposition with weekly seasonality,
  Observation of repeating demand cycles.
## Findings
The series shows clear weekly seasonality and demand fluctuates regularly rather than randomly,suitable for seasonal forecasting models.
## Models Implemented
->Naive Forecast (Baseline):Assumes future demand equals the last observed value , used as a benchmark to compare improvements.
->Moving Average Model:Uses a 7-day rolling mean to smooth short-term fluctuations and capture local trends.
->SARIMA Model (Improved Model):Seasonal AutoRegressive Integrated Moving Average,this model captures trend,seasonality,temporal dependence.
## Model Evaluation
Performance was measured using:
  ->MAE (Mean Absolute Error)
  ->RMSE (Root Mean Squared Error)
Naive:MAE 6.85 RMSE 8.08  ,  Moving Average:MAE 4.24 RMSE 5.47  ,  SARIMA:MAE 3.93 RMSE 5.28

The SARIMA model achieved the lowest error and was selected as the final model.
## Future Forecast
The final model was then trained on the entire data set and used to predict the next 14 days of demand.  
The forecast plots are available in the notebook.
## Conclusion
Time-series demand forecasting improves significantly when seasonal behavior is modeled.  
Baseline methods provide a reference point, while SARIMA captures real patterns in sales data and produces more reliable predictions.  
Such forecasting can support operational planning and inventory management in real-world systems.
