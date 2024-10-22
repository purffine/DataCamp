# House Price Prediction

## Project Overview

This project aims to build models for predicting house sale prices based on a dataset of house features. Two different models are developed and compared:

* **Model 1:**  Linear Regression using a subset of numerical features.
* **Model 2:**  Decision Tree Regressor using all available features with one-hot encoding for categorical variables.

## Data

The project uses a dataset named `house_sales.csv` provided by DataCamp that recorded the real estate data from RealAgents at specific year. The data contains the following features:

- `house_id`: Unique identifier for each house
- `city`: City where the house is located
- `sale_date`: Date of the sale
- `sale_price`: Sale price of the house (target variable)
- `bedrooms`: Number of bedrooms
- `area`: Area of the house in square meters
- `months_listed`: Number of months the house was listed before selling
- `house_type`: Type of house (e.g., Detached, Semi-detached, Terraced)

## Data Cleaning and Preprocessing

The `clean_data()` function performs the following cleaning and preprocessing steps:

- Handles missing values:
    - Replaces missing `city` values with "Unknown"
    - Removes rows with missing `sale_price`
    - Replaces missing `sale_date` with "2023-01-01"
    - Fills missing `months_listed` and `bedrooms` with their respective means
    - Replaces missing `house_type` with the mode 
- Standardizes `house_type` abbreviations (e.g., "Det." to "Detached").
- Removes units from the `area` column and converts it to a float.
- Converts `sale_date` to a datetime object and extracts numerical features (year, month, day).

## Feature Engineering

- The `sale_date` column is split into `sale_year`, `sale_month`, and `sale_day` for potential use in the models. 

## Model Building and Evaluation

- **Model 1 (Linear Regression):** 
    - Features: `bedrooms`, `area`, `months_listed`
- **Model 2 (Decision Tree Regressor):**
    - Features: All features, including one-hot encoded `city` and `house_type` 

- The models are trained on a training set and evaluated on a separate validation set (80/20 split). 

## Code Structure

- **`clean_data(df)`:**  Cleans and preprocesses the input DataFrame.
- **`model_1()`:**  Trains and evaluates the Linear Regression model.
- **`model_2()`:**  Trains and evaluates the Decision Tree Regressor model.

## How to Use

1. **Place the `house_sales.csv` file in the project directory.**
2. **Run the Python script.**

## Future Work

- Explore more feature engineering techniques (e.g., polynomial features, interactions).
- Hyperparameter tune the models to improve performance.
- Evaluate different regression models (e.g., Random Forest, Gradient Boosting).
