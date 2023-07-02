# Credit Card Fraud Detection

## What is Credit Card Fraud?
Credit card fraud is when someone uses another person's credit card or account information to make unauthorized 
purchases or access funds through cash advances. Credit card fraud doesn’t
just happen online; it happens in brick-and-mortar stores, too. As a business owner, you can avoid serious headaches – and unwanted publicity – 
by recognizing potentially fraudulent use of credit cards in your payment environment.

## Three challenges surrounding credit card fraud:
1. It's not always easy to agree on the ground truth for what "fraud" means.<br>
2. Regardless of how you define ground truth, the vast majority of charges are not fraudulent.<br>
3. Most merchants aren't experts at evaluating the business impact of fraud.<br>

## Dataset:
### In the context of the credit card fraud dataset, the terms represent the following features:

Time: The number of seconds elapsed between the current transaction and the first transaction in the dataset. This feature can be used to analyze any temporal patterns or trends in the data.<br>

V1 to V28: These are anonymized numerical features resulting from a dimensionality reduction technique, such as PCA (Principal Component Analysis), applied to the original credit card transaction data. The actual meaning of these features is not disclosed due to confidentiality reasons.<br>

Amount: The transaction amount, representing the monetary value of the transaction made using the credit card.<br>

Class: This is the target variable or the label indicating whether a transaction is fraudulent or not. It is a binary variable, where 1 represents a fraudulent transaction and 0 represents a non-fraudulent transaction.<br>

The V1 to V28 features are transformed versions of the original features to protect the privacy of the individuals involved in the transactions. These transformed features are often used in credit card fraud detection models to identify patterns and anomalies associated with fraudulent transactions while preserving data privacy.<br>

## Problem Statement:
The Credit Card Fraud Detection Problem includes modeling past credit card transactions with the knowledge of the ones that turned out to be fraud. This model is then used to identify whether a new transaction is 
fraudulent or not. Our aim here is to detect 100% of the fraudulent transactions while minimizing the incorrect fraud classifications.

## Observations:
1. Very few transactions are actually fraudulent (less than 1%). The data set is highly skewed, consisting of 492 frauds in a total of 284,807 observations.
2. This resulted in only 0.172% of fraud cases. This skewed set is justified by the low number of fraudulent transactions.
The dataset consists of numerical values from the 28 ‘Principal Component Analysis (PCA)’ transformed features, namely V1 to V28. Furthermore, there is no metadata
 about the original features provided, so pre-analysis or feature study could not be done.<br>
4. The ‘Time’ and ‘Amount’ features are not transformed data.<br>
5. There is no missing value in the dataset.<br>
   
## Why does class imbalance affect model performance?
In general, we want to maximize the recall while capping FPR (False Positive Rate), but you can classify a lot of charges wrong and still maintain a low FPR because you have a large number of true negatives.
This is conducive to picking a relatively low threshold, which results in high recall but extremely low precision.

## What is the catch?
Training a model on a balanced dataset optimizes performance on validation data.
However, the goal is to optimize performance on the imbalanced production dataset. You ultimately need to find a balance that works best in production.
One solution to this problem is: Use all fraudulent transactions, but subsample non-fraudulent transactions as needed to hit our target rate.

## Business questions to brainstorm:
Since all features are anonymous, we will focus our analysis on non-anonymized features: Time, Amount<br>
<br>How different is the amount of money used in different transaction classes?<br>
Do fraudulent transactions occur more often during certain frames?
