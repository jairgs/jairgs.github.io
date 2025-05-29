---
title: "Churn Prediction Using Voice Data and Customer Transactions"
collection: portfolio
permalink: /portfolio/churn-prediction/
date: 2019-08-01
layout: single
classes: wide
share: false
author_profile: true
excerpt: "Developed a churn prediction pipeline by extracting features from phone call audio data and combining them with transactional patterns to detect customer disengagement."
categories:
  - churn prediction
  - NLP
  - computer audition
  - dashboarding
  - AI

header:
  image: https://images.unsplash.com/photo-1611532736579-6b16e2b50449?q=80&w=3826&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
  teaser: https://images.unsplash.com/photo-1611532736579-6b16e2b50449?q=80&w=3826&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
---

### 🏢 Background

[Cemex](https://www.cemex.com), one of Mexico’s largest industrial companies with global operations needed to anticipate customer churn using underutilized audio data sources and other customer transactional data.

---

### 🎯 Objective

Identify high-risk customers by analyzing **phone conversation audio** and **historical transaction patterns**, then combine insights into a predictive model for churn detection.

---

### 🔊 Audio Data Processing

Cemex’s call center was the primary order channel, and **years of audio logs** had never been leveraged. The steps included:

- **Async pipeline for deep speech-to-text APIs**, carefully handling request tracking and response pairing due to high latency.
- **Translation of Spanish transcripts** using neural machine translation services to ensure consistency across the dataset.
- **Feature extraction** using NLP models to detect:
  - Sentiment
  - Tone
  - Conversation duration, frequency, resolution indicators
- Mapping those features back to unique customer profiles.

---

### 🧾 Transactional Data & Churn Labeling

- Aggregated **multi-year transactional records** (order frequency, product mix, payment patterns).
- Engineered time-based features and behavioral segments.
- Defined a **churn label** based on long inactivity periods or termination signals in the customer relationship.
- Merged behavioral and voice-derived data per customer.

---

### 🤖 Predictive Modeling

- Trained classification models to predict churn risk:
  - Balanced classes using oversampling/undersampling techniques.
  - Applied **cross-validation**, **probability calibration**, and **Optuna-based hyperparameter tuning**.
- Compared multiple models (e.g., XGBoost, Random Forest, Logistic Regression).
- Calibrated probability thresholds for actionable insights.

---

### 🛠️ Deliverables

- Reusable prediction pipeline for inference on new customer data.
- Final churn risk scores for each customer.
- A lightweight dashboard with filters for:
  - Churn probability range
  - Segment analysis
  - Voice/NLP signal contributions
- Documentation for retraining and model deployment.

---

### ⚙️ Technologies Used

- **NLP & Audio**: <speech-to-text API used> `nltk`, `textblob`, etc.
- **Translation**: `IBM Cloud, AI & Watson`,
- **Data Science**: pandas, scikit-learn, XGBoost
- **Pipeline orchestration**: Python3
- **Dashboard**: Power BI

---

### 📌 Impact

- Enabled Cemex to act early on potential churn, particularly in clients with unresolved call issues or sentiment shifts.
- Surfaced new insights from an **untapped audio dataset**, transforming voice data into strategic intelligence.

> Feel free to [contact me](/about/) if your organization is exploring voice data or customer behavior analytics.
