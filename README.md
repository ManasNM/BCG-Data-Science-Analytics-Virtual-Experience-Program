# PowerCo SME Churn Prediction Project

## 🚀 Overview

PowerCo, a leading energy provider in Europe, is facing increased customer churn in the SME (Small and Medium Enterprise) segment following the liberalization of the energy market. In partnership with BCG, this project aims to diagnose churn drivers and build a predictive model to identify at-risk customers, enabling PowerCo to take proactive retention measures.

## 🎯 Objective

Develop a machine learning model to:

* Predict which SME customers are likely to churn.
* Understand key factors influencing churn, especially price sensitivity.
* Estimate financial impact of reducing churn.
* Recommend actionable strategies to retain high-risk customers.

---

## 🧠 Step 1: Business Understanding & Hypothesis

**Hypothesis**: SME customer churn is primarily driven by price sensitivity.

**Approach**:

* Frame the hypothesis as a binary classification problem.
* Identify data requirements: customer usage, pricing, churn indicators.
* Analyze whether price changes correlate with churn.

**Key Questions**:

* Are customers leaving due to price increases?
* Which variables (e.g., margins, consumption, tenure) impact churn most?

---

## 📊 Step 2: Exploratory Data Analysis (EDA)

* Analyzed historical customer, pricing, and churn data.
* Explored distributions, missing values, correlations.
* Found potential churn drivers: forecast error, meter rent, gross/ net margin.

**Insights**:

* Price-related features show notable differences between churned and retained customers.
* Churned customers typically have higher forecast error and lower margin.

**Suggestions for Data Augmentation**:

* Customer support call history.
* Payment behavior.
* Market price index for energy.

---

## 🛠️ Step 3: Feature Engineering & Modeling

* Created new features: forecast accuracy, gross/ net margin, max power.
* Trained Random Forest Classifier.

**Model Results**:

* Accuracy: \~91%
* Precision: \~84%
* Recall: \~11%
* F1 Score: \~20%
* ROC AUC: \~0.72

**Feature Importance**:

* Top features: `forecast_meter_rent_12m`, `forecast_error_12m`, `cons_12m`, and `net_margin_per_product`.

**Model Pros & Cons**:

* ✅ Handles nonlinearities and interactions well.
* ❌ Low recall indicates poor sensitivity to minority (churn) class — needs balancing.

---

## 📌 Step 4: Insights & Recommendations

### 🔍 Key Insights

* Price sensitivity (forecast error, net margins) strongly influences churn.
* Most customers are being predicted as "retained," showing model imbalance.

### 📢 Recommendations

* Segment SME customers by churn risk.
* Offer price discounts or loyalty rewards to high-risk segments.
* Use churn model to trigger automated retention campaigns.
* Improve recall via resampling (SMOTE) or alternative classifiers.

---

## 💰 Step 5: Financial Impact Analysis

### 💡 Revenue Impact Estimation

* Estimated savings = Churned customers retained \* Average customer value
* Example: At 20% churn reduction, PowerCo could save **>\$340,000/year**.

### 📈 Business Scenario

> "Reducing churn by just 10% saves approx. \$170,000 annually."

This analysis demonstrates the model’s **real-world business value**, justifying investment in churn reduction efforts.

---

## ✅ Conclusion

* A Random Forest model was developed to predict churn with good accuracy but needs improvement in recall.
* Price-related features are crucial in understanding churn behavior.
* Reducing churn through targeted offers could yield significant financial benefits.

---

## 📂 Repository Structure

```
|- data/                # Raw and cleaned datasets
|- notebooks/           # EDA, modeling, financial impact Jupyter notebooks
|- images/              # Visualizations (feature importance, confusion matrix, etc.)
|- models/              # Saved model files (pickle, joblib, etc.)
|- README.md            # Project overview and guide
```

---

## 🤝 Authors

* Manas Nayan Mukherjee
* In collaboration with BCG X
---

## 🏁 Next Steps

* Improve recall using class balancing techniques.
* Explore XGBoost or LightGBM for better churn prediction.
* Integrate model with PowerCo CRM for real-time retention campaigns.

