# Titanic Dataset Analysis with Pandas

## Overview

This project provides a comprehensive analysis of the Titanic dataset using pandas for data manipulation, cleaning, and exploratory data analysis. The assignment focuses on real-world data tasks including missing value handling, feature engineering, aggregations, and insights generation.

## Approach

I structured the analysis into three progressive parts:

- **Part A (Basic)**: Data loading, inspection, and basic aggregations
- **Part B (Intermediate)**: Missing value imputation, text processing, and pivot tables
- **Part C (Advanced)**: Complex joins, outlier handling, and multi-step pipelines

## Key Assumptions and Choices

- Used median imputation for missing Age values grouped by Pclass and Gender for better accuracy
- Standardized passenger titles into major categories (Mr, Mrs, Miss, Master, etc.)
- Replaced fare outliers (top 1%) with 99th percentile values to reduce skewness
- Created family size and isolation features to capture social dynamics
- Applied "women and children first" hypothesis testing through survival rate analysis

## Files Included

- `titanic_pandas_assignment.ipynb` - Complete analysis notebook
- `train_cleaned.csv` - Preprocessed dataset ready for modeling
- `README.md` - This documentation file

## Dependencies

- pandas
- numpy
- matplotlib
- seaborn

## Key Findings

Gender, passenger class, and age group emerge as the strongest survival predictors, confirming historical accounts of maritime evacuation protocols during the Titanic disaster.
