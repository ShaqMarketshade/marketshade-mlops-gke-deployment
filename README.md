# Customer Churn Prediction 

This repository contains a machine learning project focused on predicting **customer churn** in the telecom industry. The goal is to help businesses identify customers at risk of leaving, so they can take proactive retention measures.

---

## Project Overview
- **Dataset**: Telecom Churn dataset (7,043 rows × 21 columns).
- **Objective**: Predict whether a customer will churn based on their demographic, contract, and service usage data.
- **Approach**:
  1. Exploratory Data Analysis (EDA)
  2. Feature Engineering
  3. Logistic Regression Modeling
  4. Model Evaluation
  5. Feature Importance Analysis
  6. Deployment Notes (saved model + scaler for production use)

---

## Exploratory Data Analysis
- Distribution of churn vs non-churn customers.
- Visualization of numerical and categorical features.
- Correlation heatmap to identify influential factors.

---

## Feature Engineering
- Dropped irrelevant columns (`customerID`).
- Handled missing values.
- Encoded categorical variables (One-Hot Encoding).
- Encoded target variable (`Churn`) with Label Encoding.
- Applied feature scaling (StandardScaler).

---

## Modeling
- **Simple Logistic Regression**: baseline model.
- **Multiple Logistic Regression**: improved performance with all features.

**Evaluation Metrics:**
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

## Results & Insights
- Logistic Regression was effective in identifying churners.
- Key features (contract type, payment method, tenure, etc.) showed strong influence on churn.
- Feature importance helped interpret the drivers behind customer attrition.

---

## Deployment Notes
The trained model and scaler are saved using `joblib`:
```python
# Load model & scaler
model = joblib.load("churn_prediction_model.pkl")
scaler = joblib.load("scaler.pkl")

# Preprocess new data
X_new_scaled = scaler.transform(new_data)

# Predict churn
predictions = model.predict(X_new_scaled)
