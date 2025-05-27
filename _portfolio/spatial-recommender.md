---
title: "Geospatial Modelling with Emphasis on Expansion Strategy and App with Interactive Map"
collection: portfolio
permalink: /portfolio/spatial-recommender/
date: 2024-04-15
layout: single
classes: wide
share: false
author_profile: true
excerpt: "categories:
  - geospatial analytics
  - public sources data integration
  - survey inference
  - classification
  - dashboarding
  - web app
  - maps integration
  - cloud deployment
  - quantitative index generation"

feature_row: true

header:
  image: https://images.unsplash.com/photo-1446776899648-aa78eefe8ed0?q=80&w=3872&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
  teaser: https://images.unsplash.com/photo-1446776899648-aa78eefe8ed0?q=80&w=3872&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
---

![](/assets/postsImages/sr-gif.gif)

### Overview

This project delivers a reusable and data-driven tool for identifying optimal retail expansion zones in Mexico using a combination of socioeconomic prediction, geospatial clustering, and interactive visualization. Originally designed for a national pharmacy chain, the solution was later containerized for adaptability across industries.

### Client

Pharmacy retail chain operating nationally in Mexico, targeting end customers.

### Challenge

Identify high-potential urban and semi-urban areas for new store locations—beyond traditional site selection methods—by leveraging socioeconomic and geospatial indicators.

### 🔍 Methodology

#### 1. Socioeconomic Prediction per City Block

Each block in the country (based on INEGI census boundaries) was classified into one of ten income groups. This required reconciling two different data sources:

- **Census data:** Universally available but limited in detail.
- **ENIGH income survey:** Rich in household-level income and consumption data, but available only for a representative sample.

To bridge the gap, I trained a **probabilistic classifier** assuming an underlying income distribution. Input features included basic household characteristics such as number of rooms, access to services, and education level. The model produced predicted income deciles for each block.

#### 2. Expansion Potential Index

A custom index was developed to quantify the potential of each area for new retail locations. It included three core components:

- **Direct Competition Score:** Density and proximity of competing pharmacies and retailers.
- **Health Services Cluster Score:** Count of clinics, hospitals, laboratories, and senior care facilities.
- **Market Size Score:** Total residential population, estimated number of households in the target income range, and floating population estimates.

Each component was normalized and combined into a unified expansion index.

#### 3. Hexagonal Spatial Aggregation (H3 Indexing)

To unify varying spatial resolutions, I applied **H3 hexagonal binning**, which allows consistent spatial aggregation and comparison.

This involved:

- Intersecting census block-level predictions with H3 cells.
- Aggregating POIs and population data by hexagon.
- Performing spatial joins using `geopandas` and `shapely`.

#### 4. Interactive Deployment & Visualization

The final output was an interactive web application featuring:

- **Mapbox GL JS** for high-performance rendering.
- **Color-coded H3 hex layers** representing the expansion index.
- **Interactive tooltips** and togglable data layers.
- **Dockerized deployment**, allowing easy reuse and deployment on various environments.

[🌐 You can explore the live version here](sr.jairgs.vip)

### ⚙️ Technologies Used

Machine Learning: Scikit-learn (classification), custom feature engineering

Geospatial: geopandas, shapely

Deployment: Docker

Frontend Mapping: Mapbox GL JS, JavaScript

Backend Scripting: Python, Pandas

### 🎯 Impact

This tool enabled the client to:

Pinpoint high-opportunity zones not obvious via traditional heuristics.

Prioritize expansion decisions backed by socio-spatial analytics.

Reuse the methodology in future cities or verticals with minimal reconfiguration.

### 📌 Lessons & Next Steps

Census-Survey Fusion: Careful matching of sparse and dense datasets can yield actionable predictions at national scale.

**Scalability**  
Containerization and modular architecture facilitate cross-industry deployment.

**Next Steps**  
Integrating real-time foot traffic and POS data for continuous optimization. Add layers and more interactive customization.
