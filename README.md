# Fraud Detection System

An end-to-end machine learning system for detecting fraudulent financial transactions using the PaySim simulated mobile-money transaction dataset.

## Objective

Build a machine learning model capable of identifying fraudulent transactions while minimizing false positives in a highly imbalanced dataset.

## Dataset

- **Dataset:** PaySim simulated mobile-money transactions
- **Transactions:** 6,362,620
- **Features:** 11
- **Fraudulent transactions:** 8,213
- **Fraud rate:** ~0.129%

> The dataset is simulated and does not contain real customer or banking information.

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- Jupyter Notebook
- Git & GitHub

## 🔧 Project Workflow

```text
Data Loading
     ↓
Data Cleaning & EDA
     ↓
Feature Engineering
     ↓
Class Imbalance Handling
     ↓
Logistic Regression Baseline
     ↓
XGBoost
     ↓
Feature Importance Analysis
     ↓
Leakage-Aware Feature Selection
     ↓
Temporal Validation

## Models
Logistic Regression Baseline
Fraud Precision: 3.38%
Fraud Recall: 98.11%
F1-score: 6.53%
ROC-AUC: 0.9962
PR-AUC: 0.6196

 ## Final XGBoost Model
The final model uses a realistic feature set and is evaluated using a temporal train-test split.

Fraud Precision: 93.60%
Fraud Recall: 81.84%
F1-score: 87.32%
ROC-AUC: 0.9997
PR-AUC: 0.9641
False Positives: 238
False Negatives: 772

## Key Features

The final model uses features including:
- Transaction amount
- Sender's pre-transaction balance
- Receiver's pre-transaction balance
- Transaction type
- Transaction-to-balance ratios
- Transaction time step

## Validation

A temporal split was used to evaluate generalization to later transactions.

- Training: Steps ≤ 355
- Testing: Steps > 355
This provides a more realistic evaluation than relying only on a random train-test split.

## Project Structure
fraud-detection-system/
│
├── data/
│   └── raw/
│
├── notebooks/
│   └── 01_eda.ipynb
│
├── .gitignore
└── README.md

 ## Future Improvements
- Hyperparameter tuning
- Threshold optimization
- SHAP-based model explainability
- FastAPI prediction API
- Streamlit interface
- Model monitoring and drift detection
