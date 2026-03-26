# Costumer_Churn_Prediction
<div align="center">

# 📊 Customer Churn Analysis & Prediction

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](#)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](#)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)](#)
[![XGBoost](https://img.shields.io/badge/XGBoost-1081C2?style=for-the-badge&logo=xgboost&logoColor=white)](#)

*Uncovering insights and building predictive models to understand and prevent customer attrition.*

</div>

---

## 📖 Overview

This project focuses on **Exploratory Data Analysis (EDA)** and predictive modeling to understand and prevent **Customer Churn**. 

Customer churn (or customer attrition) refers to the phenomenon where customers stop doing business with a company or service. It is a critical metric for businesses as it directly impacts revenue and profitability. High churn rates can indicate dissatisfaction with the product or service, or a generally poor customer experience. By predicting which customers are at risk of leaving, businesses can take targeted, proactive steps to retain them.

## 🗄️ Dataset

The data contains various demographics and account details of banking customers. The main variable of interest (the target) is **`Exited`**, which indicates whether the customer has churned (1) or stayed (0).

**Key Features:**
- `RowNumber` | `CustomerId` | `Surname` - Identifiers
- `CreditScore` - Customer's credit score
- `Geography` - Customer's country/region
- `Gender` - Male / Female
- `Age` - Customer's age
- `Tenure` - Years the customer has been with the bank
- `Balance` - Account balance
- `NumOfProducts` - Number of bank products the customer uses
- `HasCrCard` - Whether they hold a credit card (1 = Yes, 0 = No)
- `IsActiveMember` - Active membership status (1 = Yes, 0 = No)
- `EstimatedSalary` - Estimated annual salary

## 🚀 Key Features of this Project

- ⚖️ **Handling Imbalanced Data:** The project implements advanced techniques such as **SMOTE** (Synthetic Minority Over-sampling Technique) and class weighting to ensure accurate predictions, even when the churned customers (the minority class) are heavily underrepresented.
- 🔍 **Exploratory Data Analysis (EDA):** Deep dive into data visualization to identify trends, correlations, and the underlying reasons driving customer churn.
- 🤖 **Comprehensive Classification Modeling:** Evaluates and compares a variety of robust machine learning models to find the optimal solution for churn prediction.

## ⚙️ Requirements

To run the notebook and reproduce the models, you will need the following libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```

## 📈 Model Performance & Results

We trained several classification models. Below is the performance comparison across key metrics:

| Model | Accuracy | Recall Score | F1 Score | ROC AUC Score |
|:---|:---:|:---:|:---:|:---:|
| **Logistic Regression** | 70.37% | 0.6832 | 0.4730 | 0.7640 |
| **Random Forest** | **86.20%** | 0.4143 | 0.5389 | 0.8524 |
| **K-Nearest Neighbors** | 75.23% | 0.6678 | 0.5121 | 0.7766 |
| **Support Vector Machine** | 78.56% | 0.6626 | 0.5462 | 0.8225 |
| **XGBoost** | 83.30% | 0.6095 | 0.5869 | 0.8417 |
| 🏆 **Gradient Boosting** | 81.70% | **0.7003** | **0.5983** | **0.8597** |

---

## 💡 Conclusion & Key Insights

From the model evaluations, we can infer the following:

1. **The Champion: Gradient Boosting** 🥇
   Gradient Boosting is the most effective model for this task. It achieved the highest **F1 Score (0.598)** and the highest **ROC AUC Score (0.859)**. It provides the best overall balance between precision and recall, meaning it is highly capable of distinguishing between customers who will churn and those who will stay.

2. **The Runner Up: XGBoost** 🥈
   XGBoost also performs exceptionally well with a very strong F1 Score (0.586) and ROC AUC (0.841). It acts as a very strong alternative for this predictive task.

3. **High Accuracy vs. Real Value: Random Forest** 🤔
   While Random Forest achieved the highest raw *Accuracy* (86.2%), it suffered from a poor F1 Score (0.538) and low Recall (0.414). This indicates that while it is excellent at identifying the majority class (customers who stay), it struggles significantly to identify the minority class (customers who actually churn), which defeats the purpose of early churn detection.

4. **Moderate Performers: SVM & KNN** 📊
   Support Vector Machine and K-Nearest Neighbors delivered moderate F1 and ROC AUC scores. They noticeably outperform Logistic Regression but fall short of the tree-based boosting models.

5. **Baseline: Logistic Regression** 📉
   Logistic Regression yielded the lowest metrics across the board (Accuracy: 70.3%, F1: 0.473, ROC AUC: 0.764), proving to be the least effective algorithm for capturing the complex, non-linear relationships in this dataset.

**Summary:** 
For deployment, **Gradient Boosting** or **XGBoost** are the highly recommended models. Their ability to elegantly handle the class imbalance ensures that the business can effectively identify at-risk customers and intervene before they leave.
