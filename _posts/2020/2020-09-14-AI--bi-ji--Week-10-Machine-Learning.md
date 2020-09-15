---
layout: post
title: "AI-笔记-Week-10-Machine-Learning"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

> This week you should finish Lesson 7, [Machine Learning](https://classroom.udacity.com/courses/ud954/lessons/6808838653/concepts/68238486020923), and read Chapter 18.6-11 & 20.3 in Russell & Norvig.  
> 
> Assignment 4: Decision Trees
Due: October 29 at 11:59PM UTC-12 ([Anywhere on Earth](https://www.timeanddate.com/time/zones/aoe) time)

----

# Boosting

![Boosting](/assets/images/计算机科学/118382-1cf950d49d860a58.png)

![Boosting example](/assets/images/计算机科学/118382-76402a83fa9ff53b.png)

* ??? I don't know how to calculate e2 and e3???
![Boosting example](/assets/images/计算机科学/118382-15c72c2c79dc720f.png)

![Boosting quiz](/assets/images/计算机科学/118382-751fb27084ddc88e.png)

# Neural nets

![Neura nets](/assets/images/计算机科学/118382-1f77dea19b967b08.png)

![](/assets/images/计算机科学/118382-33032819783ace0f.png)

![simple equation can do generalized computation](/assets/images/计算机科学/118382-cd5d7e080306645f.png)

Quiz: Neural Nets Quiz

![quiz](/assets/images/计算机科学/118382-b4cd983b27acdf2b.png)

> Fill in the truth table for NOR and find weights such that:
> 
> a = { true if w0 + i1 w1 + i2 w2 > 0, else false }
>
> Truth table
> Enter 1 for True, and 0 (or leave blank) for False in each cell.
> All combinations of i1 and i2 must be specified.
Weights
> Each weight must be a number between 0.0 and 1.0, accurate to one or two decimal places.
> w1 and w2 are the input weights corresponding to i1 and i2 respectively.
> w0 is the bias weight.
> Activation function
> Choose the simplest activation function that can be used to capture this relationship.

## Multilayer Nets

![](/assets/images/计算机科学/118382-4978caa59322eacd.png)
* neural nets only makes sense when activation functions are nonlinear. If they are linear, the who network can be reduced to a linear function thus lose the power of the network.

## Perceptron Learning

![](/assets/images/计算机科学/118382-3c7e5bb310a9bd90.png)

* single layer perceptron can only generate linear boundaries.

![Comparison between decision tree and perceptron](/assets/images/计算机科学/118382-30cafc63f48ee0dc.png)

* the performance of perceptrons is not always better than other methods (e.g. decision tree). it can be improved, however, by adding more layers

## Multilayer Perceptrons
![Multilayer Perceptrons](/assets/images/计算机科学/118382-93fd7e4d1a15ccb9.png)

## Back-Propagation
![](/assets/images/计算机科学/118382-9a657e93c29e5809.png)
* Back-Propagation is the way to calculate neural nets.
* the harder a problem is, the longer time for the algorithm to converge. Below are examples how fast an algorithm converges.

![](/assets/images/计算机科学/118382-04c79c803d59ba5a.png)

![](/assets/images/计算机科学/118382-9a4a424b66e9f396.png)

## Deep Learning

* neural nets have limitations: need computation power, need more training set but still can be limited on the types of problem it suits.

# Unsupervised Learning

* or classification. The unsupervised learning algorithm classify data into sub-classes and figure out each which class each case fits in.

## k-Means and EM

![k-Means](/assets/images/计算机科学/118382-18d196851e68b7c4.png)

* K-means start with randomly initiating the means and generate decision boundaries to separate the data set. the means of the separated data are then recalculated. Then new decision try will be generated to classify the data again. repeat the process until there is no change in the classification anymore.
* this is the expectation-maximization procedure
* for data that is hard to converge or avoid local maxima, random restart technique can be used.

## EM and Mixture of Gaussians

![](/assets/images/计算机科学/118382-6432ed046bc7e4e7.png)

* instead of means, we can use k-Gaussians with the EM procedure to do classification. 

> __Readings on EM and Mixture Models__
> * AIMA: Chapter 20.3
> * PRML: [Chapter 9.0-9.2 Mixture Models and EM](https://s3.amazonaws.com/content.udacity-data.com/courses/ud954/notes/Machine-Learning/Mixture-Models-and-EM_Bishop.pdf)
> * *PRML = [Pattern Recognition and Machine Learning](http://research.microsoft.com/en-us/um/people/cmbishop/prml/), Christopher Bishop
> __Research articles__
> * [Using GPS to Learn Significant Locations and Predict Movement Across Multiple Users](http://www-static.cc.gatech.edu/~thad/p/journal/using-gps-to-learn-significant-locations.pdf), Daniel Ashbrook and Thad Starner

```
20171101 初稿
```
