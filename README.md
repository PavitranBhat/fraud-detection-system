# Fraud Detection System

An end-to-end machine learning project for detecting fraudulent financial transactions using the PaySim simulated mobile-money transaction dataset.

## Project Objective

The objective of this project is to develop a machine learning system that can classify financial transactions as:

- `0` → Legitimate transaction
- `1` → Fraudulent transaction

The project focuses on exploratory data analysis, feature engineering, handling class imbalance, model development, evaluation, and eventually exposing the trained model through an API.

## Dataset

This project uses the PaySim simulated mobile-money transaction dataset.

The dataset contains:

- 6,362,620 transactions
- 11 original features
- 8,213 fraudulent transactions
- Highly imbalanced target variable

The raw dataset is not included in this repository because of its large file size.

## Dataset Features

| Feature | Description |
|---|---|
| `step` | Simulated time step; approximately one hour per step |
| `type` | Transaction type |
| `amount` | Transaction amount |
| `nameOrig` | Identifier of the transaction originator |
| `oldbalanceOrg` | Originator's balance before the transaction |
| `newbalanceOrig` | Originator's balance after the transaction |
| `nameDest` | Identifier of the transaction destination |
| `oldbalanceDest` | Destination balance before the transaction |
| `newbalanceDest` | Destination balance after the transaction |
| `isFraud` | Target variable indicating fraudulent transactions |
| `isFlaggedFraud` | Rule-based fraud flag provided by the dataset |

## Day 1 — Initial EDA

### Dataset Structure

Loaded the dataset using Pandas and verified:

- Shape: `6,362,620 × 11`
- No missing values
- Numerical and categorical feature types identified

### Class Distribution

The target variable contains:

- Legitimate transactions: `6,354,407`
- Fraudulent transactions: `8,213`

Fraud represents only a very small proportion of the dataset, making this a highly imbalanced classification problem.

### Transaction Type Analysis

The dataset contains five transaction types:

- `CASH_OUT`
- `PAYMENT`
- `CASH_IN`
- `TRANSFER`
- `DEBIT`

Fraudulent transactions in this dataset occur only in:

- `CASH_OUT`
- `TRANSFER`

However, these transaction types are not inherently fraudulent; the majority of transactions within them are legitimate.

### Transaction Amount Analysis

Fraudulent transactions showed substantially higher average and median transaction amounts compared with legitimate transactions.

However, transaction amount alone cannot determine whether a transaction is fraudulent.

### Balance Analysis

Investigated the relationship between transaction amounts and account balances.

Engineered two initial balance-consistency features:

```text
balance_error_orig
balance_error_dest
