## Fraud Detection & Credit Card Analysis Notebooks

This repository contains Jupyter notebooks that focus on exploratory data analysis (EDA) and feature engineering for fraud detection tasks. The datasets used include Fraud_Data.csv for e-commerce transactions and creditcard.csv for credit card transactions. The notebooks are structured to guide the user from data cleaning to feature-rich datasets ready for machine learning modeling.

Notebooks Overview
1. EDA-Fraud.ipynb

Performs data cleaning: missing value imputation, duplicates removal, and datatype correction.

Conducts exploratory data analysis: univariate and bivariate analysis, target class distribution, and visualization of key features.

Integrates IP-to-country mapping to analyze geographic fraud patterns.

Engineers time-based and user-behavior features such as time since signup, hour of day, day of week, transaction count, and average time between purchases.

Saves a cleaned and enriched dataset (fraud_cleaned.csv) for modeling.

2. EDA-CreditCard.ipynb

Loads and explores the creditcard.csv dataset.

Conducts summary statistics, class distribution checks, and visualizations of transaction features.

Analyzes relationships between anonymized PCA components (V1–V28) and fraud occurrence.

Highlights the extreme class imbalance inherent in credit card fraud detection.

3. Feature-Engineering.ipynb

Combines the cleaned Fraud_Data.csv and creditcard.csv datasets for feature engineering tasks.

Scales numerical features (e.g., purchase_value, age, Amount) using StandardScaler.

Encodes categorical variables using one-hot encoding.

Handles class imbalance with undersampling and a custom SMOTE-like oversampling approach on training data.

Produces feature-rich, ready-to-use datasets for model training and evaluation.