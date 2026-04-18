# 🏦 Credit Risk Scoring — Default Prediction Model

![Python](https://img.shields.io/badge/Python-3.11-blue)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0-orange)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.4-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📌 Description

Machine learning model to predict the probability of credit default (PD)
using behavioral and financial features from 150,000 customers.
Three models were compared — Logistic Regression, Random Forest and XGBoost —
with XGBoost achieving the best performance (AUC = 0.84, Gini = 0.69).


## 🎯 Objectives

- Predict whether a customer will default within the next 2 years
- Handle class imbalance (6.68% default rate) using balanced class weights
- Compare 3 classification models using AUC-ROC and Gini coefficient
- Identify the most predictive features using XGBoost Feature Importance


## 🛠️ Tech Stack

| Tool | Usage |
|---|---|
| Python 3.11 | Core language |
| Pandas, NumPy | Data manipulation |
| Scikit-learn | Preprocessing, Logistic Regression, Random Forest |
| XGBoost | Best performing model |
| Matplotlib, Seaborn | Visualizations |
| JupyterLab | Exploratory analysis and modeling |



## 📊 Dataset

[Give Me Some Credit — Kaggle](https://www.kaggle.com/c/GiveMeSomeCredit)

- 150,000 customer records
- Target variable: SeriousDlqin2yrs (90+ day delinquency in 2 years)
- Default rate: 6.68% (imbalanced dataset)
- Features: revolving utilization, age, late payments, debt ratio, income, dependents


## 📁 Repository Structure
credit-risk-scoring/
│
├── data/
│   ├── raw/                    # Original dataset (cs-training.csv)
│   └── processed/              # Cleaned dataset (credit_clean.csv)
│
├── notebooks/
│   ├── 01_EDA.ipynb            # Exploratory analysis + data cleaning
│   └── 02_modeling.ipynb       # Model training, evaluation, feature importance
│
├── reports/
│   └── figures/
│       ├── target_distribution.png
│       ├── feature_distributions.png
│       ├── correlation_heatmap.png
│       ├── roc_curves.png
│       └── feature_importance.png
│
├── src/
│   ├── data_loader.py
│   ├── preprocessing.py
│   ├── model.py
│   └── evaluate.py
│
├── requirements.txt
├── .gitignore
├── main.py
└── README.md


## 📈 Model Results

| Model | AUC-ROC | Gini | Assessment |
|---|---|---|---|
| Logistic Regression | 0.7952 | 0.5904 | Good baseline |
| Random Forest | 0.8123 | 0.6246 | Good |
| XGBoost | 0.8438 | 0.6876 | ✅ Best model |

> In the credit industry, a Gini coefficient above 0.60 is considered a strong model.
> XGBoost achieved Gini = 0.69, meeting production-grade standards.


## 🔍 Top Predictive Features

| Rank | Feature | Importance |
|---|---|---|
| 1 | RevolvingUtilizationOfUnsecuredLines | 0.29 |
| 2 | NumberOfTimes90DaysLate | 0.25 |
| 3 | NumberOfTime30-59DaysPastDueNotWorse | 0.22 |
| 4 | NumberOfTime60-89DaysPastDueNotWorse | 0.09 |
| 5+ | age, DebtRatio, MonthlyIncome, etc. | < 0.03 |

> Key insight: The top 3 features are all payment behavior indicators,
> confirming that credit history is the strongest predictor of default.


## 🚀 How to Run
1. Clone the repository
git clone https://github.com/gmespinozar15/credit-risk-scoring.git
cd credit-risk-scoring
2. Install dependencies
pip install -r requirements.txt
3. Open notebooks
jupyter lab


Run `01_EDA.ipynb` first, then `02_modeling.ipynb`.

> Note: Download `cs-training.csv` from [Kaggle](https://www.kaggle.com/c/GiveMeSomeCredit/data)
> and place it in `data/raw/` before running.


## 📦 Requirements
pandas==2.2.0
numpy==1.26.0
scikit-learn==1.4.0
xgboost==2.0.3
matplotlib==3.8.0
seaborn==0.13.0
jupyterlab==4.1.0
imbalanced-learn==0.12.0



## 💼 Business Relevance

This project replicates the type of credit scoring models used in
financial institutions to automate lending decisions. The methodology
is directly applicable to PD (Probability of Default) modeling
under IFRS 9 and Basel III frameworks.


## 👩‍💻 Author

Gabriela Espinoza — Data Analyst | Lima, Peru
[LinkedIn](https://www.linkedin.com/in/gabriela-espinoza-a75447388/) · [GitHub](https://github.com/gmespinozar15)


This project is part of a Data Science portfolio focused on finance and risk analytics.