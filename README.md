#  Does the number of steps and ingredients effect the average rating of the recipes?

by Akash Juwadi (ajuwadi@ucsd.edu)

---

## Introduction

The goal of this project is to solve the main question of whether of not the number of steps and ingredients effects the average rating of the recipes? In order to do this we will be using the recipes dataset which contains various different recipes and information about the different recipes.This question is interesting to look at as its shows whether recipes that take a long time to prepare, and have a large number of steps and ingredients effects overall rating of a dish. As such knowing this this would allow for people to make better use of their time and allow them to make the proper plans. The main columns from the dataset that I will be focusing on will be cooking time which is the length of time it takes to prepare a recipe, the number of ingredients in the recipe, the number of steps, and average rating of each dish. 

---

## Cleaning and EDA

The process of cleaning the data first started with getting the two separate datasets and merging them together into 1 dataframe. After megring them the next step was to replace all ratings of 0 with np.nan as 0 ment there were no ratings. After that the final steps of the data cleaning process was to split up the nutrition column into all of its separate parts and make those into new colunms.

<iframe src="assets/clean.html" width=800 height=800 frameBorder=0></iframe>

The next graph contains the  univariate analysis of the data as we look at the number of ingredients and how often they occur as they can be useful in comparing to the overall ratings. After looking at the graph we can see that most of the data is grouped around nine to ten steps with some major outliers.

<iframe src="assets/min.html" width=800 height=600 frameBorder=0></iframe>

The next graph contains the bivariate analysis of the data as we look at the number of steps and the number of minutes in a recipe and divide them in order to see how long each individual step in the recipe would take, allowing the chef to be be able to better plan their time for making each step of the recipe

<iframe src="assets/time_step.html" width=800 height=600 frameBorder=0></iframe>

The next table contains an interesting aggregate which is the number of ingredients and how that compares with the time, steps, and overall rating of each different recipe. 

<iframe src="assets/agg.html" width=800 height=800 frameBorder=0></iframe>


---

## Assessment of Missingness

The first thing to look at for the missingness is whether the data is NMAR. After looking the data I beleive that the ratings column in the dataset is not NMAR as there are over 2000 entries missing from it. This is beacuse the data is missing when it has no ratings and as such there may be a common correlation between the data and as such we can look it the other columns in greater depth to confirm whether the data is NMAR.

The first graph is for the missingness of rating when compared with the minutes column and the graph shows the distribution of the data.

<iframe src="assets/min_med.html" width=800 height=600 frameBorder=0></iframe>

The next graph shows the distribution for the missingness of rating when compared with the minutes column and shows the TVDs after preforming the test. From the resulting graph and p-val we are able to conclude that the data is NMAR when comparing these two columns as the p-val is less than the signifance level and we can reject the null of the data being MAR.

<iframe src="assets/dist_min.html" width=800 height=600 frameBorder=0></iframe>

This graph is for the missingness of rating when compared with the protien column and the graph shows the distribution of the data.

<iframe src="assets/protein.html" width=800 height=600 frameBorder=0></iframe>

The next graph shows the distribution for the missingness of rating when compared with the minutes column and shows the TVDs after preforming the test. From the resulting graph and p-val we are able to conclude that the data is MAR when comparing these two columns as the p-val is greater than the signifance level and we can accept the null of the data being MAR.

<iframe src="assets/file-name.html" width=800 height=600 frameBorder=0></iframe>


---

## Hypothesis Testing


The next thing is we will preform a hypothesis test in order to determine whether the number of steps truly has an effect on the average rating of a recipe. This will be done in order to answer the main question of this analysis. Does the number of steps effect the average rating of the recipes?Our null hypothsis is that the number of steps does not effect the average rating of the recipe, while our alternate hypothesis is that the number steps does effect the average rating of the recipe. The choice of test statistic will be the mean of the average ratings and the significance level will be .01.After running the test we would get a p-val of approxiamately 0.85 which would be greater than our significance value of 0.1. As such we would fail to reject null hypothesis and instead keep it, which is that the number of steps in a recipe would not effect its average rating. These choices hypothesis and test statistic were chosen as they are able to provide a good approimation for the data and allow for an easy analysis to see if the number if steps truly affects the average ratings of the outcome.

---
