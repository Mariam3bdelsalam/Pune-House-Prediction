# 🏠 House Price Prediction (Regression Project)

This project is focused on predicting house prices using various regression models with structured preprocessing and feature selection pipelines.

---

## 📊 Dataset Overview

The dataset contains information about residential units with the following features:

- `area_type` (Categorical)
- `availability` (Categorical)
- `size` (e.g., 2 BHK)
- `society` (Categorical)
- `total_sqft` (Numeric)
- `bath` (Numeric)
- `balcony` (Numeric)
- `site_location` (Categorical)
- `price` (Target - Numeric)

---

## 🔍 Steps Performed

### 1. Exploratory Data Analysis (EDA)
- Checked for null values.
- Analyzed distribution and skewness of numerical features.
- Visualized categorical feature counts.
- Detected and visualized outliers.

### 2. Data Preprocessing

**Numerical Pipeline:**
- Imputed missing values using median.
- Applied `PowerTransformer (Yeo-Johnson)` to reduce skewness.
- Used `RobustScaler` to handle outliers.

**Categorical Pipelines:**
- Used `TargetEncoder` for high-cardinality features (`society`, `site_location`).
- Applied `OneHotEncoder` for low-cardinality features (`area_type`, `availability`).

### 3. Feature Engineering
- Extracted number of bedrooms from `size` column.
- Calculated total price per square foot (`price_per_sqft`) as an optional feature.


### 4. Feature Selection
- Used `SelectKBest` with `f_regression` score function inside a pipeline.

### 5. Modeling
- Built a complete `Pipeline` combining preprocessing, feature selection, and model.
- Used `GridSearchCV` with 5-fold cross-validation and `neg_root_mean_squared_error` scoring.
- Models used in GridSearch:
  - Linear Regression
  - Random Forest Regressor
  - Support Vector Regressor (SVR)

### 6. Evaluation
- Evaluated the best model using:
  - **R² Score**
  - **Mean Squared Error (MSE)**
  - **Root Mean Squared Error (RMSE)**

---

## 🏁 Results

- **Best Model:** Random Forest 
- **Best RMSE (CV):** `31.16`
- **R² Score (Test):** ` 97.67`
- **RMSE (Test):** `25.68`

---

## 🛠 Tools & Libraries

- Python
- Pandas, NumPy
- Scikit-learn
- Category Encoders (`TargetEncoder,OneHotEncoder`)
- Matplotlib / Seaborn (EDA)

---

## ✅ Next Steps

- Hyperparameter tuning of top-performing model.
- Try advanced models like **XGBoost**, **LightGBM**.
- Possibly include more features or external datasets.

---


