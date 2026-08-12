# Day 05 — Real Estate Rent Prediction using Lasso Regression 🏠

As part of my **20 Days of Supervised Learning** challenge, Day 5 focuses on **Lasso Regression** for predicting monthly rental prices of real estate properties.

## 🎯 Objective

Build a machine learning model that predicts:

> **Monthly Rental Estimate (INR)**

using property characteristics such as:

- Property location
- Property type
- Built-up area
- Number of bedrooms
- Number of bathrooms
- Property age
- Walkability score
- Maintenance cost
- Property price
- Other relevant features

---

## 📊 Dataset

- Records: **1,000**
- Original features: **25**
- Final modeling features: **17**
- Target: `monthly_rental_estimate_inr`

### Data Quality

- Missing values: **0**
- Duplicate rows: **0**

---

## 🔍 Data Preparation

The following steps were performed:

1. Data loading
2. Data understanding
3. Missing-value checking
4. Duplicate checking
5. Numerical feature analysis
6. Categorical feature analysis
7. Correlation analysis
8. Data leakage checking
9. Feature selection
10. Train/Test split

### Train/Test Split

```text
Training data: 800 rows
Testing data:  200 rows
```
