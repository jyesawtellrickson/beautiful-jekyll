---
layout: post
title: Home Depot Product-Search Relevance
tags: [kaggle, data-science, nlp, nltk, home-depot]
---

Having never worked much on NLP, this was a good chance to improve my skills. The competition was basically about predicting product-search relevance, that is, working out if a given product is what the user wants to see for a given search term. For example, if I search “1/2'’ screw” the best results would be (you guessed it) a 1/2 inch screw, but what brand? Is it steel or wood? Do I also want to see screwdrivers? Do I care about 1/2 inch nails? This is a very tricky topic when you get into the details.

## Data
The training set for this competition was created by human validators. For each pairing, at least three human raters evaluated the result. This is interesting, as it introduces quite a bit of uncertainty from the start. For example, there may be some pairs where the three raters all gave different answers based on their own opinion. This makes training difficult and we have to make sure our model is flexible enough to take this into account.

## Data Preparation
We start by combining the data together from the different sources. There is a lot of interesting stuff from the attributes of the products but it will be difficult to process, so I decided to leave it out in model, but it could definitely be used to improve the overall result.

The first step to make the data more usable is to stem the words. Stemming takes a word and replaces it with its stem, e.g. stemming => stem, happy => happi. We do this so that we can match words which have similar meaning but may be represented differently, e.g. happiness and happy have the same stem. The Porter Stemmer was chosen over the Snowball Stemmer for its greater execution speed and similar results.

While we stem, we also remove any unwanted characters and numbers to make associations easier. Measurement units like volts or centimeters shouldn’t be used to match otherwise a “30 centimeter ruler” could match with a “3 centimeter nail”. At this stage, we also correct for various common spelling mistakes found in the dataset through exploration. The model could be improved by performing a sophisticated spellcheck.

## Feature Generation
To judge the product-search relevance we generate numerous features; primarily:
- length: are the query and product name of a similar length?
- query matching: can we find any words in both terms?
- brand matching: is the brand found in both the query and product?
These features are expanded upon in depth by utilising the full set of product information. Ratios between certain variables are calculated where they could add value.

## Prediction
The prediction is done through a Random Forest Regressor which is essentially an estimator that fits multiple classifying decision trees on subsets of the training data. Before making the prediction, the term frequency–inverse document frequency is calculated using the TfidfVectorizer in sklearn and a data pipeline. Finally, a 10 x 20 grid search is performed to optimise the model parameters.
