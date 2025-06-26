# Laptop Price Prediction Model

This repository contains a machine learning pipeline for predicting laptop prices using various regression and ensemble techniques. The workflow includes data preprocessing, feature engineering, model training, evaluation, and stacking ensemble methods.

---

## **Techniques Used**

### **1. Data Preprocessing**
- **Data Cleaning:** Removal of unnecessary columns and handling of categorical variables.
- **Encoding:** 
  - Ordinal encoding for RAM and ROM sizes.
  - One-hot encoding for categorical features such as ROM type, OS, and RAM type.
  - Frequency encoding for processor, CPU, and GPU columns.
- **Feature Engineering:** 
  - Creation of new features such as combined RAM and ROM in GB.
- **Feature Scaling:** 
  - Standardization using `StandardScaler`.
- **Feature Selection:** 
  - Selection of top features using `SelectKBest` with `f_regression`.
- **Dimensionality Reduction:** 
  - Principal Component Analysis (PCA) to reduce feature space.

### **2. Model Training**
- **Base Models:**
  - Linear Regression
  - Decision Tree Regressor
  - Random Forest Regressor
  - XGBoost Regressor
  - Support Vector Regressor (SVR)
- **Hyperparameter Tuning:** 
  - Grid search for optimal parameters (commented in code, ready for use).

### **3. Ensemble Learning**
- **Stacking Regressor:** 
  - Combines SVR, Linear Regression, and XGBoost as base learners.
  - Uses Lasso Regression as the meta-learner.
  - Option to include original features in the meta-learner (`passthrough` parameter).

### **4. Model Evaluation**
- **Metrics:**
  - Root Mean Squared Error (RMSE)
  - Mean Absolute Error (MAE)
  - R² Score
- **Cross-Validation:** 
  - 10-fold cross-validation to assess model generalization.

---

## **Results**

### **Price Range in Dataset**
- **Minimum Price:** ₹9,999
- **Maximum Price:** ₹450,039
- **Mean Price:** ₹79,907

### **Stacking Regressor Performance**
- **Test Set:**
  - **RMSE:** ~25,347
  - **MAE:** ~16,657
  - **R² Score:** 0.81
- **Train Set:**
  - **RMSE:** ~20,602
  - **MAE:** ~14,080
  - **R² Score:** 0.89
- **10-Fold Cross-Validation:**
  - **Mean CV RMSE:** (see output for exact value)
  - **CV RMSE Std:** (see output for exact value)

### **Interpretation**
- The model achieves an R² score of ~0.81 on the test set, indicating it explains about 81% of the variance in laptop prices.
- The RMSE is about 32% of the mean price, which is moderate for this regression task.
- The gap between train and test performance is small, indicating minimal overfitting.

---

## **How to Improve**
- Further hyperparameter tuning for base and meta-learners.
- Experiment with additional features or alternative ensemble methods.
- Collect more data or engineer new features for better generalization.

---

## **Usage**
1. Place your dataset in the `./dataset/` directory.
2. Run the notebook `model.ipynb` step by step.
3. Review the evaluation metrics and visualizations for insights.

---

## **License**
This project is for educational
