# 🏥 Insurance Price Prediction using Elastic Net Regression

A Machine Learning project that predicts medical insurance charges using
Elastic Net Regression.

## 📌 Project Overview

This project uses customer information such as age, BMI, number of children,
smoking status, sex, and region to predict medical insurance charges.

Elastic Net Regression combines L1 (Lasso) and L2 (Ridge) regularization,
making it useful when dealing with multiple features and potential
multicollinearity.

## 🎯 Objectives

- Perform Exploratory Data Analysis
- Clean and preprocess the dataset
- Handle numerical and categorical features
- Build an Elastic Net Regression model
- Tune `alpha` and `l1_ratio`
- Evaluate model performance
- Analyze model coefficients
- Predict charges for new customers
- Save the trained model

## 📊 Dataset

Features:

- age
- sex
- bmi
- children
- smoker
- region

Target:

- charges

After removing duplicate rows:

- Records: 1,337
- Features: 6
- Target: charges

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Joblib

## 🔄 Machine Learning Workflow

Dataset
↓
Data Cleaning
↓
EDA
↓
Feature Analysis
↓
Train/Test Split
↓
Preprocessing
↓
Baseline Elastic Net
↓
Hyperparameter Tuning
↓
Model Evaluation
↓
Coefficient Analysis
↓
New Customer Prediction
↓
Model Saving

## ⚙️ Preprocessing

Numerical Features:

- age
- bmi
- children

Categorical Features:

- sex
- smoker
- region

Numerical features were standardized using `StandardScaler`.

Categorical features were transformed using `OneHotEncoder`.

## 🤖 Model

Elastic Net Regression was used because it combines:

- L1 Regularization
- L2 Regularization

Hyperparameters tuned:

- `alpha`
- `l1_ratio`

GridSearchCV with 5-fold cross-validation was used for tuning.

## 📈 Model Performance

### Baseline Elastic Net

- MAE: 6893.38
- RMSE: 9664.92
- R²: 0.4917

### Tuned Elastic Net

- MAE: 4177.94
- MSE: 35,488,082.17
- RMSE: 5957.19
- R²: 0.8069

The tuned model improved the R² score from approximately
49.17% to 80.69%.

## 🔍 Feature Analysis

The strongest coefficients were associated with:

- Smoking status
- Age
- BMI
- Number of children

Smoking status had the strongest influence on the model predictions.

## 🔮 New Customer Prediction

The final model was also tested with previously unseen customer records.

Example predictions included:

- $2,922.51
- $31,977.53
- $11,847.38
- $6,104.26
- $38,284.90

## 💾 Model Saving

The complete preprocessing + model pipeline was saved using Joblib.

```python
joblib.dump(
    best_elastic_net,
    "day6_elastic_net_insurance_model.pkl"
)
```
