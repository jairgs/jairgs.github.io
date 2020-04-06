---
title: "Coronavirus Mexico Data API"
excerpt: "I worked on making the Coronavirus data from Mexico available through an API"
toc: true
toc_sticky: true
header:
  overlay_image: https://cdn.pixabay.com/photo/2020/03/19/21/35/covid-4948866_1280.jpg
  overlay_filter: .8
  caption: "Photo by Pixabay"
tags: 
  - Flask 
  - API
  - Python
  - Heroku
  - Health
---

Last week I wrote about the [repository](https://github.com/jairgs/Covid19MexicoDatos) I am maintaining to persist the data from Mexico Coronavirus cases which involves programmatically extracting the data figures published by the Mexican Health Bureau in PDF format.  
Since the data in PDF format is not consumable as is, this repository constitutes the only available daily data (to my knowledge) of the Coronavirus cases in Mexico which not only contains valuable information about the evolution of the infection inside the country, it also has granularity at the Sate, Sex, Age and other individual-level dimensions. 

### The API
Building on maintaining this data-set so other people can use it to build tools and application of social importance, I worked on a simple API to query this data-set.
The API is deployed on **Heroku** using **Flask RESTful** and has 5 elementary components:
- **All Data** - To query all historic data run a get method to   
`http://corona-api-mexico.herokuapp.com/`
- **State Data** - To query all data from a specific state run a get method to  
`http://corona-api-mexico.herokuapp.com/state/{state}`  
Use URL encoding for example Nuevo Leon would be   
`http://corona-api-mexico.herokuapp.com/state/Nuevo%20León`
- **Date Data** - To query a specific state run a get method to  
`http://corona-api-mexico.herokuapp.com/date/{yyyy-mm-dd}`  
- **Aggregated state** - If you would like to aggregate the state data and get the total cases by date for a specific state only add the "agg" parameter to the url like so
`http://corona-api-mexico.herokuapp.com/state/{State}/agg`  
- **Aggregated date** - Same functionality on the date; if you would like to see only the total cases by state on a specific date add "agg" to the date query:
`http://corona-api-mexico.herokuapp.com/date/{yyyy-mm-dd}/agg`  

The results are returned in **JSON** format and are updated daily as the data is made available.

You can check out the [repository of this API](https://github.com/jairgs/coronavirusMexicoAPI).