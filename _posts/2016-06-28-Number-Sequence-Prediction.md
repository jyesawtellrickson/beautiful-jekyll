---
layout: post
title: Number Sequence Prediction
tags: [kaggle, maths]
---

In this competition we were challenged to predict the next number in a number sequence taken from the On-Line Encyclopedia of Integer Sequences (OEIS). For example, in the classic sequence [1, 1, 2, 3, 5, 8, 13, ...] the model would be expected to predict 21 (I hope you got the same - Fibonacci's Sequence). However, unlike you, the computer has little training and lacks the elasticity when it comes to the various sequences which makes this problem a very difficult one.

## Data
The sequences are all taken directly from OEIS. One initial problem is that some sequences in the test set are identical. For example, if ask you what's next in the sequence [1, 2, ...] you might say 3 (linear) and your friend might say 4 (exponential). Both answers could be correct but because you don't have enough information it is very difficult to recognise the sequence. 

## Models
There is a huge variet of number sequences used in this competition, and they are described by many different functions. To approach this competition I thought the best approach would be to create generalised functions which the model could try to find. These models are outlined below. Another approach, would be to try feature generation across the sequences and use these features to estimate the result, e.g. most common number, highest number, negatives. A few people tried these with some sucess.

One issue with using typical fitting models that use least squares or similar is that they are not so relevant to number sequences. This is because we are applying a continuous and approximate method to the discrete and exact problem of integer prediction. This just won't work in most cases, especially when you have big numbers and the least squares is less likely to land you in the correct spot due to rounding (we can get away with it for smaller sequences). The issues is that least squares will minimise the distance between prediction and target, e.g. guessing 11 for 12 is better than 2 for 12 but in reality these are equally bad. I think the results could be significantly improved by using a different scoring function, though I'm not sure what this may be.

Another layer we could add to our model is processing multiple predictions. As it stands, the return from the prediction is a real number that is rounded to the nearest integer, but the amount of rounding required could be a telling feature. For example, I predict 12.5, I'm probably way off, I predict 12.02, I have a better chance. We could calculate the results of all the functions and choose the one with the least difference from an integer. This would allow us to apply multiple functions and possibly improve results.

### Linear
y = mx + c
A basic linear model can be used to guess the answer. For this, we're calculating the parameter m where x is the index and y is the sequence value. The prediction can the be found simply by multiplying m by the next indek. This should match all linear sequences correctly and has a decent chance at maching small, oscillating sequences

### Linear Multivariate
y = a + bx0 + cx1 + dx2 + ...
Instead of keeping the sequence as one  list of numbers, we can break it up into sets of smaller sequences and use these for training. By doing this, we can give the model a better chance to 'learn' the sequence as it trains across multiple sets. We feed in sets of numbers from the sequence, e.g. [1, 1, 2, 3], [1, 2, 3, 5], [2, 3, 5, 8] and then it learns the coefficients which best predict y. This model can accurately describe the Fibonacci sequence  (c = [0, 0, 1, 1]) as well as many more complex series.

## Results
I never submitted (for an unknown reason) but my model scores around 15% which puts me in the top 50% for the competition.
