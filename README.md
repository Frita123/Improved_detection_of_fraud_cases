# Improved_detection_of_fraud_cases
Task 1 – Data Analysis, Cleaning, and Feature Engineering
Overview

This task focuses on preparing two datasets for modeling by performing data cleaning, exploratory data analysis (EDA), feature engineering, and class imbalance handling. The datasets included are:

Fraud Dataset (Fraud_Data.csv) – e-commerce transaction data with user, device, and transaction information.

Credit Card Dataset (creditcard.csv) – anonymized financial transactions from a credit card dataset with severe class imbalance.

Key Steps
Fraud Dataset

Data Cleaning: handled missing values, removed duplicates, corrected datatypes.

EDA: analyzed univariate and bivariate distributions, visualized class imbalance, and quantified fraud patterns.

Geolocation Integration: converted IP addresses to integers and mapped them to countries to analyze fraud distribution by location.

Feature Engineering: created time-based features (time_since_signup, hour_of_day, day_of_week) and transaction frequency features (user_transaction_count, avg_time_between_tx).

Data Transformation: scaled numerical features and encoded categorical features.

Class Imbalance Handling: applied undersampling and SMOTE-like oversampling to training data.

Output: cleaned and feature-rich dataset saved as fraud_cleaned.csv.

Credit Card Dataset

Data Cleaning: removed duplicates and verified missing values and datatypes.

EDA: visualized class distribution, transaction amounts, and time features; performed correlation analysis on anonymized PCA features.

Class Imbalance Awareness: noted extreme imbalance (<0.2% fraud), to be addressed during model training.

Output: cleaned dataset saved as creditcard_cleaned.csv.