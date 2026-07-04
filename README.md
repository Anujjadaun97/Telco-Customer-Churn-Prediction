# Customer Churn Prediction using Machine Learning

> **Predicting customer churn to help businesses proactively retain valuable customers through data-driven insights and machine learning.**

---

## 📌 Project Overview

Customer retention is one of the most critical challenges for subscription-based businesses. Acquiring a new customer often costs significantly more than retaining an existing one. This project focuses on building and evaluating multiple machine learning classification models to predict whether a customer is likely to churn based on their demographic information, subscribed services, account details, and billing history.

The project follows an **end-to-end Machine Learning workflow**, starting from business understanding and data cleaning to feature engineering, model building, evaluation, interpretation, and business recommendations.

---

## 🎯 Business Problem

Telecommunication companies lose revenue when customers discontinue their services.

**Business Question**

> **Which customers are most likely to churn, and what actions can the company take to reduce customer attrition?**

The objective is to identify high-risk customers early so the business can implement targeted retention strategies.

---

## 📂 Dataset

**Dataset:** Telco Customer Churn Dataset (Kaggle)

### Dataset Summary

* **Rows:** 7,043
* **Columns:** 21
* **Target Variable:** Churn (Yes / No)

### Feature Categories

| Category              | Features                                                                    |
| --------------------- | --------------------------------------------------------------------------- |
| Customer Demographics | Gender, SeniorCitizen, Partner, Dependents                                  |
| Services              | PhoneService, InternetService, StreamingTV, TechSupport, OnlineBackup, etc. |
| Account Information   | Contract, PaymentMethod, PaperlessBilling, Tenure                           |
| Financial             | MonthlyCharges, TotalCharges                                                |
| Target                | Churn                                                                       |

---

# 🛠️ Tech Stack

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* XGBoost
* Jupyter Notebook

---

# 📁 Project Structure

```text
Customer-Churn-Prediction/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_business_understanding.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_exploratory_data_analysis.ipynb
│   ├── 04_feature_engineering.ipynb
│   └── 05_model_training.ipynb
│
├── reports/
│   ├── figures/
│   ├── business_insights.md
│   └── recommendations.md
│
├── models/
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

# 🔄 Project Workflow

```text
Business Understanding
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Data Preprocessing
        ↓
Model Training
        ↓
Model Evaluation
        ↓
Model Interpretation
        ↓
