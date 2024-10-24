# Credit Risk Modeling Project

## Overview

This project focuses on developing a credit risk model to help banks accurately assess borrowers' creditworthiness and mitigate risks associated with loan defaults. Given the rising default rates driven by economic instability and volatile markets, this project leverages two datasets (an internal product dataset and bureau dataset) to predict the likelihood of loan approval, with users being categorized into four priority levels: `P1`, `P2`, `P3`, and `P4`.

## Datasets

1. **Internal Product Dataset**: Contains 25 features related to user demographics, transaction history, and financial behavior.
2. **Bureau Dataset**: Contains 61 features consisting of credit data collected and maintained by credit bureaus.

The two datasets were merged based on common columns, and the target variable is `Approved_flag`, which assigns priority levels to users.

## Project Workflow

### 1. **Domain Knowledge**
   - Gained insights into the credit risk domain before starting the modeling process, ensuring relevant features were included for better predictions.

### 2. **Data Preprocessing**
   - Merged the two datasets on common columns.
   - Handled missing values and outliers.
   - Performed data cleaning to ensure consistency across both datasets.

### 3. **Feature Selection**
   - **Chi-Square Test**: Used to check the association of categorical columns with the target variable.
   - **Variance Inflation Factor (VIF)**: Applied to check multicollinearity among the 76 numerical columns. Features with a VIF score above the threshold (6) were removed, reducing the number of numerical features to 39.
   - **ANOVA**: Conducted to test the association of the remaining numerical features with the target variable. Two columns were rejected, leaving 37 numerical columns.

### 4. **Encoding**
   - **Categorical Encoding**: Applied on categorical features to convert them into a format suitable for machine learning algorithms.
   - **Ordinal Encoding**: Performed on the `Education` feature due to its ordered nature.

### 5. **Model Training**
   - Trained three machine learning models:
     1. **XGBoost**
     2. **Random Forest**
     3. **Decision Trees**
   - XGBoost performed the best in terms of accuracy.
   - Standard Scaler and Label Encoding were applied for further fine-tuning, but no significant improvement was observed in the metrics.

### 6. **Hyperparameter Tuning**
   - Hyperparameter tuning was performed using **GridSearchCV** to determine the optimal settings for XGBoost, improving its performance further.

### 7. **Model Deployment**
   - Applied the tuned model on unseen data.
   - Calculated the bank's risk appetite and provided recommendations for user prioritization (P1, P2, P3, P4) based on their creditworthiness.

## Results
The XGBoost model, after hyperparameter tuning, achieved the best accuracy for predicting the `Approved_flag`. The model can now be used to aid the bank in making informed lending decisions while minimizing the risk of defaults.

