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

Tried: linear regression, r2 score of about 0.4, not that good   
xgboost, r2 score similar, not that good  
nn, r2 score 0.81, much better  


## Classification

For classification, we tried to predict whteher or not a recruit would go to a Power 5 college using most of the same fatures as before  

Tried different kinds of decision trees
decision tree(max_depth=5) - not good  
decision tree(max_depth=10) - pretty good  
reandom forest - not good  
xgb - pretty good  
  
xgb vs decision tree:  
use the decision tree(good precision) if you want a safe bet list with no junk data - this will only give us good players but might miss some talent

use xgboost(good recall) if you are a scout who doesn't want to miss a single sleeper and is willing to manually vet the extra results - this will give us a lot of potentially good players but some might not be good


next tried nn, much better, and we ran shap analysis.  

turns out that if you are a punter, you have a much higher chance to make it to power 5.

