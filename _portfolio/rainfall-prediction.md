---
title: "Rainfall Prediction – Kaggle Competition"
excerpt: "High-performance rainfall classification model (99.95 ROC AUC), built with Optuna-tuned XGBoost and deployed as a Dockerized Streamlit app for reproducible forecasting."
layout: single
classes: wide
share: false
permalink: /portfolio/rainfall-prediction/
collection: portfolio
date: 2025-03-26
categories:
  - Binary Classification
  - Kaggle
  - Streamlit
  - Containerization
  - Hyperparameter Optimization
  - Cross Validation

header:
  teaser: https://images.unsplash.com/photo-1600697230088-4992c83b2804?q=80&w=3870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
  image: https://images.unsplash.com/photo-1600697230088-4992c83b2804?q=80&w=3870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
---

## 🌧️ Project Overview

This project was developed for the [Kaggle “Binary Prediction with a Rainfall Dataset” competition](https://www.kaggle.com/competitions/binary-prediction-with-a-rainfall-dataset). The goal was to predict the occurrence of rainfall using a set of environmental features. My final solution achieved a **public ROC AUC score of 99.95**, placing it among the top scores in the competition.

---

## 🔍 Problem Scope

Generate predictions for the full test set with the probability of rain conditional to the available regressors (e.g. temperature, wind speed, cloud cover, and humidity).  
60% of the test set is used only at the end of the competition, when the private score is computed, the remaining 40% is used to calculate the public score with each submission (it's unknown which samples are part of the public score computation.)

---

## 🛠️ Technical Approach

### ✅ Feature Engineering

- Normalized key predictors and engineered meaningful ratios and deltas.
- Created visualizations to validate distributional consistency between training and test data.
- Analyzed correlations with the target to prioritize high-signal features.

### ✅ Modeling

- Trained two high-performing models:
  - **Random Forest Classifier**
  - **XGBoost Classifier**, using **GPU acceleration via CUDA** for faster tuning and inference
- Used **Optuna** for **Bayesian hyperparameter optimization** with custom search spaces.

### ✅ Validation Strategy

- Applied **Grouped KFold** and **Random KFold** to ensure the model generalized across known splits.
- Carefully monitored overfitting using out-of-fold performance.

---

## 🚀 Deployment

To demonstrate the model's predictions interactively and reproducibly, I:

- Built a **Streamlit app** that allows exploration of predictions and feature importances.
- Packaged the entire app using **Docker** to simplify reproducibility.
- Hosted the application on a **private cloud server** accessible here:

👉 [Live App](https://rainfall.jairgs.vip)

---

## 📊 Visual Preview

<figure>
    <a href="/assets/postsImages/rainfall.png"><img src="/assets/postsImages/rainfall.png"></a>
    <figcaption>Screenshot of the Rainfall App</figcaption>
</figure>

---

## 🧠 Lessons Learned

- GPU acceleration can be very valuable even for structured data when doing intensive feature selection and hyperparameter optimization.
- Cross validation is still one of the best tools in the ML field.
- Binary classification with Random Forest and XGboost are still very powerful tools.

---

## 📁 Links

- 📈 [Kaggle Competition Page](https://www.kaggle.com/competitions/binary-prediction-with-a-rainfall-dataset)
- 🐍 GitHub Repo: https://github.com/jairgs/kaggle-rainfall-prediction

---

If you'd like help writing the missing "Lessons Learned" section or a custom visual banner, I can help with that too!
