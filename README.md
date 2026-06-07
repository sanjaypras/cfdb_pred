# cfdb_pred - College Football Recruiting Analysis

This project explores college football recruiting data from 2015–2021, split into two primary tasks: **Regression** and **Classification**.

**Dataset:** `cfb_recruits_2015_2021.csv`(attached)

### Features
* `year`, `name`, `position`, `height`, `weight`, `stars`, `rating`, `ranking`, `school`, `committed_to`, `city`, `state`, `country`, `lat`, `lng`
* **Rating:** Score from 0.6–1, showing the skill level of the recruit.
* **Ranking:** Number that rates a recruit in their relative year, starting at 1.
* **School:** High school of the recruit.
* **Committed_to:** College the recruit initially attended.
* **City, State, Country, Lat, Lng:** Where the recruit came from.

---

## Regression

For regression, we tried to predict someone's **rating** based on other features (e.g., height, weight, college committed to, etc.).

* **Linear Regression:** R2 score of about 0.4; not that good.
* **XGBoost:** R2 score similar; not that good. Most important feature: `stars`.
* **Neural Network (NN):** R2 score 0.81; much better. Most important feature: `stars`.

**Overall thoughts:** `stars` is very useful; it showed for XGB how much it helps predict rating. However, if stars and rating don’t correlate for an individual, the prediction will be heavily off.

---

## Classification

For classification, we tried to predict whether or not a recruit would go to a **Power 5** college using most of the same features as before.

### Decision Trees & Boosting
* **Decision Tree (max_depth=5):** Not good.
* **Decision Tree (max_depth=10):** Pretty good.
* **Random Forest:** Not good.
* **XGBoost:** Pretty good.

**XGBoost vs. Decision Tree:**
* Use the **Decision Tree** (good precision) if you want a safe bet list with no junk data—this will only give us good players but might miss some talent.
* Use **XGBoost** (good recall) if you are a scout who doesn't want to miss a single sleeper and is willing to manually vet the extra results—this will give us a lot of potentially good players, but some might not be good.

### Neural Network & SHAP Analysis
We next tried a **Neural Network**, which performed much better. We ran a SHAP analysis on this model.
> **Key Finding:** It turns out that if you are a **punter**, you have a much higher chance to make it to the Power 5.

**Thoughts:** `power_5` is pretty easy to predict, since most of the models had pretty good results.

---

## Conclusion
Overall, this dataset had few outliers and clear questions to ask. I liked working with the data. Its being college football, something I am already familiar with, heped me decipher the data more too.
