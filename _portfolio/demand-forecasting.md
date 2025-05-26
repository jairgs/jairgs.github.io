---
title: "Monthly Demand Forecasting for a multi-billion dollar multinational in the advanced materials sector"
collection: portfolio
permalink: /portfolio/demand-forecasting/
date: 2025-05-15
layout: single
classes: wide
author_profile: true
excerpt: "Built tailored forecasting models for unit sales across product-region segments using cross-validated model selection and Bayesian optimization."
categories:
  - demand forecasting
  - offline inference
  - timeseries analysis
  - data processing

feature_row: true

header:
  image: https://images.unsplash.com/photo-1594999853137-3188c27b2886?q=80&w=3731&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
  teaser: https://images.unsplash.com/photo-1594999853137-3188c27b2886?q=80&w=3731&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
# sidebar:
#   - title: "Role"
#     image: http://placehold.it/350x250
#     image_alt: "logo"
#     text: "Designer, Front-End Developer"
#   - title: "Responsibilities"
#     text: "Reuters try PR stupid commenters should isn't a business model"
# gallery:
#   - url: /assets/images/unsplash-gallery-image-1.jpg
#     image_path: assets/images/unsplash-gallery-image-1-th.jpg
#     alt: "placeholder image 1"
#   - url: /assets/images/unsplash-gallery-image-2.jpg
#     image_path: assets/images/unsplash-gallery-image-2-th.jpg
#     alt: "placeholder image 2"
#   - url: /assets/images/unsplash-gallery-image-3.jpg
#     image_path: assets/images/unsplash-gallery-image-3-th.jpg
#     alt: "placeholder image 3"
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

<figure>
    <a href="/assets/postsImages/forecast-results.png"><img src="/assets/postsImages/forecast-results.png"></a>
    <figcaption>Cross-Validation Results.</figcaption>
</figure>

---

### 📈 Forecasts

For each group, I generated:

- **Out-of-fold predictions** (to visualize model accuracy)
- **Future forecasts** (next 6 months)
- **95% prediction intervals**

The following plot is representative of the final outputs delivered, for one of the top groups that was fit best by a **Prophet** model:

<figure>
    <a href="/assets/postsImages/prophet-forecast.png"><img src="/assets/postsImages/prophet-forecast.png"></a>
    <figcaption>Forecast Plot.</figcaption>
</figure>

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
