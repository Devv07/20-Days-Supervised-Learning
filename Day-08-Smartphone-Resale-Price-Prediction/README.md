# 📱 Smartphone Resale Price Prediction

## 📌 Day 8 — 20-Day Supervised Learning Challenge

This project focuses on predicting the resale price of smartphones using **Random Forest Regression**.

The goal is to build a complete machine learning pipeline starting from raw, imperfect data and ending with predictions for new smartphones.

---

## 🎯 Objective

Predict the resale price of a smartphone based on features such as:

- Brand
- Model
- Age
- Original Price
- RAM
- Storage
- Battery Health
- Screen Size
- Camera
- Condition
- Warranty
- Repair Count
- Accessories

### Target Variable

`resale_price_inr`

---

## 🧠 Machine Learning Algorithm

### Random Forest Regression

Random Forest Regression combines multiple decision trees and averages their predictions to produce a more robust prediction.

It can capture nonlinear relationships between smartphone characteristics and resale prices.

---

## 📊 Dataset

The dataset contains **2,000 smartphone records**.

### Numerical Features

- `age_months`
- `original_price_inr`
- `ram_gb`
- `storage_gb`
- `battery_health_percent`
- `screen_size_inches`
- `camera_mp`
- `warranty_months_left`
- `repair_count`

### Categorical Features

- `brand`
- `model`
- `condition`
- `accessories_included`

### Target

- `resale_price_inr`

---

## 🔍 Data Preparation

The project included practical data preprocessing:

- Missing-value detection
- Duplicate detection and removal
- Numerical feature analysis
- Categorical feature analysis
- Categorical encoding
- Train/test splitting
- Feature preprocessing

---

## 📈 Exploratory Data Analysis

The relationship between numerical features and resale price was analyzed.

The strongest numerical relationships included:

| Feature        | Correlation |
| -------------- | ----------: |
| Original Price |       0.766 |
| Age            |      -0.457 |
| Storage        |       0.190 |
| RAM            |       0.083 |

This shows that **original price** has a strong positive relationship with resale price, while **phone age** has a moderate negative relationship.

---

## 🌳 Random Forest Baseline

The initial Random Forest model produced:

| Metric |   Test Result |
| ------ | ------------: |
| MAE    |     ₹6,165.14 |
| MSE    | 67,351,920.28 |
| RMSE   |     ₹8,206.82 |
| R²     |        0.8862 |

---

## ⚙️ Hyperparameter Tuning

Several Random Forest parameters were tested.

### Maximum Depth

Different values were compared:

- 5
- 8
- 10
- 12
- 15
- 20
- None

The model achieved its strongest test performance around a depth of **12–20**, with only small differences between the best configurations.

### Minimum Samples Split

Values from 2 to 50 were tested.

### Minimum Samples Leaf

Values from 1 to 20 were tested.

### Number of Estimators

Values tested:

- 50
- 100
- 150
- 200
- 300

The 300-tree configuration gave approximately:

- Test R²: **0.8864**
- Test MAE: **₹6,157**
- Test RMSE: **₹8,199**

---

## 📊 Final Model Performance

### Training Performance

- MAE: approximately ₹2,243
- MSE: approximately 9.32M
- RMSE: approximately ₹3,053
- R²: **0.9858**

### Testing Performance

- MAE: approximately ₹6,157
- MSE: approximately 67.35M
- RMSE: approximately ₹8,199
- R²: **0.8864**

The difference between training and testing performance indicates some overfitting, but the model still generalizes well to unseen data.

---

## 🔎 Model Interpretation

Feature importance analysis was used to understand which variables contributed most to the Random Forest predictions.

The model considers information such as:

- Original smartphone characteristics
- Phone age
- Storage
- RAM
- Battery health
- Condition
- Warranty
- Repair history
- Brand and model

Feature importance helps explain which inputs the model relies on most when predicting resale value.

---

## 📉 Residual Analysis

Residual analysis was performed using:

```text
Residual = Actual Price - Predicted Price
```
