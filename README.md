# Telecom Churn Case Study

## Problem Statement

## Business Problem Overview

The telecom industry is highly competitive, with an annual churn rate of 15-25%, making customer retention more critical than acquisition.

It costs 5-10 times more to acquire a new customer compared to retaining an existing one.

Retaining high-profit customers is a top priority for incumbent telecom operators.

To reduce churn, telecom companies must predict which customers are at high risk of leaving.

This project involves analyzing customer-level data from a leading telecom firm, building predictive models, and identifying key churn indicators.

## Understanding and Defining Churn

In the telecom industry, two main payment models exist: postpaid (monthly/annual billing after service use) and prepaid (advance payment for service use).

In the postpaid model, customers inform the operator when switching, indicating churn. In prepaid, customers can stop using services without notice, making churn prediction challenging.

Churn prediction is crucial for prepaid customers, and defining 'churn' is essential. Prepaid is common in India and Southeast Asia, while postpaid prevails in Europe and North America. This project focuses on the Indian and Southeast Asian markets.


## Data Preparation

It is done using following steps:
- Handling null values
- Dropping columns (Date column, column with only 1 unique value, mobile number, circle id and columns with null values > 35%)
- Getting high value customers using derived variables
- Tagging churn customers (Class imbalance check)
- Handling outliers for numerical columns
- Extracting useful insights using EDA
- Checking correlation matric for all data month-wise
- Tenure analysis

## Modelling

- Data is pre-processed with train-test split (80-20%) and SMOTE (Synthetic Minority Oversampling Technique) is used to handle data imbalancing
- Feature has been scaled using standard scaler
- 3 basic models are created:
    1) Basic logistic regression with RFE (30 features)
    2) Decision Trees (With max depth = 4)
    3) Basic random forest mode (With max depth = 4)

- Optimized random forest model is tried with grid search cv with different values of max depth, n estimators, max features and min samples leaf
- On training set, accuracy value is close to 97% and there is also high value for all the other evaluation measures like specificity, sensitivity, precision, recall and F1-score with all values in range (96 - 97%)

## Evaluating model on the test set
- Final model has overall accuracy around 92% on the test dataset and it also has high specificity value around 94%. Sensitivity is also comparatively good with value around 64%.
- Precision value is close to 38% whereas recall value is close to 64%. And F1 score is close to 48%.

## Business Insights
- Few high-value customers are churning, but there have been no new high-value customers onboarded in the last 6 months, which is concerning.
- Customers with less than 4 years of tenure are more likely to churn, so the company should focus on this segment and introduce new schemes.
- Average revenue per user is a crucial factor in predicting churn.
- Strong indicators of churn behavior include:
  - Incoming and outgoing calls on roaming in the 8th month.
  - Local outgoing calls made to landline, fixedline, mobile, and call center.
  - Better 2G/3G area coverage, especially in areas with poor 2G/3G services.