# Razorpay POS Customer Churn Analysis

## Project Overview
This project analyzes customer churn for **Razorpay POS Terminals**, aiming to identify key factors influencing merchant retention and develop strategies to reduce churn.

## Dataset Description
The dataset consists of **10,000+ records** of merchants using Razorpay POS terminals, with key features such as:
- **POS_Cost**: Cost of the POS machine
- **Monthly_Rental_Fee**: Recurring rental fee for the terminal
- **MDR_Rate**: Merchant Discount Rate (transaction fee)
- **LTV (Lifetime Value)**: Revenue expected from a merchant
- **Avg_Transaction_Value & Avg_Monthly_Transaction_Value**: Transaction behavior metrics
- **Churned**: Target variable (1 = Churned, 0 = Retained)

## Methodology & Approach
1. **Exploratory Data Analysis (EDA)**:
   - Identified key trends, correlations, and distribution of features.
   - Visualized transaction behaviors and cost impacts.
   
2. **Feature Engineering**:
   - Created new features such as **High Cost & Low Transaction Volume** merchants.
   - Examined correlations between churn and various factors.

3. **Modeling & Evaluation**:
   - **Logistic Regression** and **Random Forest** models were trained to predict churn.
   - Model performance assessed using **ROC AUC Score, Confusion Matrix, and Feature Importance**.

## Exploratory Data Analysis (EDA)
EDA was conducted to **understand patterns in churned vs. non-churned merchants**:
- **Churn Distribution:** Visualized overall churn rate and industry-wise segmentation.
- **Boxplots:** Used to compare key numerical features (POS Cost, Monthly Rental Fee, LTV) between churned and non-churned merchants.
- **Correlation Heatmap:** Identified relationships between numerical variables and churn, revealing insights on factors like transaction volume and MDR rate.


## Model Performance
### 1) **Logistic Regression**
- Chosen for its interpretability in understanding feature importance.
- ROC AUC Score: **0.51** (slightly better than random guessing).
- Struggles with **high false positives (609) and false negatives (380)**.

### 2) **Random Forest**
- Used for capturing non-linear relationships in the data.
- ROC AUC Score: **0.48** (slightly worse than Logistic Regression).
- Feature importance indicates **transaction-based factors (Avg Transaction Value, LTV) are stronger churn predictors than pricing-based factors**.

## 🚀 Key Insights from both the models:
| Model                 | ROC AUC Score | Key Findings |
|----------------------|--------------|--------------|
| **Logistic Regression** | 0.51 | Slightly better than random guessing, struggles with false positives. |
| **Random Forest** | 0.48 | Worse than Logistic Regression, suggests transaction-based factors are stronger predictors. |

### Key Insights from Confusion Matrix:
- **High False Positives (609 merchants)** → Wasted retention efforts.
- **High False Negatives (380 merchants)** → Missed opportunities for proactive retention.
- **Recall (63%)** → Model detects churners well, but with **low precision (51%)**.


## Key Findings & Business Insights
**Factors Contributing to Churn**:
1. **Transaction Volume is a key churn driver**: Merchants with lower transaction values have higher churn rates.
2. **High Cost & Low Transaction Volume segment churns equally as others** → POS Cost alone is **not a major churn driver**.
3. **Feature Importance (Random Forest Model)**:
   - **Top churn predictors**:
     - **Avg_Monthly_Transaction_Value** (Most Important)
     - **LTV (Lifetime Value)**
     - **MDR Rate (Transaction Fee)**
   - **Low Importance**: POS Cost & Monthly Rental Fee


## Suggested Strategies for Retention
1. **Target merchants with declining transaction volumes** with personalized offers.
2. **Revise MDR & POS pricing** for SMBs to remain competitive.
3. **Enhance customer support** to assist at-risk merchants.
4. **Loyalty programs & cashback incentives** to increase merchant stickiness.
5. **AI-powered predictive retention models** for early churn detection.


## Next Steps
- Try **Gradient Boosting Models (XGBoost, LightGBM)** for better churn prediction.
- Incorporate **support tickets, technical issues & feedback scores** as new features.
- Develop an **AI-driven retention strategy** based on transaction trends.

---

## Tech Stack
- **Python** (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)
- **Machine Learning Models**: Logistic Regression, Random Forest
- **EDA & Feature Engineering**: Correlation matrix, Churn segmentation, Interaction effects
- **Visualization Tools**: Seaborn, Matplotlib

