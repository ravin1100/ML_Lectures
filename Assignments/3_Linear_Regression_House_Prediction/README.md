# California Housing Price Prediction - Linear Regression Assignment

## Objective

Build and evaluate a linear regression model to predict house prices using the California Housing dataset.

## Dataset

- **Source:** Kaggle California Housing Prices
- **Samples:** 20,640
- **Features:** 8 (plus target)
- **Target:** Median house value (in US Dollars)

## Solution Overview

This notebook walks through the following steps:

### 1. Data Exploration

- Loaded the dataset (`housing.csv`) using pandas.
- Inspected data structure, types, and summary statistics.
- Checked for missing values and outliers.
- Visualized feature relationships using correlation heatmaps, boxplots, and pairplots.

### 2. Data Preprocessing

- Handled missing values in `total_bedrooms` by imputing with a ratio-based approach.
- Created new features (e.g., `room_bedroom_ratio`).
- Encoded categorical variable `ocean_proximity` using both binary and one-hot encoding.
- Applied MinMax scaling to numerical features.
- Dropped unnecessary columns after encoding and feature engineering.

### 3. Model Implementation

- Split the data into training (80%) and testing (20%) sets.
- Implemented Linear Regression using scikit-learn.
- Trained the model and made predictions on the test set.
- Compared performance with Ridge Regression (alpha=1.0).

### 4. Evaluation Metrics

- Calculated and compared the following metrics for both models:
  - Mean Absolute Error (MAE)
  - Mean Squared Error (MSE)
  - Root Mean Squared Error (RMSE)
  - R² Score

### 5. Analysis & Insights

- Identified important features using model coefficients.
- Discussed model limitations (e.g., linearity, feature selection, potential for more advanced models).
- Suggested improvements such as feature engineering, polynomial features, and trying other regression algorithms.

## How to Run

1. Open `main.ipynb` in Jupyter or VS Code.
2. Ensure required packages are installed: `pandas`, `numpy`, `scikit-learn`, `seaborn`, `matplotlib`.
3. Run all cells sequentially to reproduce the analysis and results.

## Key Files

- `main.ipynb`: Complete solution notebook
- `housing.csv`: Dataset file

---

**Author:** [Ravin Kumar Jangir]
**Date:** September 2025
