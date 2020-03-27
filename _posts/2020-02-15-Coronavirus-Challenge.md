---
title: "Coronavirus Challenge"
excerpt: "I joined a challenge to develop a solution to an open problem of easing the effects of the 2020 pandemic"
toc: true
toc_sticky: true
header:
  overlay_image: https://cdn.pixabay.com/photo/2020/03/26/16/53/corona-4971013_1280.jpg
  caption: "Photo by Pixabay"
tags: 
  - Data Visualization
  - Flask 
  - Dash
  - Python
  - React
  - Heroku
  - Git
  - Plotly
  - Health
  - Containers
---

I decided to join a challenge to bring to the table some idea or solution that could help ameliorate the current pandemic burden on our society.  
The challenge was very open on the types of solutions you wanted to work on and the scope of it in terms of working for something local or global.  
This challenge was issued in January 2020, very early in the epidemic lifetime and even before it was considered a pandemic, but it is worth noting that 
currently there are very big competitions on this same problem hosted by companies such as [Kaggle](https://www.kaggle.com/).  
The solution received a prize in the actual competition which has already ended.

## The problem to solve
When I was starting working on this, there were not many sources of data of the confirmed cases of Covid-19 other than the PDFs published by the [WHO](https://www.who.int/) so I decided it was worth to extract the data from these "non-consumable" data sources and publish them in a visualization dashboard.  
By the time the competition ended, there were many (an understatement) of these visualizations, the most famous of them probably being the [Johns Hopkins Dashboard](https://coronavirus.jhu.edu/map.html).  
This made the solution redundant so I decided to localize it to Mexico since the data was only being visualized partially in all of those dashboards. 
Particularly, the data that was missing was the decomposition of all cases by state, so I decided to show this information in a map and add some very important metrics also missing in other dashboards such as the historic line of active cases  
*Active = Confirmed - Recovered - Deaths*.

## The solution components
As of today, the mexican government is still publishing the official figures in PDF format which is not consumable as is and needs pre-processing to be used by any analytic work.  
The solution therefore is decomposed in the following parts:
- Extract the data from the PDF and put it in a structured format, in this case CSV. 
- Persist and publish this data and the original sources in a [Github repository](https://github.com/jairgs/Covid19MexicoDatos) so more people can use it to develop their own solutions and tools to help.
- Develop and publish a visualization dashboard of this data in a simple yet impactful way that communicates the information quickly. [I deployed the app here](https://covid19-mexico.herokuapp.com/).

## The dashboard
The dashboard was developed using the [Dash Framework](https://plotly.com/dash/) which uses **_React_** and **_Python_** to develop interactive dynamic visualizations and can be easily deployed using **_Flask_**.  

I won't go into much detail about the specifics of the code in this entry, but the code consists simply of two parts:
- **The layout**, which is the arrangement of graphics and page elements to be served. I used **_bootstrap_** to make the front-end responsive for comfortable use in mobile devices.
- **The backend**, which is the logic and brains of the application. This contains the data wrangling needed to feed the plots and the decorators to route the app and make the plots interact with one another.

The app uses git version control, is containerized and is being deployed in [Heroku](https://www.heroku.com/).

## Final Remarks
As mentioned before, you can [visit the app here](https://covid19-mexico.herokuapp.com/) and it is being updated once a day as the data is published by the [Mexican Health Entity](https://www.gob.mx/salud).    
I keep adding elements to the dashboard that add value to the community. 
