# 🏡 House Prices - Advanced Regression Techniques

This repository contains my solution for the Kaggle competition:  
[House Prices - Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)

## 🎯 Objective

- Build an accurate regression model to predict **SalePrice** of houses.
- Perform thorough data preprocessing, feature selection, and model evaluation.
- Use cross-validation to confirm the generalization performance.

## 🧠 Approach Overview

### 🔹 Data Preprocessing

- **Missing values**
  - Categorical: filled with `'None'`
  - Numerical: filled with `0`
- **Categorical encoding**
  - One-hot encoding using `pd.get_dummies`

### 🔹 Target Variable Transformation

- `SalePrice` is log-transformed using `np.log1p`  
  → improves normality and stabilizes RMSE

### 🔹 Outlier Removal

- Remove entries where `GrLivArea > 4600` (extreme outliers)

### 🔹 Feature Selection

- Train initial LightGBM model
- Select **top 40 features** based on feature importance
- Retrain the model with selected features

### 🔹 Model Training & Prediction

- Train LightGBM regressor
- Predict `SalePrice` on the test set
- Apply `np.expm1` to reverse the log-transform

### 🔹 Submission Generation

- Create `submission.csv` file and submit to Kaggle

### 🔹 Cross-Validation

- Use **5-fold KFold** CV to evaluate generalization performance
- Metric: `Root Mean Squared Error (RMSE)`

## 🔧 Tools & Technologies

- Python (Pandas, NumPy, LightGBM, scikit-learn)
- LightGBM for gradient boosting regression
- Cross-validation with `KFold`
- Visualization with `matplotlib` (optional)

## 📁 Files

| File | Description |
|------|-------------|
| `notebook.ipynb` | Kaggle Notebook containing the full solution |
| `submission.csv` | Final submission file |
| `requirements.txt` | Optional: Python environment dependencies |

## 📈 Public Score

- **RMSE: 0.13451 (Public Leaderboard)**

## 📌 Author

いちと / Ichito  
Bachelor 4th year → Going to Master’s program  
Aspiring Data Scientist｜Portfolio: GitHub, Kaggle, Research  
