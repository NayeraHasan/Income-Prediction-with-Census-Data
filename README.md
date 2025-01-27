# Income-Prediction-with-Census-Data

This repository contains an end-to-end machine learning project aimed at predicting whether an individual's income exceeds $50K based on demographic and employment features. The project follows the machine learning lifecycle and uses the 1994 Census dataset.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Problem Statement](#problem-statement)
- [Approach](#approach)
- [Models and Evaluation](#models-and-evaluation)
- [Key Results](#key-results)
---

## Project Overview

This project solves a **binary classification problem** to predict income levels (`<=50K` or `>50K`) using machine learning. The goal is to build a robust, accurate model to enable businesses to make data-driven decisions, such as targeting high-value customers or optimizing marketing strategies.

---

## Dataset

The dataset used is the **Census 1994 data**, containing 32,561 entries with demographic and employment information. Key features include:
- `age`, `education-num`, `hours-per-week`, `marital-status`, `occupation`, etc.
- Target variable: `income_binary`, which categorizes income as `<=50K` or `>50K`.

### Challenges
- Missing data in features like `workclass`, `occupation`, and `native-country`.
- Class imbalance between income groups.
- Outliers and skewed distributions in numerical features.

---

## Problem Statement

### Objective
Predict whether an individual's income exceeds $50K based on demographic and employment features.

### Type of Problem
- Supervised Learning
- Binary Classification Problem

---

## Approach

1. **Data Preprocessing**
   - Handle missing values using median (numerical) and mode (categorical).
   - Normalize numerical features (`age`, `hours-per-week`).
   - Encode categorical features (e.g., `marital-status`, `workclass`) using one-hot encoding.
   - Engineer features (e.g., flagging presence of capital gains/losses).

2. **Feature Selection**
   - Retained: `age`, `education-num`, `hours-per-week`, `marital-status`, `occupation`, `relationship`.
   - Removed: Redundant features (`education`, `fnlwgt`).

3. **Model Training**
   - Evaluated multiple models: Logistic Regression, Random Forest, Gradient Boosting Machines (GBM).
   - Applied hyperparameter tuning using GridSearchCV.

4. **Evaluation Metrics**
   - Accuracy, Precision, Recall, F1-Score, ROC-AUC.

---

## Models and Evaluation

### Baseline Results
- **Accuracy**: 85%
- **Precision**: 71% (for `>50K`)
- **Recall**: 63% (for `>50K`)
- **ROC-AUC**: 0.89

### Optimized Model (Random Forest with Tuning)
- **Accuracy**: 86%
- **Precision**: 76%
- **Recall**: 61%
- **ROC-AUC**: 0.91

---

## Key Results

- **Confusion Matrix**:
  - True Negatives: 4548
  - True Positives: 982
  - False Positives: 394
  - False Negatives: 589

- **ROC Curve**: Demonstrated a high area under the curve (AUC = 0.91), indicating strong classification performance.

---
