
# KKBOX Churn Prediction Pipeline

This project is part of the KKBOX Churn Prediction competition hosted on Kaggle in conjunction with the 11th ACM International Conference on Web Search and Data Mining (WSDM 2018). The goal is to build an algorithm that predicts whether a subscription user will churn using a donated dataset from KKBOX.
https://www.kaggle.com/c/kkbox-churn-prediction-challenge

## Project Overview

Accurately predicting customer churn is crucial for subscription-based businesses like KKBOX, Asia’s leading music streaming service. The ability to forecast whether a user will renew or cancel their subscription helps in formulating strategies to retain customers and maximize profits.

In this competition, the task is to predict whether a user will churn after their subscription expires, using various user behaviors and transaction data.

## Dataset

The dataset includes several files:

- ` train_v2.csv`: Training data with user ids and churn labels.
  - `msno`: User ID
  - `is_churn`: Target variable; `1` indicates churn, `0` indicates renewal

- `transactions_v2.csv`: Contains transaction details of users.
  - `msno`: User ID
  - `payment_method_id`: Payment method
  - `payment_plan_days`: Length of the membership plan in days
  - `plan_list_price`: Plan list price in New Taiwan Dollar (NTD)
  - `actual_amount_paid`: Actual amount paid in NTD
  - `is_auto_renew`: Whether the membership is auto-renewed
  - `transaction_date`: Date of the transaction
  - `membership_expire_date`: Membership expiration date
  - `is_cancel`: Indicates if the user canceled the membership

- `user_logs_v2.csv`: Daily user logs describing listening behaviors.
  - `msno`: User ID
  - `date`: Date of the log entry
  - `num_25`: Number of songs played less than 25% of the song length
  - `num_50`: Number of songs played between 25% and 50%
  - `num_75`: Number of songs played between 50% and 75%
  - `num_985`: Number of songs played between 75% and 98.5%
  - `num_100`: Number of songs played over 98.5%
  - `num_unq`: Number of unique songs played
  - `total_secs`: Total seconds played

- `members_v3.csv`: Contains user information.
  - `msno`: User ID
  - `city`, `bd`, `gender`, `registered_via`: User demographics
  - `registration_init_time`: User registration time

## Project Pipeline

The project involves the following steps:

1. **Data Preprocessing**: Cleaning and transforming the data to handle missing values, outliers, and feature engineering.
2. **Feature Engineering**: Creating new features based on user behavior and transaction history.
3. **Model Training**: Using machine learning models to predict churn.
4. **Evaluation**: Measuring the model performance using appropriate metrics.

## Tools
- **Python**: For data analysis and clustering (libraries like Pandas, NumPy, Scikit-Learn).
- **Jupyter Notebook**: For documenting the analysis and results.
- **Matplotlib**: For creating visualizations and plots.
- 


## Results

- Achieved an accuracy of over 90% in predicting user churn using lightGBM.
- Used feature importance analysis to understand the impact of various features on churn prediction. Permutation importance and surrogate model show that `membership_expire_day` is the most important feature.


