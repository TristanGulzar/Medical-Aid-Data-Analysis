# Medical Aid Cost Prediction - Linear Regression Model

## 📘 Overview
This project presents a machine learning model developed to predict medical insurance charges based on client demographics and lifestyle choices. The goal is to assist medical aid schemes in tailoring premiums more accurately, using variables such as age, sex, BMI, number of children, smoking status, and region.

## 🧠 Objectives
- Analyse the insurance dataset to identify trends and outliers.
- Build a linear regression model to predict charges.
- Evaluate the model using standard regression metrics.

## 📁 Dataset
The dataset used is publicly available via Kaggle: [Medical Cost Personal Dataset](https://www.kaggle.com/datasets/mirichoi0218/insurance).

### Features:
- `age`: Age of the individual
- `sex`: Gender of the individual
- `bmi`: Body mass index
- `children`: Number of children
- `smoker`: Smoking status
- `region`: Region of residence
- `charges`: Target variable (medical cost)

## 📊 Exploratory Data Analysis (EDA)
- Verified data types and checked for missing values.
- Identified outliers, particularly in `charges`, but chose to retain them as they represent valid real-world data.
- Applied histograms and boxplots to examine skewness and distributions.
- Noted that `charges`, `bmi`, and `age` are right-skewed.

## 🛠️ Feature Engineering
- One-hot encoded categorical features (`sex`, `smoker`, `region`).
- Created an interaction feature: `bmi_smoker = bmi > 30 * smoker_yes = 1`.
- Applied log transformation to normalise skewed continuous variables.

## 🧪 Model Training
- Trained a standard Linear Regression model using sklearn.
- Added Ridge Regression (L2 regularisation) with 5-fold cross-validation.
- Compared both models to test for improvements.

## ✅ Evaluation Metrics
**Linear Regression:**
- R² Score: 0.91
- MAE: 2266.68
- RMSE: 3863.17

**Ridge Regression:**
- R² Score: 0.906
- CV Average R²: 0.895

Conclusion: The standard Linear Regression slightly outperformed Ridge, indicating the model is already well-regularised.

## 📈 Visualisations
- Histograms & boxplots for feature distribution
- Residual vs predicted plot
- Actual vs predicted scatter plot
- Coefficient importance bar chart

## 📌 Conclusion
The model effectively predicts medical charges with a high degree of accuracy. Feature engineering, particularly the smoker*BMI interaction, played a key role in performance. Ridge Regression did not offer a significant improvement, confirming that the model was stable and generalisable. This solution offers a valuable starting point for dynamic pricing strategies in the medical aid industry.

