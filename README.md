# cfdb_pred

This was split into two main tasks: regression and classification

Dataset: cfb_recruits_2015_2021.csv

### Features:[year,name,position,height,weight,stars,rating,ranking,school,committed_to,city,state,country,lat,lng]  
Rating: Score from 0.6-1, showing skill level of recruit  
Ranking: Number that retes recruit in their relative year, starting at 1  
School: High school of recruit  
Committed_to: College that recruit went to intially  


## Regression

For regression, we tried to predict someones rating based on other features(eg height, weight, college commited to, etc)


## Classification

For classification, we tried to predict whteher or not a recruit would go to a Power 5 college using most of the same fatures as before
