# Task 1: Data Analysis & Preprocessing for Fraud Detection

## Overview
This task focuses on preparing a clean, feature-rich dataset for fraud detection modeling. It includes data cleaning, exploratory data analysis (EDA), geolocation integration, feature engineering, and strategies for handling class imbalance.

## Objectives
- **Data Cleaning:** Handle missing values, duplicates, and data type conversions.  
- **Exploratory Data Analysis (EDA):** Analyze transaction patterns, fraud distributions, and key features.  
- **Geolocation Integration:** Map IP addresses to countries for geo-based risk assessment.  
- **Feature Engineering:** Create time-based, behavioral, and categorical features.  
- **Preprocessing:** Standardize numerical features, encode categorical variables, and prepare for modeling.  
- **Class Imbalance Handling:** Identify imbalance issues and plan for SMOTE application during training.  

## Datasets Used
- **Fraud_Data.csv:** Main transaction data with user details, purchase info, and fraud labels.  
- **IpAddress_to_Country.csv:** IP address ranges mapped to countries for geolocation.  
- **Processed Output:** `fraud_processed.csv` saved in `../data/processed/`.  

## Key Findings from EDA
- **Class Imbalance:** Fraudulent transactions are ~0.6% of the data, requiring specialized metrics like Precision-Recall AUC.  
- **Fraud Patterns:** Higher purchase values and quick post-signup transactions are associated with fraud.  
- **Geolocation Insights:** Certain countries show elevated fraud rates, useful for risk scoring.  
- **Feature Distributions:** Age and purchase value distributions differ between legitimate and fraudulent transactions.  

## Notebooks
- `eda-fraud-data.ipynb` – Comprehensive EDA and preprocessing for the fraud dataset.  
- `eda-creditcard.ipynb` – EDA for credit card transaction data (if applicable).  

## Dependencies
- pandas  
- numpy  
- matplotlib  
- seaborn  
- scikit-learn  

**Install via:**  
```bash
pip install -r requirements.txt




# Fraud Detection – Task 2 (Interim-2)

This repository contains the **Task 2 modeling notebook** for the 10 Academy AI Mastery project.  
The goal is to **train and evaluate models** for detecting fraudulent e-commerce transactions.

---

## Project Structure

```

fraud-detection/
├── notebooks/
│   └── modeling_task2.ipynb   
├── models/                    
├── README.md                  

```
## Task 2 Workflow

1. **Load Processed Data**  
2. **Select Features**: numeric + small categorical features (`purchase_value`, `age`, `hour_of_day`, `day_of_week`, `time_since_signup`, `sex`)  
3. **Train-Test Split** (stratified)  
4. **Handle Imbalance**: SMOTE applied on training set  
5. **Model Training**: Logistic Regression (baseline) and Random Forest (selected)  
6. **Evaluation Metrics**: F1-Score, AUC-PR, Confusion Matrix  

---

## Notes

- Random Forest outperformed Logistic Regression on F1-Score and AUC-PR.  
- High-cardinality features (IP, device, browser, source) were dropped to save memory.  
- Small categorical features were label-encoded.  


```
# Task 3: SHAP Explainability for Fraud Detection

## Overview

This task focuses on **model explainability** for the best fraud detection model from Task 2. The goal is to understand what drives the model's predictions and provide actionable insights for the business.

The notebook `notebooks/shap-explainability.ipynb` contains:

- Built-in **feature importance** extraction and visualization  
- **SHAP analysis** for global and local explanations  
- **Waterfall plots** for True Positive (TP), False Positive (FP), and False Negative (FN) cases  
- Comparison between **built-in feature importance** and **SHAP importance**  
- **Interpretation of model logic** (global vs. local)  
- **Actionable business recommendations** based on insights

---

## Dependencies

The notebook requires the following Python packages:

- `pandas`  
- `numpy`  
- `matplotlib`  
- `joblib`  
- `shap`

Install missing packages using pip:

```bash
pip install pandas numpy matplotlib joblib shap

=======


