# How long does it take to cook a recipe?

by Akash Juwadi (ajuwadi@ucsd.edu) temp

---

## Framing the Problem

The goal of this analysis is to answer the main question of how long it takes to cook a recipe. In order to preform this analysis we must first start by cleaning the data. The data cleaning process is the same the process presented in project three and the link to the exploratory data analysis can be found [here](https://akashjuwadi123.github.io/dsc80final/). The prediction problem of this datatset is how it takes for a recipe to cook. In order to order to figure this out we willl split the recipes into two groups with those having a cooking time of less than 40 minutes being considered short and those with a cooking time of 40 minutes or more being considered short. As such we would be using s classifirer or more specifally a binary classifier for this problem. The variable we will be preditdting will be wether or note the recipe has a long or short cooking time and the analysis metric for the model will be accuracy as it can be quickly compared in ordered to determine the efficacy of the model. 

---

## Baseline Model

The first thing we do in order to determine whether the cooking time of the input is long or short we must first start by creating a baseline model for the data. This is first done by taking in the data from three dirsfferent columns and placing it into the train_test_split in order to create data that has a useable output. This first uses the "n_steps" and "n_ingredients" data and compares it with the "is long" to determine if the data fits. Both of the columns used are quantative columns and they do not need  any enocdings as they are already in a useable form to maiputlate. As such we will use a KNeighborsClassifier in order to simply to a binary output of True or False as our precition function. After running the classifier we seem to get an accuracy of around 60% which is okay,but not very good as its till can be imporved further 


---

## Final Model

The first thing we do in order to improve our model is by adding two new transformed columns to it. The columns that I choose to assess were the calories and the rating columns. I choose to add these columns as they seemed to have a connection and could provide addditional insight into how long it would take for a recipe to be produced, as cooking having a higher rating could mean cooking for less time or a meal with more coalories could take longer to prepare. However in roder to better work with them the data first had to be transformed to be more workable. This was done by passing calories through a normalizer to make the data easier to work with as well as rating through an imputer in order to better show the spread of each rating overall. In order to decide what hyperparameters to use I decided to use a grid search Cv in order to fit the data to determine the best possible vals to use for my calcuation. After running this it was then I choose to use those two variables for my final model. Overall my final model is a large step up compared to the previous base model as the accuracy as gone by by around 28% showing that we are able to predict whether or not a recipe takes a lot of time.


---

## Fairness Analysis


The next thing is we will preform a hypothesis test in order to determine whether the number of steps truly has an effect on the average rating of a recipe. This will be done in order to answer the main question of this analysis. Does the number of steps effect the average rating of the recipes?Our null hypothsis is that the number of steps does not effect the average rating of the recipe, while our alternate hypothesis is that the number steps does effect the average rating of the recipe. The choice of test statistic will be the mean of the average ratings and the significance level will be .01.After running the test we would get a p-val of approxiamately 0.85 which would be greater than our significance value of 0.1. As such we would fail to reject null hypothesis and instead keep it, which is that the number of steps in a recipe would not effect its average rating. These choices hypothesis and test statistic were chosen as they are able to provide a good approimation for the data and allow for an easy analysis to see if the number if steps truly affects the average ratings of the outcome.

---
