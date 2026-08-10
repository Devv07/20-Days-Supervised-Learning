# Day 03 — Student Score Prediction using Polynomial Regression

## 📌 Project Overview

This project focuses on predicting a student's **total score** based on their **weekly self-study hours** using Polynomial Regression.

The goal of this project was to understand how a machine learning model can learn a **non-linear relationship** between an input feature and a target variable.

---

## 📊 Dataset

The dataset contains **1,000,000 student records** with the following columns:

- `student_id`
- `weekly_self_study_hours`
- `attendance_percentage`
- `class_participation`
- `total_score`
- `grade`

For this project, the main features used were:

**Input (X):**

- `weekly_self_study_hours`

**Target (y):**

- `total_score`

---

## 🔎 Machine Learning Workflow

The project followed this workflow:

1. Load the dataset
2. Inspect the dataset using `info()` and `describe()`
3. Check data quality
4. Check unique student IDs
5. Select the required feature and target
6. Split the data into training and testing sets
7. Train a Linear Regression baseline model
8. Evaluate the baseline model
9. Apply Polynomial Features
10. Train Polynomial Regression models
11. Compare polynomial degrees from 1 to 5
12. Select the best-performing degree
13. Test the model on new student data
14. Compare actual vs predicted scores
15. Save the trained model using Joblib
16. Load the saved model and make a new prediction

---

## 📈 Model Comparison

| Degree |        MAE |         MSE |       RMSE |         R² |
| -----: | ---------: | ----------: | ---------: | ---------: |
|      1 |     7.1613 |     80.9350 |     8.9964 |     0.6600 |
|      2 |     6.3087 |     68.3980 |     8.2703 |     0.7127 |
|      3 |     6.2122 |     67.6816 |     8.2269 |     0.7157 |
|      4 |     6.1302 |     67.2755 |     8.2022 |     0.7174 |
|  **5** | **6.1080** | **67.2204** | **8.1988** | **0.7177** |

### 🏆 Final Model

The Degree 5 Polynomial Regression model produced the best test-set performance among the tested degrees.

**Final metrics:**

- **MAE:** 6.1080
- **MSE:** 67.2204
- **RMSE:** 8.1988
- **R²:** 0.7177

---

## 🧪 New Data Prediction

The trained model was also tested with new weekly study-hour values.

Example predictions:

| Weekly Study Hours | Predicted Score |
| -----------------: | --------------: |
|                  5 |           62.25 |
|                 10 |           75.08 |
|                 15 |           87.01 |
|                 20 |           95.79 |
|                 25 |           99.88 |
|                 30 |           99.70 |
|                 35 |           98.92 |

This demonstrated how a trained machine learning model can be used to predict the score of a new student.

---

## 🧠 Key Learning

This project helped me understand:

- Linear Regression as a baseline model
- Polynomial Regression
- Polynomial feature transformation
- Train/Test Split
- Model evaluation
- MAE, MSE, RMSE and R²
- Comparing different polynomial degrees
- Making predictions on unseen data
- Understanding actual vs predicted values
- Saving and loading trained ML models using Joblib

One important lesson was that **a prediction alone does not tell us how good a model is**. Evaluation metrics such as MAE and RMSE help us understand the model's prediction error.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Joblib
- Google Colab

---

## 📂 Files

```text
student_score_polynomial_regression.ipynb
README.md
polynomial_features.pkl
student_score_polynomial_model.pkl
```

---

## 🚀 20-Day Supervised Learning Challenge

This project is **Day 3 of my 20-Day Supervised Learning Challenge**.

**10 Regression Projects → 10 Classification Projects**

The goal is to build practical machine learning projects while documenting my learning journey every day.
