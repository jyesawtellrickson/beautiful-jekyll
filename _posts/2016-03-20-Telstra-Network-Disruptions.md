---
layout: post
title: Telstra Network Disruptions
tags: [kaggle, telstra, data-science, python]
---

In this competition we were challenged to predict the severity of a network failure on Telstra’s network. There is a good set of established (and obvious) features so this competition was a chance to work on some interesting feature generation techniques that I hadn’t tried before. Overall it was an interesting competition with some good discussion. You can check it out [here](https://www.kaggle.com/c/telstra-recruiting-network) and see my submissions [here](https://github.com/jyesawtellrickson/kaggle/Telstra/).

# Data Preparation
There were many different sources of data for this competition including severity, resource types and event numberings. Most of this data isn’t in a neat numeric format so the data was first processed with map functions.

We also have many numerical categorical variables which should be converted to categories to avoid any confusion within the model. To do this, we use pandas' [get_dummies()](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.get_dummies.html) which appends columns to the Dataframe for each variable. We do this for resource, severity type and events which have less than 50 options each however we cannot do this for locations as we have 929 in  the training set alone (we can check this with DataFrame.location.unique().size). This would create far too many columns, so we must use another method. The log_feature variables have a similar problem with multiple entries per id with the added complexity of volume / event. As such, we can create a few extra features such as the number of unique entries, total volume of entries, the spread of the volume (i.e. even volume for each type or one predominant) and the ranking of entries. We lose some data here by dropping the rows which didn’t feature in the top 3. <!-- how many is this?-->
<!--- LEAKED DATE at end of file -->

# Feature Generation
This is where things get interesting. We’ve got the basic features sorted but we need to find the unicorns to improve our score. I tried a lot of different things here to get the right features. Firstly, the shotgun approach of generating different combinations of the currently available variables through the basic operators (+, -, /, \*). We can then use PCA / dimensional reduction to improve our results and performance.

# Feature Selection
Now we iterate over a lot of the features and choose which are the best based on the training set.

# Prediction 
To predict we utilise an xgboost model which is the most popular approach at this point in time and is giving the best results in similar competitions.

# Results
The initial public score for the model, based off a xgboost model of the basic data is 0.602. Using xgb.cv to choose the best result improves this score to 0.560. The most effective feature in improving the score was log_feat * volume which brought us closer to 0.518. With the additional efforts and features it was brought down to 0.509 which was the lowest in the end.
So all our efforts in generating / selecting new features brought us from 0.560 -> 0.509 which is an improvement of almost 10% which isn’t bad. In the end, this placed me in 200th position (21%).
