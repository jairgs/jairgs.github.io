---
title: "Monthly Demand Forecasting for a multi-billion dollar multinational in the advanced materials sector"
collection: portfolio
permalink: /portfolio/demand-forecasting/
date: 2025-05-15
layout: single
excerpt: "Built tailored forecasting models for unit sales across product-region segments using cross-validated model selection and Bayesian optimization."
tags: [forecasting, retail, machine learning, prophet, time series]
feature_row: true
header:
  overlay_image: /assets/images/post-forecast.png
image:
  path: /assets/images/post-forecast.png
  alt: "Demand Forecast"
---

In this project, I was tasked with forecasting unit sales for the next six months using historical monthly data from a large multinational in the industrial coatings sector (Mexican subsidiary, anonymized for confidentiality).

### 🧠 Project Scope

The goal was to provide accurate volume forecasts for various brand-region combinations. I worked with monthly time series data that included:

- Seasonality and trend components
- External regressors (1 categorical, 1 continuous)
- Autoregressive structure

### 🛠️ Modeling Strategy

Rather than building a single global model, I opted for a **grouped modeling approach**, training **one model per (brand, region) segment**. This allowed for finer control and more accurate modeling of local patterns.

I evaluated several forecasting models per group:

- **SARIMAX** (with and without differencing)
- **Seasonal Autoregressive State Space (SAS)**
- **Holt-Winters**
- **Prophet**

Each model was tuned using **Optuna** for hyperparameter optimization with a **Bayesian search strategy**, guided by a **5-fold expanding window cross-validation** process. The primary evaluation metric was **Root Mean Square Error (RMSE)** on out-of-fold predictions.

---

### 📊 Cross-Validation Results

Below is a summary of cross-validation performance for the top 10 brand-region groups:

![Cross-validation results](/assets/postsImages/forecast-results.png)

---

### 📈 Forecasts

For each group, I generated:

- **Out-of-fold predictions** (to visualize model accuracy)
- **Future forecasts** (next 6 months)
- **95% prediction intervals**

The following plot is representative of the final outputs delivered, for one of the top groups that was fit best by a **Prophet** model:

![Forecast plot](/assets/postsImages/prophet-forecast.png)

Consider that this is an out-of-fold prediction plot, not a training set fit, which would likely look very close to the actual data for all months.

---

### 🧹 Data Handling

Significant effort went into preprocessing and cleaning:

- Outlier handling
- Missing value imputation
- Encoding categorical features
- Normalization of external regressors

The data was aligned to ensure all time series were consistent and complete before modeling.

---

### 🧪 Deliverables and Deployment

The final deliverables included:

- Forecast plots and prediction files for each group
- Saved model files per group for potential reuse
- Clear documentation on retraining and inference strategy

While the project didn't include deployment, the structure supports **batch retraining and monthly prediction**, making it easy to integrate into a production pipeline.

---

### 💼 Value

This project demonstrates my ability to:

- Work independently on large forecasting initiatives
- Identify and correct input data errors and inconsitencies
- Select and validate models in a robust, unbiased way
- Communicate results clearly and professionally

If your organization needs time series forecasting or custom AI solutions, feel free to [reach out](/about/) — I'd be happy to collaborate.
