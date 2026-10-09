# Churn Risk Advisor

An ML-powered decision support tool designed to assist retention teams in identifying customer churn risks and evaluating intervention strategies.

🚀 **Live App:** [Churn Risk Advisor on Streamlit](https://churn-risk-advisor-h3kybxrxt8tmj6wu6dhoxn.streamlit.app)

## Model Card: Churn Risk Advisor v1.0

- **Intended use:** Rank existing telecom customers by churn risk so a retention team can prioritize calls. Decision support, not automation.
- **Not for:** Credit, pricing, or any decision that denies a service.
- **Data:** IBM Telco Customer Churn, 7,043 customers, 26.5% churn.
- **Model:** XGBoost / Logistic Regression, chosen by 5-fold CV. Features: 30 encoded columns.
- **Performance:** CV AUC 0.845 +/- 0.012; test AUC 0.84 (test set used once).
- **Threshold:** 0.50, from a cost analysis (FN = PKR 6,000, FP = PKR 1,000).
- **Limitations:** One US dataset from one period; no Pakistan data; associations, not causes; performance may drift as plans change.
- **Fairness check (Week 15):** Compare recall across gender and seniors.
- **Owner and version:** Alisha Khan, v1.0, October 2026.

## Project Overview

This application uses a trained Machine Learning model to evaluate customer churn probability based on demographic information, account details, and subscribed services. It includes single customer risk evaluation as well as batch scoring features for bulk customer analysis.

## Features

- **One Customer Assessment:** Predict churn probability and evaluate what changes (e.g., contract extension, adding tech support) would lower the risk.
- **Batch Scoring:** Upload CSV files to generate churn risk predictions and recommendations for multiple customers at once.
- **Model Transparency:** Displays feature contributions and model metadata.

## Local Setup Instructions

1. **Clone the Repository:**
```bash
git clone https://github.com/msalishakhan023/churn-risk-advisor.git
cd churn-risk-advisor
