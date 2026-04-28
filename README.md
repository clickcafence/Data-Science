Project Goal

1. Predict hourly bike rental demand.
2. Detect unusual demand spikes and drops.
3. Compare results across 2 independent datasets (Washington DC and Seoul).

Phase 1: Project Setup 

1. Define problem statement in 3-5 lines.
2. Download both datasets from UCI.
3. Create a short data dictionary for each dataset.
4. Confirm target variable:
5. DC dataset: cnt
6. Seoul dataset: Rented Bike Count

Phase 2: Data Cleaning and Standardization 
1. Load both datasets.
2. Parse date and hour fields.
3. Handle missing values (if any).
4. Standardize column names so both datasets share a common schema.
5. Keep core columns:
 datetime
 demand
 temperature
 humidity
 windspeed
 rainfall/snowfall
 holiday
 season

Phase 3: Exploratory Data Analysis

1. Plot demand over time.
2. Compare weekday vs weekend demand.
3. Compare seasonal demand.
4. Analyze weather effect on demand.
5. Write 5-7 key insights.

Phase 4: Feature Engineering

1. Create time features:
 hour
 day_of_week
 month
 is_weekend
2. Create lag features (for time dependency), like previous hour demand.
3. Create rolling mean features (for smoothing), for example 24-hour average.
4. Scale numeric features if model needs it.

 Phase 5: Forecasting Models

1. Build baseline model (Linear Regression or Random Forest Regressor).
2. Train and test on each dataset separately.
3. Evaluate with:
MAE
RMSE
4. Save prediction vs actual values.

Phase 6: Cross-Dataset Generalization 

1. Train on DC, test on Seoul.
2. Train on Seoul, test on DC.
3. Compare error increase/decrease.
4. Explain why transfer works or fails (climate, behavior, holidays, data differences).

Phase 7: Anomaly Detection Using Residuals 

1. Compute residual = actual - predicted.
2. Define anomaly rule:
abs(residual) > 2 or 3 standard deviations
Mark anomalies in timeline plots.
3. Categorize anomalies:
unexpected spike
unexpected drop
4. Discuss possible causes (weather extremes, holidays, events).

Phase 8: Final Report and Presentation 

1. Problem and motivation.
2. Dataset summary (prove 2 independent datasets used).
3. Methods used.
4. Main results and metric tables.
5. Anomaly examples with plots.
6. Limitations and future improvements.
