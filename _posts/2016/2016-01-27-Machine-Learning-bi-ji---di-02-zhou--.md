---
layout: post
title: "Machine Learning笔记 第02周 "
date: "2016-01-27 04:02:41"
categories: 计算机科学
excerpt: "本学期学习Machine Learning。本课程在Udacity上有免费版本，并提供详细的笔记。本文的笔记是超级脱水版，目的是自用。 Week..."
auth: conge
---
* content
{:toc}

> 本学期学习Machine Learning。本课程在Udacity上有[免费版本](https://www.udacity.com/course/machine-learning--ud262)，并提供详细的笔记。本文的笔记是超级脱水版，目的是自用。

Week 02 tasks：
* Lectures:  Instance Based Learning, Ensemble B&B, and Kernel Methods & SVMS.
* Readings: Mitchel Chapter 8, Schapire's overview to Machine learning and Jiri Matas' slides on AdaBoost.

## SL4: Instance Based Learning

> * [Lesson 4 Notes](https://storage.googleapis.com/supplemental_media/udacityu/666010252/Lesson%204%20Notes.pdf)
> * [Instance Based Learning](https://storage.googleapis.com/supplemental_media/udacityu/666010252/Instance%20Based%20Learning.pdf)

![Instance Based Learning Before](/assets/images/计算机科学/118382-a731793f5383c519.png)

* in supervised learning, we learn a function from data and use the function to predict future data.

![Instance Based Learning Before](/assets/images/计算机科学/118382-b3d5d0d163b6c997.png)

* Now we keep everything in a database and f(x)=lookup(x). this database approach has pros (fast and simple) and cons (no generalizable and overfitting).

![ Cost of the House example](/assets/images/计算机科学/118382-c8cc81158090dfbe.png)

* classify unknow price houses by 
  * nearest neighbor
  * k nearest neighbors

![K-NN](/assets/images/计算机科学/118382-3b1126963f9b3dfa.png)

* in K-NN, there are a lot decisions can be made to get the result: e.g.  classification: by voting or weighted voting; regression: average or weighted average. 

![Quiz 1: compute my neighbors](/assets/images/计算机科学/118382-ee3c6f6036852ea5.png)

* the running time and space required for each algorithm.
* Sorted data points is more efficient in query.
* Lazy learning (push work to when it's needed) V.S. eager learning

![quiz 2: Domain K-nnowledge](/assets/images/计算机科学/118382-a1c2bc983929864d.png)

* Different distance function and K makes very different prediction of the query point q.

![K-NN Bias](/assets/images/计算机科学/118382-6cbf6c759643d79e.png)

* K-NN works well when data has 1) locality, 2) smoothness and 3) equality of features

![ Curse of Dimensionality](/assets/images/计算机科学/118382-d7d989991708fcd6.png)

* This is bad
* the curse is not just for KNN, it's for ML.

![Some Other Stuff](/assets/images/计算机科学/118382-a85eb0986cd51494.png)

* Picking d(), picking K, replacing average with local weighted regression.

![Wrap up](/assets/images/计算机科学/118382-cd89a2931b23cb02.png)

----

## SL5: Ensemble Learning Boosting

> * [Lesson 05 Notes](https://storage.googleapis.com/supplemental_media/udacityu/367378584/Lesson%205%20Notes.pdf)
> * [Intro to Boosting](https://storage.googleapis.com/supplemental_media/udacityu/367378584/Intro%20to%20Boosting.pdf)

![ Ensemble Learning Boosting](/assets/images/计算机科学/118382-c21363eddbae9c4e.png)

* example of spam email rules: but the rules are not definitive.

![Ensemble learning algrithm](/assets/images/计算机科学/118382-1ff2c1ba5fe204c4.png)

algorithm:
1. pick up rules from subset of training data and 
2. combine rules.

![Ensemble learning algrimth continue](/assets/images/计算机科学/118382-87b6f7da041b8a3c.png)

For each step of ensemble learning algorithm, there are multiple ways of doing things. 
* picking up dataset uniformly randomly and
* combine by average give us bagging. See examples below.

![Quize 1. Ensemble Learning Outputs](/assets/images/计算机科学/118382-6cbb2481a39cffd0.png)

Example 1:
- N points and learner is zeor order polynormial
- combining method: mean
- Subsets are N disjoint, each w/ one data point.

What's the ensemble output? A: average of N data points.

Now, another example:

![Ensemble learning example](/assets/images/计算机科学/118382-5037209e4ece089b.png)

* 3rd order polynomial (redline) on subset is better than 4th order polynomial on whole data on testing. It somehow removes overfitting.
* Bagging or bootstrapping:  take a random subset and combine by the mean

![Ensemble Boosting](/assets/images/计算机科学/118382-d8c65c78a34ca7d7.png)

New subsetting and combination method:
* Choose hard examples: hard relative to if we were to stop now, how well we do?
  * hard samples are samples which hypotheis do not match with the target function
* Use weighted average


![Quiz 2: Error](/assets/images/计算机科学/118382-b185ac9be2894ca3.png)

* subscript D stands for distribution. So h is the hypothesis and C is the true underlying concept.
* Olde definition: an error rate or an error percentage as the total number of mismatches over the total number of examples
* New Definition: error is the probability, given the underlying distribution, that I will disagree with the true concept on some particular instance X.
* Quiz 2: say we have 4 instance, we got 2 correct and 2 wrong, what's the error? A: 0.5, assuming each instance has the same possibility to be seen.

![Quiz 3: Error when instances have different possibility](/assets/images/计算机科学/118382-e1d65608db26dd46.png)

* What's the error rate using new definition? A: 0.1.

![Weak Learner](/assets/images/计算机科学/118382-1ef38c50638b7a1b.png)

* a weak learner is a learner that, no matter what the distribution is over your data, will do __better than chance__ when it tries to learn labels on that data. 

![Quiz4: Weak Learning](/assets/images/计算机科学/118382-496d1d83cb982d43.png)

* __Good D__: find distribution over the 4 different examples, such that a learning algorithm that has to choose between one of those hypotheses will in fact be able to find one that does better than chance (by having an expected error less than 1/2)

*  __evil D__: find a distribution such that if you have that distribution over the four examples, a learning algorithm that only looked at H1, H2 and H3 would not be able to return one of them that has an expected error less than 1/2.

![Quiz4: answer, and my answer above also passed the grader](/assets/images/计算机科学/118382-ad077ecf7a98e79a.png)

![Boosting in code](/assets/images/计算机科学/118382-d089133eaab68e9c.png)

* a training set made up of a bunch of x<sub>i</sub>, y<sub>i</sub> pairs. 
* loop at every time step _t_, from step 1, to some _T_
  * construct a distribution D<sub>t</sub>
  * Given that distribution, find a weak classifier to output hypothesis H<sub>t</sub> with some small error  ϵ<sub>t</sub>, and ϵ<sub>t</sub> can't be bigger than 1/2.
* eventually,  output some final hypothesis. H<sub>final</sub>.
*  the two really important things are left out: 
  1. where do we get this distribution and 
  2. where do we get this final hypothesis?

![Quiz, what will happen when D agrees](/assets/images/计算机科学/118382-67d74bc522b21d79.png)

* Important part 1: how to construct distributions
  * initial D(i) = 1/n. No special weights
  * for D<sub>t</sub>(i), use normalized (by Z<sub>t</sub>) distribution which is weighted by e to the alpha, Y, and h<sub>t</sub> .
* When y and h<sub>t</sub> disagree, the distribution will change. but whether the change is increase or decrease will depends on normalization factor and others.

![Final Hypothesis](/assets/images/计算机科学/118382-35e56c74acf96384.png)

* H<sub>final</sub> is defined  as a SGN function of the sum of all the weighted hypothesis.

![Boosting example](/assets/images/计算机科学/118382-1f57b629091134e1.png)

* in three steps, boosting will solve the problem of separating red positive sign and green negative sign.
* Size of sign represents their weights.

![Quiz 6 answer](/assets/images/计算机科学/118382-fa921961e0f28097.png)

* by average the three hypothesis, we can get the correct Hypothesis here.

![Intuition of why boosting will converge to a good answer?](/assets/images/计算机科学/118382-9446c2cdbd51da5c.png)

I am lost here, and need to read the proof!


![Recap](/assets/images/计算机科学/118382-446cec807a6b6400.png)

In practice, Boosting might not have a overfitting problem (testing error goes high)




```
2016-01-24 SL4 完成
2016-21-25 SL5，初稿完成
```
