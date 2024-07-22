# Forecasting Project

## Introduction

This project aims to develop a predictive model to forecast the number of taxi orders for the upcoming hour. This model will assist Sweet Lift, a taxi company, in attracting more drivers during peak hours and optimizing operational efficiency. The target is to achieve a root mean square error (RMSE) of 48 or less on the test set.

## Goal

The primary goal of this project is to create a machine learning model that can predict the number of taxi orders in the next hour with an RMSE value of less than 48.

## Project Steps

### Data Acquisition and Resampling

1. Download the dataset from the provided file path.
2. Resample the data to aggregate it on an hourly basis.

### Data Analysis

1. Perform a comprehensive analysis of the resampled data to identify patterns and trends.

### Model Training and Evaluation

1. Train various models with different hyperparameters to determine the most effective forecasting approach.
2. Ensure the test sample represents 10% of the original dataset.
3. Evaluate the model's performance using the test sample, ensuring the RMSE does not exceed 48.

## Data Description

The dataset includes historical taxi order data with the number of orders recorded in the `num_orders` column. This data will be utilized for resampling, analysis, and model training to predict future taxi order volumes.

- **Total Rows**: 26,496
- **Total Columns**: 1 (num_orders)
- **Time Interval**: 10 minutes

### Data Quality

- No missing values.
- No duplicated values.
- Consistent increase in orders from March to August 2018.

## Model Training and Evaluation

Several machine learning models were trained and evaluated on both train and test datasets. The performance of these models is summarized below:

### Train Dataset Results

- **Linear Regression Model**
  - RMSE (Train): 29.189
  - RMSE (Validation): 40.539

- **Random Forest Regressor Model**
  - Max Depth: None
  - RMSE (Train): 7.792
  - RMSE (Validation): 31.760

- **Light GBM Model**
  - RMSE (Train): 32.195
  - RMSE (Validation): 52.586

- **CatBoost Model**
  - RMSE (Train): 33.144
  - RMSE (Validation): 54.083

### Test Dataset Results

- **Linear Regression Model**
  - RMSE (Train): 30.489
  - RMSE (Test): 53.178

- **Random Forest Regressor Model**
  - Max Depth: None
  - RMSE (Train): 8.239
  - RMSE (Test): 46.198

- **Light GBM Model**
  - RMSE (Train): 34.461
  - RMSE (Test): 77.177

- **CatBoost Model**
  - RMSE (Train): 35.499
  - RMSE (Test): 80.164

## Conclusion

Based on the performance on the test dataset, the **Random Forest Regressor Model** with `n_estimators` set to 500 is the best model, achieving an RMSE of 46.198, which is below the target of 48.

## Recommendations

- **Implementation**: Deploy the Random Forest Regressor Model for real-time forecasting to optimize driver allocation during peak hours.
- **Future Improvements**: Further tuning of hyperparameters and exploring additional data preprocessing techniques to improve model performance.
