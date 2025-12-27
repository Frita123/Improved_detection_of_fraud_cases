## Improved_detection_of_fraud_cases
#### Data Analysis, Cleaning, and Feature Engineering

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

#### Modeling and Evaluation

Overview
This task focuses on building, training, and evaluating classification models to detect fraudulent transactions using the cleaned datasets. Both baseline and ensemble models are implemented, with robust handling of class imbalance and cross-validation for reliable performance estimation.

Key Steps

Data Preparation

Split the cleaned dataset using stratified train-test split to preserve class distribution.

Separate features from the target variable (class).

Drop raw datetime columns and high-cardinality IDs (signup_time, purchase_time, device_id, ip_address).

Modeling

Baseline Model: Logistic Regression with class balancing, trained on undersampled data.

Ensemble Model: Random Forest with hyperparameter tuning (n_estimators, max_depth, min_samples_split) using Grid Search and Stratified K-Fold cross-validation (k=5).

Preprocessing: numerical features scaled with StandardScaler, categorical features one-hot encoded.

Evaluation

Metrics used: F1-score, AUC-PR, and confusion matrices.

Cross-validation scores reported to assess model stability and robustness.

Model comparison performed to select the best model for deployment.

Output

Performance metrics for both Logistic Regression and Random Forest models.

Visualizations: bar charts comparing F1-score and AUC-PR, precision-recall curves, and confusion matrices.

Best Random Forest model saved to the models/ folder as best_random_forest.pkl for reuse and deployment.

## Model Selection Justification

After training and evaluating both the Logistic Regression (baseline) and the Random Forest (ensemble) models, the **Random Forest model is selected as the best model** for the following reasons:

1. **Superior Performance Metrics**  
   - The Random Forest achieved higher **F1-score** and **AUC-PR** compared to Logistic Regression, indicating better balance between precision and recall. This is critical in fraud detection where missing fraudulent transactions can be costly.

2. **Robustness to Class Imbalance**  
   - Random Forest handles class imbalance effectively through ensemble learning. Cross-validation showed consistent AUC-PR scores across folds, demonstrating stable performance.

3. **Ability to Capture Non-linear Patterns**  
   - Fraud patterns are often complex and non-linear. Random Forest can model intricate feature interactions that a linear model like Logistic Regression cannot.

4. **Interpretability & Practicality**  
   - Feature importance from Random Forest provides insights into which features contribute most to fraud prediction.  
   - The model is saved as `best_random_forest.pkl` for deployment, ensuring practical usability.

**Conclusion:**  
Considering its **higher predictive performance, robustness, and interpretability**, the Random Forest is clearly the best choice for detecting fraudulent transactions in this dataset.
