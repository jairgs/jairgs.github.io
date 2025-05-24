---
title: "Geospatial Modelling with Emphasis on Expansion Strategy and App with Interactive Map"
collection: portfolio
permalink: /portfolio/spatial-recommender/
date: 2024-04-15
layout: single
classes: wide
author_profile: true
excerpt: "Developed a scalable solution to identify high-potential retail zones across Mexico using census-based income prediction, competitor clustering, and healthcare infrastructure analysis. Aggregated data with hexagons and deployed an interactive Mapbox-based app. Enabled data-driven site selection for a national pharmacy chain. Built with Python, scikit-learn, Docker, and geopandas."
tags:
  - retail
  - machine learning
  - geospatial
  - docker
  - mapbox

feature_row: true

header:
  image: https://plus.unsplash.com/premium_photo-1712175879037-86f0007dc7dd?q=80&w=3840&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
  teaser: https://plus.unsplash.com/premium_photo-1712175879037-86f0007dc7dd?q=80&w=3840&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
---

![](/assets/postsImages/sr-gif.gif)

### Overview

This project delivers a reusable and data-driven tool for identifying optimal retail expansion zones in Mexico using a combination of socioeconomic prediction, geospatial clustering, and interactive visualization. Originally designed for a national pharmacy chain, the solution was later containerized for adaptability across industries.

### Client

Pharmacy retail chain operating nationally in Mexico, targeting end customers.

### Challenge

Identify high-potential urban and semi-urban areas for new store locations—beyond traditional site selection methods—by leveraging socioeconomic and geospatial indicators.

### 🔍 Methodology

1. Socioeconomic Prediction per City Block
   Each block in the country (from INEGI census boundaries) was classified into one of ten income groups. The challenge involved bridging two distinct data sources:

Census data: Universally available but limited in detail.

ENIGH income survey: Rich in household-level income and consumption, but only available for a representative sample.

To bridge the gap, I trained a probabilistic classifier assuming an underlying income distribution. Features included basic household characteristics (e.g., number of rooms, services), and outputs were income deciles.

2. Expansion Potential Index
   A custom index was developed to assess expansion suitability, composed of three key components:

Direct Competition Score: Based on proximity and density of competing pharmacies and retailers.

Health Services Cluster Score: Aggregates presence of clinics, hospitals, laboratories, and senior care homes.

Market Size Score: Includes residential population, estimated number of households in the target income range, and floating/transient population metrics.

Each factor was standardized and combined into a unified index.

3. Hexagonal Spatial Aggregation

To unify varying spatial resolutions across data sources, I applied hexagonal binnings. This allowed aggregation and comparison of metrics across consistent spatial units, enabling more actionable visual insights.

This involved:

Intersecting census block-level predictions with hexagon cells.

Aggregating POIs and population data spatially.

Spatial joins using geopandas and shapely.

4. Interactive Deployment & Visualization
   The final product was an interactive web app built with:

Mapbox GL JS for high-performance map rendering.

Color-coded hexagon layers to represent the expansion index.

Tooltips and togglable layers to show detailed metrics per area.

Containerized with Docker, making it portable and easily deployable on cloud or local infrastructure.

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

Scalability: Containerization and modular architecture facilitate cross-industry deployment.

Next Steps: Integrating real-time foot traffic and POS data for continuous optimization. Add layers and more interactive customization.
