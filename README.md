Predicting Fraudulent Transactions

Project Overview

This project focuses on developing a machine learning model to predict fraudulent transactions for a financial company. The dataset consists of 6,362,620 rows and 10 columns, available in CSV format. The model aims to detect fraudulent activities and provide insights for preventing financial fraud.

Data Dictionary

step: Represents time units, where each step corresponds to one hour (total 744 steps for 30 days).

type: Type of transaction (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER).

amount: Transaction amount in local currency.

nameOrig: Customer initiating the transaction.

oldbalanceOrg: Initial balance before the transaction.

newbalanceOrig: New balance after the transaction.

nameDest: Recipient of the transaction.

oldbalanceDest: Initial balance of the recipient (no data for merchants).

newbalanceDest: New balance of the recipient (no data for merchants).

isFraud: Indicator of fraudulent transactions within the simulation.

isFlaggedFraud: Flags transactions where illegal attempts are detected (e.g., transfers over 200,000 in a single transaction).

Performance Metric

Given the highly imbalanced dataset (99% non-fraud, 1% fraud), we use the Area Under the Precision-Recall Curve (AUPRC) instead of the traditional AUROC. AUPRC effectively evaluates the model's ability to detect rare fraudulent transactions by focusing on positive examples.

Machine Learning Approach

To handle imbalanced data, various strategies were considered:

Undersampling: Removing majority class samples, but this discards crucial information, leading to poor performance on real-world data.

Oversampling: Using the Synthetic Minority Oversampling Technique (SMOTE) to generate synthetic fraudulent examples.

Ensemble Decision Trees: The best results were obtained using XGBoost, a gradient-boosting algorithm that inherently performs well on imbalanced data. XGBoost allows for:

Handling missing values.

Parallel processing for efficiency.

Assigning higher weight to the minority (fraud) class to compensate for data imbalance.

Conclusion

This project builds a robust fraud detection model using XGBoost and AUPRC as the evaluation metric. By leveraging decision tree ensembles and handling imbalanced data effectively, the model improves fraud detection accuracy and provides actionable insights to mitigate financial risks.
