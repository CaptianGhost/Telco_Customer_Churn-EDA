# Customer Churn Analysis & Predictive Modeling (v2.0)

This project analyzes a **Telco Customer Churn dataset** to understand customer behavior **and build a baseline predictive model** for identifying customers at risk of churning.

The project follows a **business-first, step-by-step workflow**, starting from data understanding and EDA, and progressing to an interpretable **Logistic Regression model** with threshold tuning and proper evaluation.

---

## Dataset
**Telco Customer Churn Dataset** ([_Kaggle_](https://www.kaggle.com/datasets/blastchar/telco-customer-churn))

---

## Technologies Used
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  

---

## Project Scope & Workflow

This project was developed iteratively, following real-world data science practices.

### 1️⃣ Data Understanding & Cleaning
- Inspected dataset structure, data types, and distributions
- Identified and handled inconsistencies and categorical encodings
- Prepared data for both EDA and modeling without unnecessary over-engineering

---

### 2️⃣ Exploratory Data Analysis (EDA)
Churn behavior was analyzed across key business dimensions:
- Customer tenure
- Contract type
- Monthly charges
- Payment methods
- Senior citizen status

EDA focused on **why customers churn**, not just what correlates with churn.

---

### 3️⃣ Feature Engineering
Simple, interpretable features were created:
- `long_contract`: Binary feature indicating long-term contracts (1 or 2 years)
- Selected numerical drivers:
  - Tenure
  - MonthlyCharges

The goal was **interpretability over complexity**.

---

### 4️⃣ Baseline Predictive Modeling
A **Logistic Regression** model was built using a Scikit-learn pipeline:
- Feature scaling with `StandardScaler`
- Logistic Regression with `liblinear` solver

This provided a transparent and explainable baseline model.

---

### 5️⃣ Model Evaluation (Default Threshold = 0.50)
Initial evaluation showed:
- Strong performance on non-churn customers
- **Low recall for churners**, meaning many at-risk customers were missed

This behavior is expected in **imbalanced churn datasets**, where non-churners are the majority.

---

### 6️⃣ Threshold Tuning (Business-Driven)
To better align with business goals, the decision threshold was lowered to **0.30**:
- Improved churn recall significantly
- Accepted higher false positives to avoid missing potential churners

This reflects a realistic retention strategy where **false alarms are cheaper than losing customers**.

---

### 7️⃣ Advanced Evaluation Metrics
The model was evaluated using:
- **Confusion Matrix**
- **Classification Report**
- **Precision–Recall Curve**
- **Average Precision (AP) Score**

Precision–Recall analysis was prioritized over accuracy and ROC-AUC due to class imbalance.

---

## Key Results (Threshold = 0.30)

- **Churn Recall:** ~75%  
- **Churn Precision:** ~51%  
- The model successfully identifies most customers at risk of churn
- False positives are acceptable in exchange for higher churn capture

---

## Key Insights
- **26.5%** of customers churned, indicating a serious retention challenge
- Churn is most likely in the **early stages of customer tenure**
- **Month-to-month contracts** have significantly higher churn rates
- Customers with **higher monthly charges** churn more frequently
- **Electronic check** users show elevated churn risk
- Senior citizens represent a vulnerable churn segment

---

## Business Interpretation

Churn is driven by a combination of:
- Early customer experience
- Pricing and perceived value
- Contract commitment
- Payment convenience

**Recommended actions:**
- Strengthen onboarding and early engagement
- Incentivize long-term contracts
- Review pricing for high-risk segments
- Encourage automated payment methods
- Use the churn model as an **early warning system**, not a final decision-maker

---

## Skills Demonstrated
- Data Cleaning & Preparation
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Logistic Regression Modeling
- Threshold Optimization
- Precision–Recall Evaluation
- Business-oriented ML interpretation

---

## Project Status
- **Version:** v2.0
- Baseline model completed and evaluated
- Designed for future extensions (class weighting, cost-sensitive learning, advanced models)

---

*This project reflects a practical, business-driven approach to machine learning rather than a purely academic one.*

Any feedback or suggestions are always welcome.

— **Ghost**