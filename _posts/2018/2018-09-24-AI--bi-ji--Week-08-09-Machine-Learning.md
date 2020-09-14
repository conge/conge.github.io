---
layout: post
title: "AI 笔记 Week 08-09 Machine Learning"
date: "2018-09-24 14:23:00"
categories: 计算机科学
excerpt: "This week:  watch the first section of Lesson 7, Machine Learning (throu..."
auth: conge
---
* content
{:toc}

> This week:  watch the first section of Lesson 7, [Machine Learning](https://www.udacity.com/course/viewer#!/c-ud954/l-6808838653) (through Random Forests), and read Chapters 18.1-5, 18.8, 20.1-20.2 in AIMA (Russell & Norvig).

# Challenge Question

Find the most efficient decision tree given the fact table

![quiz 1: challenge question](/assets/images/计算机科学/118382-f66bcfa8945d9652.png)

# k-Nearest Neighbors

![](/assets/images/计算机科学/118382-545bc6eec9dec0c2.png)

# Cross Validation

![Cross validation](/assets/images/计算机科学/118382-22f440bea9570ab6.png)

* Training set and test set.
Cross-validation often uses a randomly chosen independent sample as test sets.
* Model selection: tweaking parameters of the model and report the one which gives the best prediction ( be this might lead to the over-fitting problem.
* Leave-one-out cross-validation (LOOCV) strategy: when a sample is small, a test set might not be feasible, in this case, use the leave-one-out strategy in which we train the model with all cases in a data set except one random case. repeat the process multiple times with one case leave out. 

![quiz: CV](/assets/images/计算机科学/118382-4ac3ff3348fc22c0.png)

> AIMA: Chapter 18.8
> Further study: [Sebastian Thrun’s and Peter Norvig’s lecture on kNN](https://classroom.udacity.com/courses/cs271/lessons/48703335/concepts/487480760923)
>
> ![Quiz: 1NN](/assets/images/计算机科学/118382-cd89a6674a21fca9.png)
> * which data point is positive given the known data points?
>
> ![quiz: kNN](/assets/images/计算机科学/118382-a22e09074b8ceff9.png)
> * what is the value of the data points using kNN when k = 1, 3, 5, 7, 9?
>
> # K As Smoothing Parameter
>
> ![](/assets/images/计算机科学/118382-9af621a5260f12dd.png)
>
> ![](/assets/images/计算机科学/118382-25cf00a684fbb485.png)
>
> * as K increases, the separation boundary becomes smoother, but there are more outliers which will be misclassified. The model will also  be come more complex
>
> ![](/assets/images/计算机科学/118382-385ad692aa287f96.png)

# The Gaussian Distribution

![](/assets/images/计算机科学/118382-9a6776f1816a1397.png)
* standard deviation determines the width of the distribution
* 68% with 1 SD, 95% within 2 SD, 99.7% with 3 SD.

## Central Limit Theorem

* Samples of random variables, the mean of the samples will form a Gaussian Distribution. And the mean of the distribution will be expected to be the population mean

## Grasshoppers Vs Katydids
A pattern recognition example of Gaussian distribution

![](/assets/images/计算机科学/118382-77a5875af6a04c9e.png)

![](/assets/images/计算机科学/118382-953ad3c1850f983c.png)
* the distribution can be formed by projecting data on to the Y-axis.
* once a distribution is formed, it is very easy to get the probability of what a case if from by fit it in the distribution.

## Quiz: Gaussian Distribution

Take the **Insect data**: Antennae length [[xlsx](https://s3.amazonaws.com/content.udacity-data.com/courses/ud954/data/insects/antennae-length.xlsx) | [csv](https://s3.amazonaws.com/content.udacity-data.com/courses/ud954/data/insects/antennae-length.csv)] and calculate the probability of the length "7" indicate a Katydid or Grasshopper
![Quiz: Gaussian Distribution](/assets/images/计算机科学/118382-e991c4ebac5c0e62.png)

## Decision Boundaries

![Decision Boundaries with Gaussian is easy](/assets/images/计算机科学/118382-2b5072180cfe8c81.png)
* the boundary is where the distributions cross.


![Quiz on recoginition](/assets/images/计算机科学/118382-2b3b424287e67418.png)
* "No" because the recognizer might classify everything as negative and get 90% cases correctly.

## Decision Boundaries in Higher Dimensions

* The Decision boundaries are also in higher dimensions for higher dimensional distribution

![](/assets/images/计算机科学/118382-f46091f45179126c.png)

![](/assets/images/计算机科学/118382-ae9ba8c522350ada.png)

## Error
![](/assets/images/计算机科学/118382-a6a3dfb48239b29d.png)

* we can make the decision boundary which changes the error rate of the classification. In real life, the decision should be made to increase acceptable errors (classify mosquitoes don't care certain disease as the ones who carry the disease) to avoid unacceptable errors (misclassify bad as good).

# Bayes Classifier

![](/assets/images/计算机科学/118382-45861ef3136218e0.png)

![quiz: Bayes rule by counting](/assets/images/计算机科学/118382-e90b31540f367612.png)

* based on the table P(G|N ) = P(N|G) * P(G)/P(N) 
* using counting to get the probabilities. E.g. P(male), there are 3 males in 8 data points, then p(male) = 3/8, etc...
* N = Name = Drew here.
* P (male|Drew)= P(Drew|male) P(male) /P(Drew) = 1/3 * 3/8 / (3/8) = 0.33
* P (female|Drew)= P(Drew|female) P(female) /P(Drew) = 2/5 * 5/8 /(3/8) = 10/15 = 0.67

## Naive Bayes

* Independent assumption gives Naive Bayes.
* Naive Bayes can be represented as a tree structure of class pointing to features

![](/assets/images/计算机科学/118382-f64cc8ce0f17e4d8.png)

Naive Bayes net assumes independence between features: so P( height, hair length | sex) = P(height | sex) * P(hair length | sex), thus
* p(d|C<sub>j</sub>) = p(d<sub>1</sub>C<sub>j</sub>) * p(d<sub>2</sub>C<sub>j</sub>)  * ... * p(d<sub>m</sub>C<sub>j</sub>)
* here we assume Maximu Likelihood where everyone prior has the same probability of occurence.


![](/assets/images/计算机科学/118382-b5b19886f1fc389e.png)

![answer](/assets/images/计算机科学/118382-76e24dd2451626e8.png)

> __Readings for Bayesian Classifiers__
> * AIMA: Chapter 20.1-20.2   
>
> __Further resources__
> * [Keogh’s original slides](http://www.cs.ucr.edu/~eamonn/CE/Bayesian%20Classification%20withInsect_examples.pdf)
> * [Isbell’s and Littmann’s lecture](https://www.udacity.com/course/viewer#!/c-ud262/l-478818537/m-482228628)
> * [Thrun’s lecture](https://www.udacity.com/course/viewer#!/c-cs271/l-48703335/e-48704326/m-48687677)

## No Free Lunch
No one ML algorithm is good for all problems.

## Naive Bayes vs kNN

## using a mixture of Gaussians
![two Gaussian](/assets/images/计算机科学/118382-371d861a7029e93a.png)

* Two Gaussian can generate a more complex decision boundary, and more Gaussian can do more until it creates its own decision boundaries for each of the data points which is nearly the same as kNN.

* Kernel density estimation: use fewer Gaussians which would cause the decision boundary to be smooth, But still give a good continuous approximation of the shape 
* cross-validation can be used to find the good N of Gaussians.
* use a final test set to test for overfitting.

## Generalization

## Visualization

Visualize data to determine which algorithm might work.
* If most of the classes from balls of data without many concavities, then modeling it with Gaussians will probably work well.
* If there are situations where classes interpenetrate, but still have distinct boundaries, then k-nearest neighbors or one of the kernel methods will probably work.
* for high dimensional data we can also use methods like __decision trees__ and __boosting__ to help you understand which features are most important.

----

# Decision Tree

## Decision tree with discrete information

## Decision tree with continuous information

## Minimum Description Length

![Minimum Description Length](/assets/images/计算机科学/118382-b6a54752f160322c.png)

![](/assets/images/计算机科学/118382-c5b389dd8e710e6e.png)

* which attributes should we use first?
* Which question provides the most solution of the problem? then it should be on the top of the decision trees according to information theory.

## Entropy

![](/assets/images/计算机科学/118382-0b4f843382166265.png)
* p is the number of positive cases
* n is the number of negative cases
* B(_q_) = -(_qlog<sub>2</sub>q_ + (1 - _q_)_log<sub>2</sub>_(1 - _q_))

## Information Gain

![](/assets/images/计算机科学/118382-f5664cca4d475ec9.png)

![](/assets/images/计算机科学/118382-878a3365c095caef.png)
* Information Gain is a way to determine how to construct three

![image.png](/assets/images/计算机科学/118382-acf916c486bb897e.png)

* Please note that the attribute which is not important at the first iteration might become important in the new level.

![quiz](/assets/images/计算机科学/118382-487b9e72f9d7bac4.png)

* B(9/14) = 0.94
Gain(outlook) = 0.94 - [5/14 * B(3/5)  + 4/14 * B(4/4) + 5/14 * B(2/5)]
=0.94 - [5/14 * 0.97  + 5/14 * 0.97]
 
![quiz answer](/assets/images/计算机科学/118382-71333493eea70af0.png)

> Readings on Decision Trees   
> AIMA: Chapter 18.1-18.5

----

# Random Forest

![Random forest](/assets/images/计算机科学/118382-34098eb2341c1430.png)

* train several decision trees and let them vote for the answer
* Random sampling seems to be able to lower the chance of overfitting


> week 09 is the midterm week. No lectures
