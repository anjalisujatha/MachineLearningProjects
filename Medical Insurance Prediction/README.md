# 🏥 Medical Insurance Price Prediction using Machine Learning

This project aims to predict medical insurance premiums based on individual attributes such as age, BMI, smoking habits, and more. It utilizes various machine learning models and compares their performance to identify the best-performing predictor.

## 📌 Objectives

- Analyze the impact of different features on insurance cost.
- Perform Exploratory Data Analysis (EDA) to understand patterns and distributions.
- Handle outliers and encode categorical variables appropriately.
- Train and evaluate multiple machine learning models.
- Deploy the final optimized model for prediction using `pickle`.

## 📊 Dataset

- Source: `insurance.csv` (contains 1338 records)
- Features:
  - `age`: Age of the person
  - `sex`: Gender
  - `bmi`: Body Mass Index
  - `children`: Number of children
  - `smoker`: Smoking status
  - `region`: Residential region
  - `charges`: Insurance premium (target variable)

## 🔍 Exploratory Data Analysis (EDA)

- Distribution plots for categorical features
- Bar plots of mean charges by categories
- Scatter plots showing the relationship between `age`, `bmi`, and `charges`
- Detection and capping of outliers using IQR and `feature_engine`

## 🧹 Preprocessing

- Encoding:
  - `sex`, `smoker`, and `region` encoded numerically
- Outlier handling in `bmi` using capping
- Removed less significant features (`sex`, `region`) based on feature importance

## 🧠 Models Used

- Linear Regression
- Support Vector Regressor (SVR)
- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoost Regressor

### ✅ Best Model: XGBoost Regressor

- Tuned with GridSearchCV (`n_estimators`, `max_depth`, `gamma`)
- Feature importance shows `smoker`, `bmi`, `age`, and `children` are most influential

### 🔢 Model Performance

| Model                  | Train R² | Test R² | CV Score |
|------------------------|----------|---------|----------|
| Linear Regression      | ~0.73    | ~0.81   | ~0.75    |
| SVR                    | <0       | <0      | <0       |
| Random Forest          | ~0.97    | ~0.88   | ~0.84    |
| Gradient Boosting      | ~0.86    | ~0.90   | ~0.86    |
| **XGBoost (Final)**    | ~0.87    | **0.90**| **0.86+**|

## 💾 Deployment

- Final model is saved using `pickle` as `insurancemodelf.pkl`
- Sample prediction:

```python
new_data = pd.DataFrame({
    'age': [19],
    'bmi': [27.9],
    'children': [0],
    'smoker': [1]
})
prediction = finalmodel.predict(new_data)
