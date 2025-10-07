---
layout: post
title: "ML4T笔记 | 03-04 Ensemble learners, bagging and boosting"
date: "2019-01-29 01:29:29"
categories: 计算机科学
auth: conge
tags: Machine_Learning Trading ML4T OMSCS
---
* content
{:toc}

# 01 - Overview

![](/assets/images/计算机科学/118382-3d6dcba62635e0c0.png)

* 1988, Michael Kearns and Leslie Valiant: __Can a set of weak learners be combined to create a single, strong learner?__

* 2006, Netflix: $1 million prize for a machine learning algorithm that could do 10% better than their own algorithm at predicting movies people like.

* 2009, The winning algorithm: a combination of several algorithm, or an __ensemble learners__.

> Time: 00:00:42





# 02 - Ensemble learners

![ ](/assets/images/计算机科学/118382-e9e870d6b14c0d7a.png)

__Purpose: Creating an ensemble of learners to make existing learners  perform better__

* assembling together several different algorithms or several different models to create an ensemble learner.
* Process: plug our data into several learners (KNN, linear regression, decision tree, etc..) and we learn several models, then query our models with an X and it get a Ys. Then get the means of the  Ys as output.
* If doing classification mean of Ys does not work but we can have each of these Ys vote.
* then test this overall ensemble learner using test data that we set aside.

__Why ensembles?__

* ensembles often have lower error than any individual method by themselves.
* Ensemble learners offer less overfitting.

__Now why is that?__

* each learner has bias: e.g. with linear regression our bias is that the data is linear.
* when you put different algorithms together, you tend to reduce the biases because they're fighting against each other's bias


> Time: 00:02:51

# 03 - quiz: How to build an ensemble

![ ](/assets/images/计算机科学/118382-8451eeeea40a4707.png)

__Given a KNN learner and a linear aggression learner, how could you go about building an ensemble?__

pick the best answer.

Solution: D

A, Train several parameterized polynomials of differing degree. could work but it's not the best answer.

B, Train several KNN models using different subsets of data. Same as above, could work but not the best.

C, Train several KNN models with randomized Y values: Wrong.

D, Combine A and B into a super ensemble. [Yes, that is the best answer.]

E, combine B and C.

> Time: 00:01:01

# 04 - Bootstrap aggregating bagging

![ ](/assets/images/计算机科学/118382-888409571a99baef.png)

__bootstrap aggregating or bagging__: using the same learning algorithm but train each learner on a different set of the data.

* invented by Bremen in the late '80s, early '90s.

* create _m_ number of subsets of the data from the origina data (with N members) ramdomly with replacement. each subset has a size of N'.

	* Select with replacement means at each selection, we choose from all the N cases of the data.(we might choose the same data point again)

* _N_ is the number of training instances in our original data. _N'_ prime is the number of instances that we put in each bag, and _m_ is the number of bags.
* N' < N and usually N' = 60% * N (rule of thumb).

* use the _m_ collections of data to train a different model and get _m_ different models.
* Ensamble the models: query each model with the same x and collect all of their outputs and take their mean


> Time: 00:02:59

# 05 - Overfitting

![ ](/assets/images/计算机科学/118382-cb59e54c2b7cb54c.png)

__Which of these two models do you think is more likely to overfit?__

A single 1 nearest neighbor model trained on all the data or an ensemble of 10 1 nearest neighbor learners, where each one is trained on 60% of the data.

__Solution__: the ensemble's going to be less likely to over fit.

> Time: 00:00:10

# 06 - Bagging example

![ ](/assets/images/计算机科学/118382-0a1204729a957bf4.png)

Take 1NN for example, ensemble of two 1NN leaner gives more smooth results than the two models along

![ ](/assets/images/计算机科学/118382-29ca1a7690f9a6bf.png)

Five 1NN ensemble can give much smoother result.

Anyways, the point here is that you can build an ensemble that is much more smooth than any of the individual learners by themselves.

> Time: 00:01:39

# 07 - Boosting

![ ](/assets/images/计算机科学/118382-bc641257076f72e4.png)

__Boosting is a fairly simple variation on bagging__  

* Boosting aims to improve the learners by focusing on areas where the system is not performing well.

__ADA boost__

* build our first bag of data in the usual way (random sampling with replacement) and train a model in a usual way.

* Take all the training data and use it to test the model and discover that some of the points that are not well predicted.

* build our the bag of data by randomly from our original data but this time, each instance is weighted according to the error. (The not well predicted data points have higher chance to be selected).

* With the data, build another model and combine with the first one so we get a ensemble.

* Now test the ensemble again with the training data and measure errors. Repeat the process of weighting the data points with error, do bagging again, build another model and add it the to ensemble. 

* And thus we build our next bag and our next model until _m_ number of bags.

__Difference between bagging and boosting__:

* bagging: creates bags in the same way: choosing data at random with replacement.

* Boosting: choosing subsequent bags with more data instances that had been modeled poorly in the overall system before.

> Time: 00:02:24

# 08 - quiz: Overfitation

![ ](/assets/images/计算机科学/118382-4014f98b7ae559cb.png)

All right, so I want you to think back over what we've been talking about, bagging and add a boost.

___Bagging and boosting: which is more likely to overfit as _m_ increases?__

The answer is Ada Boost.

* the reason is that Ada Boost is trying hard to match outliers and it's striving to fit, and subsequently it may be susceptible to over fitting.

> Time: 00:00:22

# 09 - Summary

![ ](/assets/images/计算机科学/118382-ad790b9e8f05a33d.png)

* bagging and boosting are just methods for taking existing learners and wrapping them in this meta algorithm that converts your existing learner into an ensemble.

* An ensemble can be treated as one algorithm thus can use the same API we have been using to call an individual learner.

* The resulting learner is also likely to lower error and reduced overfitage.

* boosting and bagging are not new algorithms in and of themselves.


> Time: 00:01:02

> Total Time: 00:14:27

```
2019-01-29 初稿
```
