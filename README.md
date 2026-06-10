# Logistic-Regression-Intuition
## 📊 Logistic Regression: Binary & Multiclass Classification

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine_Learning-F7931E.svg)](https://scikit-learn.org/)

### 🎯 Project Overview
This repository features a complete, interview-ready implementation of Logistic Regression algorithms for both Binary and Multiclass classification scenarios[cite: 1]. It demonstrates core data science workflows, including model training, probability prediction, and rigorous hyperparameter tuning to optimize model performance[cite: 1].

### 🧠 Methodology & Setup
* **Data Generation:** Utilized `sklearn.datasets.make_classification` to create standardized synthetic datasets featuring 1,000 samples and 10 features[cite: 1].
* **Data Splitting:** Applied a 70/30 train-test split to reliably evaluate out-of-sample accuracy[cite: 1].
* **Hyperparameter Tuning:** Conducted exhaustive parameter optimization using both `GridSearchCV` and `RandomizedSearchCV` (leveraging 5-fold Stratified K-Fold cross-validation) to isolate the optimal combination of regularization penalties (`l1`, `l2`, `elasticnet`) and solvers[cite: 1].

### 📈 Model Performance

#### 1. Binary Classification
* **Baseline Accuracy:** The initial, untuned model achieved an accuracy of 84.6%[cite: 1].
* **Optimized Model:** Post-tuning via `GridSearchCV`, the accuracy improved to 85.3%[cite: 1].
* **Best Parameters:** The model performed best using an L2 penalty, the `newton-cg` solver, and an inverse regularization strength of `C=0.01`[cite: 1]. *(Note: `RandomizedSearchCV` identified a fast alternative configuration using an L1 penalty and `liblinear` solver, yielding 84.6% accuracy[cite: 1]).*

#### 2. Multiclass Classification (One-vs-Rest)
* **Baseline Accuracy:** The initial One-vs-Rest (OVR) configuration yielded an accuracy of 78.3%[cite: 1].
* **Optimized Model:** After running grid search tuning, the overall test accuracy increased to nearly 79%[cite: 1].
* **Best Parameters:** The most effective parameters for separating the three classes were an L1 penalty, the `liblinear` solver, and `C=0.1`[cite: 1].

#### 📊 Final Multiclass Evaluation
Below is the classification report summary for the tuned multiclass model[cite: 1]:

| Target Class | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Class 0** | 0.92 | 0.78 | 0.85 | 105 |
| **Class 1** | 0.75 | 0.71 | 0.73 | 97 |
| **Class 2** | 0.71 | 0.87 | 0.78 | 98 |
| **Overall (Weighted Avg)**| **0.80** | **0.79** | **0.79** | **300** |