Business Recommendations
```

---

# 🧹 Data Cleaning

The dataset was thoroughly validated before model development.

### Tasks Performed

* Inspected dataset structure and data types
* Converted `TotalCharges` from string to numeric
* Investigated missing values
* Removed 11 records with:

  * Tenure = 0
  * Missing TotalCharges
* Checked duplicate rows and customer IDs
* Validated categorical values
* Performed numerical validation
* Documented all cleaning decisions with business justification

---

# 📊 Exploratory Data Analysis

The project includes extensive univariate, bivariate, and multivariate analysis to understand customer behavior.

## Key Findings

### Customer Distribution

* Approximately **27% of customers churned**
* Dataset is moderately imbalanced

### Customer Tenure

* New customers showed significantly higher churn
* Long-tenure customers were more likely to stay

### Contract Type

* Month-to-month contracts had the highest churn rate
* Two-year contracts showed the strongest retention

### Monthly Charges

* Customers with higher monthly charges were more likely to churn

### Internet Service

* Fiber optic customers experienced higher churn than DSL users

### Payment Method

* Electronic check users churned more frequently than customers using automatic payment methods

### Customer Demographics

* Gender showed minimal influence on churn
* SeniorCitizen had relatively low predictive importance

---

# ⚙️ Feature Engineering

To better represent customer behavior, several new business-driven features were created.

| Engineered Feature      | Business Purpose                  |
| ----------------------- | --------------------------------- |
| TotalServicesSubscribed | Measures customer engagement      |
| CustomerTenureGroup     | Represents customer lifecycle     |
| CustomerValueTier       | Represents customer value         |
| DigitalAdoptionScore    | Measures digital service adoption |

These features improved the business representation of customer behavior beyond the original dataset.

---

# 🤖 Machine Learning Models

The following classification algorithms were trained and evaluated:

* Logistic Regression
* Decision Tree
* Random Forest
* Gradient Boosting
* XGBoost

---

# 📈 Model Evaluation

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix
* Classification Report

---

# 🏆 Model Performance

| Model               |   Accuracy |  Precision |     Recall |   F1 Score |    ROC-AUC |
| ------------------- | ---------: | ---------: | ---------: | ---------: | ---------: |
| Logistic Regression | **80.13%** | **65.46%** | **53.21%** | **58.70%** | **84.18%** |
| Decision Tree       |     73.39% |     49.86% |     47.33% |     48.56% |     65.01% |
| Random Forest       |     79.21% |     64.01% |     49.47% |     55.81% |     82.10% |
| Gradient Boosting   |     79.99% | **65.97%** |     50.80% |     57.40% | **84.42%** |
| XGBoost             |     78.42% |     60.61% | **53.48%** |     56.82% |     82.20% |

---

# 🏅 Final Model Selection

Although XGBoost achieved the highest Recall by a very small margin, **Logistic Regression** was selected as the recommended production model because it provided the best overall balance between:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* Model Interpretability
* Generalization Performance

Its Recall was only marginally lower than XGBoost while outperforming it on most other evaluation metrics and offering much greater interpretability.

---

# 🔍 Feature Importance & Model Interpretation

Model interpretation was performed using:

* Logistic Regression Coefficients
* Tree-based Feature Importance

The most influential features consistently included:

* Contract Type
* Customer Tenure
* Monthly Charges
* Total Charges
* Internet Service
* Payment Method
* Total Services Subscribed
* Digital Adoption Score

These features played the largest role in predicting customer churn across multiple algorithms.

---

# 💡 Business Insights

Based on exploratory analysis and model interpretation, the following insights were identified:

* Customers on month-to-month contracts are significantly more likely to churn.
* Newly acquired customers have a higher probability of leaving.
* Customers with higher monthly charges tend to churn more frequently.
* Fiber optic subscribers exhibit higher churn despite premium services.
* Customers using electronic check payments show increased churn.
* Customers with lower service adoption are more likely to leave.
* Long-tenure customers demonstrate stronger loyalty.
* Customers with greater overall service engagement are less likely to churn.

---

# 📌 Business Recommendations

Based on the findings, the following strategies are recommended:

### Customer Retention

* Encourage migration from month-to-month to long-term contracts through discounts and loyalty incentives.

### Customer Onboarding

* Develop structured onboarding programs during the first 90 days to improve early customer engagement.

### Pricing Strategy

* Review pricing for high monthly charge plans and communicate value more effectively.

### Payment Experience

* Promote automatic payment methods through incentives to reduce churn associated with manual payments.

### Customer Engagement

* Increase service adoption through personalized cross-selling and bundled service offerings.

### Premium Customer Support

* Improve support quality for Fiber Optic customers experiencing higher churn rates.

### Loyalty Programs

* Reward long-tenure customers with exclusive benefits and retention offers.

### Predictive Retention

* Deploy the machine learning model to identify high-risk customers and trigger proactive retention campaigns.

---

# 🎯 Skills Demonstrated

This project demonstrates practical experience in:

* Business Problem Framing
* Data Cleaning & Validation
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Data Preprocessing
* Classification Modeling
* Model Comparison
* Feature Importance Analysis
* Business Interpretation
* Data Storytelling
* End-to-End Machine Learning Pipeline

---

# 🚀 Future Improvements

Potential enhancements include:

* Hyperparameter tuning using GridSearchCV or RandomizedSearchCV
* Cross-validation for robust model evaluation
* SHAP for advanced model explainability
* Threshold optimization to improve Recall
* Probability calibration
* Model deployment using Streamlit or FastAPI
* Real-time churn prediction API
* Automated retraining pipeline

---

# 📚 Key Learning Outcomes

Through this project, I gained hands-on experience in:

* Translating business problems into machine learning solutions.
* Designing a complete end-to-end classification pipeline.
* Building business-driven engineered features instead of relying solely on raw data.
* Comparing multiple machine learning algorithms using appropriate evaluation metrics.
* Understanding why business objectives should guide model selection rather than relying only on accuracy.
* Interpreting machine learning results and converting them into actionable business recommendations.
* Communicating technical findings through clear data storytelling suitable for both technical and non-technical stakeholders.

---

## ⭐ If you found this project interesting, consider giving the repository a star and sharing your feedback!
