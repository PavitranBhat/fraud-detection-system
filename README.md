# Fraud Detection System | Machine Learning & Power BI Analytics

An end-to-end fraud detection and transaction analytics project using the PaySim simulated mobile-money transaction dataset. This project combines exploratory data analysis, machine learning classification, temporal validation, and interactive Power BI dashboarding to identify fraudulent financial transactions and analyse transaction behaviour.

---

## 🎯 Project Objective

To develop a machine learning system capable of identifying fraudulent transactions while minimizing false positives in a highly imbalanced dataset, supported by analytical visualizations for understanding fraud patterns and transaction behaviour.

## 📊 Dataset Overview

- **Dataset:** PaySim Simulated Mobile-Money Transactions
- **Total Transactions:** 6,362,620
- **Features:** 11
- **Fraudulent Transactions:** 8,213
- **Fraud Rate:** 0.129%

> The dataset is simulated and does not contain real customer or banking information.

## 🛠️ Tech Stack

**Programming & Data Analysis**
- Python
- Pandas
- NumPy
- Jupyter Notebook

**Machine Learning**
- Scikit-learn
- XGBoost

**Data Visualization**
- Power BI
- Matplotlib
- Seaborn

**Tools**
- Git
- GitHub
- Google Colab

## 🔧 Project Workflow

1. Data Loading and Understanding
2. Data Cleaning and Exploratory Data Analysis
3. Feature Engineering
4. Class Imbalance Handling
5. Logistic Regression Baseline
6. XGBoost Model Development
7. Feature Importance Analysis
8. Leakage-Aware Feature Selection
9. Temporal Train-Test Validation
10. Power BI Dashboard Development

## 🤖 Machine Learning Models

### 1. Logistic Regression – Baseline Model

A baseline classification model was developed to understand the performance of a traditional machine learning algorithm on a highly imbalanced dataset.

| Evaluation Metric | Result |
|---|---:|
| Fraud Precision | 3.38% |
| Fraud Recall | 98.11% |
| F1-Score | 6.53% |
| ROC-AUC | 0.9962 |
| PR-AUC | 0.6196 |

### 2. Final XGBoost Model

XGBoost was selected as the final model after feature engineering, feature selection, and evaluation using a temporal train-test split.

| Evaluation Metric | Result |
|---|---:|
| Fraud Precision | 93.60% |
| Fraud Recall | 81.84% |
| F1-Score | 87.32% |
| ROC-AUC | 0.9997 |
| PR-AUC | 0.9641 |
| False Positives | 238 |
| False Negatives | 772 |

The final model achieved a strong balance between precision and recall, reducing false positives while identifying fraudulent transactions.

## 🔍 Key Features Used

The final model uses features including:

- Transaction amount
- Sender's pre-transaction balance
- Receiver's pre-transaction balance
- Transaction type
- Transaction-to-balance ratios
- Transaction time step

## 📈 Model Validation

A temporal split was used to evaluate the model's ability to generalize to later transactions.

- **Training Data:** Steps ≤ 355
- **Testing Data:** Steps > 355

This approach provides a more realistic evaluation of model performance on future transactions compared with relying exclusively on a random train-test split.

## 📊 Power BI Dashboard – Fraud & Transaction Analytics

An interactive Power BI dashboard was developed to analyse transaction volume, fraud distribution, fraudulent transaction amounts, and transaction patterns.

### Key Performance Indicators (KPIs)

- **Total Transactions:** 6,362,620
- **Fraudulent Transactions:** 8,213
- **Fraud Rate:** 0.129%
- **Total Fraudulent Transaction Amount:** Sum of transaction amounts classified as fraudulent.

### Dashboard Visualizations

1. Transaction Volume by Type
2. Fraudulent Transactions by Transaction Type
3. Fraud Trends Across Simulation Time Steps
4. Total Fraudulent Transaction Amount
5. Fraud Rate and Transaction Volume KPIs

### Dashboard Preview

![Fraud Detection and Transaction Analytics Dashboard](PowerBI/Fraud_Detection_Dashboard.png)

### Dashboard Report

[View / Download Power BI Dashboard PDF](PowerBI/Fraud_Detection_Report.pdf)

## 📁 Project Structure

```text
fraud-detection-system/
│
├── notebooks/
│   └── 01_eda.ipynb
│
├── PowerBI/
│   ├── Fraud_Detection_Report.pdf
│   └── Fraud_Detection_Dashboard.png
│
├── .gitignore
└── README.md
```

*Note: The raw and processed datasets are excluded from the repository through `.gitignore`.*

## 💡 Key Learnings

- Working with highly imbalanced financial transaction datasets.
- Performing exploratory data analysis on large-scale transactional data.
- Applying feature engineering and feature selection techniques.
- Understanding data leakage and its impact on model performance.
- Evaluating classification models using Precision, Recall, F1-score, ROC-AUC, and PR-AUC.
- Applying temporal validation for more realistic model evaluation.
- Building interactive Power BI dashboards to communicate analytical findings.

## 🚀 Future Improvements

- Model monitoring and performance tracking.
- Data drift detection.
- Automated fraud prediction pipeline.
- Further dashboard enhancements for fraud investigation.

## 👩‍💻 Author

**Pavitra Narayan Bhat**

- GitHub: [PavitranBhat](https://github.com/PavitranBhat)
- LinkedIn: [LinkedIn Profile](https://www.linkedin.com/)

---

*This project was developed as a practical application of machine learning and data analytics techniques for financial fraud detection.*
