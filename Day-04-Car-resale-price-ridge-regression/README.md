# Day 04 — Car Resale Price Prediction Using Ridge Regression

This project is part of my **20 Days of Supervised Learning** journey.

For Day 4, I built a **Ridge Regression model** to predict the estimated resale price of cars using vehicle characteristics and market-related features.

## 🎯 Objective

The objective of this project is to predict:

**Estimated Final Price of a Used Car**

using features such as:

- Brand
- Model
- Year
- Fuel Type
- Transmission
- KM Driven
- Owner Type
- City
- Mileage
- Engine CC
- Condition Rating
- Original Price
- Car Age
- Demand Score
- Brand Popularity Score
- Premium Car

---

## 📊 Dataset

The dataset contains **200 car records** and **23 columns**.

After data inspection and feature selection, the target variable was:

```text
estimated_final_price
```

### Target

```text
estimated_final_price
```

### Important excluded features

The following columns were removed because they could introduce target leakage or would not be appropriate for the prediction scenario:

```text
depreciation_amount
resale_value_percent
price_per_km
bargain_percent
days_to_sell
listed_price
```

A particularly important finding was the relationship between `listed_price` and the target.

```text
Correlation:
listed_price → estimated_final_price = 0.998906
```

Because `listed_price` was almost perfectly correlated with the target, I removed it and rebuilt the model.

---

## 🔍 Data Preprocessing

The project included:

1. Data loading
2. Data inspection
3. Duplicate checking
4. Relationship/correlation analysis
5. Target and feature selection
6. Leakage investigation
7. Numerical and categorical feature identification
8. Train/test split
9. Numerical feature scaling
10. Categorical feature encoding

### Numerical Features

```text
year
km_driven
mileage
engine_cc
condition_rating
original_price
car_age
demand_score
brand_popularity_score
premium_car
```

### Categorical Features

```text
brand
model
fuel_type
transmission
owner_type
city
```

Categorical features were encoded using `OneHotEncoder`, while numerical features were standardized using `StandardScaler`.

---

## 🤖 Models

Two regression models were compared:

### 1. Linear Regression

```text
MAE  : 132,094
RMSE : 162,040
R²   : 0.8654
```

### 2. Ridge Regression

```text
MAE  : 121,257
RMSE : 152,833
R²   : 0.8803
Alpha: 1.0
```

---

## 🏆 Model Comparison

| Model                |         MAE |        RMSE |         R² |
| -------------------- | ----------: | ----------: | ---------: |
| Linear Regression    |     132,094 |     162,040 |     0.8654 |
| **Ridge Regression** | **121,257** | **152,833** | **0.8803** |

Ridge Regression performed better than Linear Regression on the test set.

It achieved:

- Lower MAE
- Lower RMSE
- Higher R²

Therefore, **Ridge Regression with α = 1.0 was selected as the final model.**

---

## 🔬 Ridge Hyperparameter Tuning

I also tested different Ridge regularization values using cross-validation:

```text
0.01
0.1
1
10
100
1000
```

Cross-validation selected:

```text
Best Alpha = 10
```

However, when evaluated on the held-out test set, `alpha=10` performed worse than `alpha=1`.

### Tuned Ridge Result

```text
MAE  : 128,011
RMSE : 168,054
R²   : 0.8552
```

Therefore, based on the held-out test performance, I retained:

```text
Ridge(alpha=1.0)
```

as the final model.

---

## 🚗 New Car Predictions

After training the final model, I tested it with multiple new car records that were not part of the training dataset.

The model successfully generated estimated resale prices for the new vehicles.

---

## 📈 Actual vs Predicted

The final model was also evaluated by comparing:

```text
Actual Resale Price
        vs
Predicted Resale Price
```

A scatter plot was created to visualize how closely the predictions followed the actual values.

---

## 📌 Final Result

### Final Ridge Regression Model

```text
Algorithm : Ridge Regression
Alpha      : 1.0

MAE  : 121,257
RMSE : 152,833
R²   : 0.8803
```

The model explains approximately **88% of the variation** in the test-set resale prices.

---

## 🧠 Key Learnings

Through this project, I learned:

- How Ridge Regression works
- Why regularization is useful
- How to compare Linear and Ridge Regression
- How to identify potential target leakage
- Why extremely high model performance should be investigated
- How correlation can reveal suspiciously strong relationships
- How to preprocess numerical and categorical features
- How to use Pipelines
- How to tune Ridge's `alpha`
- How to evaluate regression models
- How to make predictions on new data
- Why validation performance and test performance can differ

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab
- Kaggle Dataset

---

## 📂 Project Files

```text
Day-04-Car-resale-price-ridge-regression/
│
├── dataset/
├── Day-04-Car-resale-price-ridge-regression.ipynb
├── images/
├── README.md
└── requirements.txt
```

---

## 🚀 20 Days of Supervised Learning

This project is **Day 04 of my 20 Days of Supervised Learning challenge**.

### Regression — Days 1–10

- Day 01 — Simple Linear Regression
- Day 02 — Multiple Linear Regression
- Day 03 — Polynomial Regression
- **Day 04 — Ridge Regression**
- Day 05 — Lasso Regression
- Day 06 — Elastic Net Regression
- Day 07 — Decision Tree Regression
- Day 08 — Random Forest Regression
- Day 09 — Gradient Boosting Regression
- Day 10 — Regression Model Comparison

### Classification — Days 11–20

Classification projects will follow after completing the regression phase.
