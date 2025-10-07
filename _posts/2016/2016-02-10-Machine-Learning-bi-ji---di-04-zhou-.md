---
layout: post
title: "Machine Learning笔记 第04周"
date: "2016-02-10 13:59:40"
categories: 计算机科学
excerpt: "Week 04 tasks： Lectures:  VC Dimensions and Bayesian Learning. Reading: ..."
auth: conge
---
* content
{:toc}

Week 04 tasks：

* Lectures:  VC Dimensions and Bayesian Learning.
* Reading:  Mitchell Chapter 7 and Chapter 6.

----

## SL8: VC Dimensions

* [Lesson 08 Notes](https://storage.googleapis.com/supplemental_media/udacityu/417758568/Lesson%208%20Notes.pdf)
* [VC Dimensions Review](https://storage.googleapis.com/supplemental_media/udacityu/417758568/VC%20Dimensions%20Review.pdf)

![Quiz 1: Which Hypothesis Spaces Are Infinite](/assets/images/计算机科学/118382-1dce9bfce0118179.png)

* m>= 1/ε( ln|H|+ln(1/𝛿) ). Here the sample size _m_ is dependent on the size of hypothesis |H|, the error _ε_ and the failure parameter_ 𝛿_. What happens if |H| is infinite?
* quiz 1: Which Hypothesis Spaces Are Infinite

![ Maybe It Is Not So Bad](/assets/images/计算机科学/118382-16af59ab5565e63a.png)

* In the example above, although the hypothesis space is infinite (syntactic), we can still explore the space efficiently because a lot of hypothesis are not that meaningfully different (semantic). 

![What Does VC Stand For](/assets/images/计算机科学/118382-b41b58c51fe96c88.png)

* VC dimension: what is the largest set of inputs that the hypothesis class can shatter.
* Vapnic-Chervonenkis

![Quiz 2: internal training](/assets/images/计算机科学/118382-7ebcf827b204ebd9.png)
* not sure how to answer this question. need to rewatch.

![Quiz 3: Linear Separators](/assets/images/计算机科学/118382-97e2e9eca094b42e.png)

* Here VC = 3. 

![The ring](/assets/images/计算机科学/118382-6630ff78a04a84b5.png)
*  the vc dimension is going to end up being d plus 1 because the number of parameters needed to represent a d dimensional hyperplane is __ d plus 1__.

![quiz 4: polygons](/assets/images/计算机科学/118382-ac5b3e3da2ca55a0.png)

* if the hypothesis is that points inside some convex polygon, then the VC = infinite.


![Sample size with infinate hypothesis space](/assets/images/计算机科学/118382-0cd6eccc48d49904.png)

![VC of finite H](/assets/images/计算机科学/118382-1c31b43c8c9e407d.png)

![recap lesson 8](/assets/images/计算机科学/118382-45a29c1496d24f21.png)

-----

## Bayesian Learning

* [Lesson 09 Notes](https://storage.googleapis.com/supplemental_media/udacityu/454308909/Lesson%209%20Notes.pdf)
* [Bayesian Learning Extension](https://storage.googleapis.com/supplemental_media/udacityu/454308909/Bayesian%20Learning%20Extension.pdf)


![Bayesian Learning](/assets/images/计算机科学/118382-4f8709b87ce50261.png)

* the best hypothesis is the most probable hypothesis given data and domain knowledge.
* argmax<sub>h∈ H</sub> Pr(h|D)

Bayes Rule

![Bayes Rule](/assets/images/计算机科学/118382-1868eda627d94cb9.png)
* Bayes Rule: Pr(h|D) = Pr(D|h)Pr(h)/Pr(D)
  * Pr(D) is the prior about data
  * Pr(h) is the prior of hypothesis, and it's the domain knowledge.
  * Pr(D|h) is the possibility of data given h, it is much easier than Pr(h|D) to compute.

![Quiz 1](/assets/images/计算机科学/118382-33a65d121026117a.png)

* comparing the probability of one having /not having spleentitis.

## Bayesian Learning

![Bayesian Learning](/assets/images/计算机科学/118382-7c5a04709e12c948.png)

* to find the largest Pr(D|h), we could drop P(D) for the bayes rule because it doesn't matter since our task is to find the best _h_. __MAP: maximum a posterior__.
* If we don't have a strong prior or we assume the prior is uniform for every _h_, we can drop Pr(h). ML: __maximulikelihoodod___
* the hard part is to look into every h
* Since H is often very large, this learning algorithm is not practical

##  Bayesian Learning in Action

![Bayesian Learning when the data has no noise](/assets/images/计算机科学/118382-c33d108f530ec7cf.png)
* given a bunch of data, your probability of a particular hypothesis being correct, or being the best one or the right one, is simply uniform over all of the hypotheses that are in the version space. That is, are consistent with the data that we see.

![Quiz 2:](/assets/images/计算机科学/118382-54cb514b8ab7b632.png)
* given <x,d> pairs, and d<sub>i</sub> =k \* x<sub>i</sub> which has a probability of Pr(1/2<sup>k</sup>), what is the probability of _D_ given _d_.

![Bayes learning given gausion error](/assets/images/计算机科学/118382-f28b37c3c6278e9f.png)

* given training data, figure out f(x) and with its error term. If the error can be modeled by Gaussian function, then 
* h<sub>ML</sub> can be simplified to minimizing a sum of squared error.

![Quiz 3](/assets/images/计算机科学/118382-3bf017b4832ed7c9.png)
* find best hypothesis from the three.
  * calculate and compare squared error.

![Quiz 4: small trees](/assets/images/计算机科学/118382-a31610986ba0308b.png)

* h<sub>MAP</sub> can be transformed to minimize the length of hypothesis (size of h) and the length of the D|h (which is misclassification error)
* there is a tradeoff between size of h and error. this is called minimum description length
* there is a unit problem: unit of error and size need to be figured out

##  Bayesian Classification

![Bayesian Classification](/assets/images/计算机科学/118382-798bc2122020fbc1.png)
* when we do the Classification, we will have each hypothesis to vote

![Recap](/assets/images/计算机科学/118382-9142b746f7847502.png)

* Bayes optimal classifier = weighted voting by h.

```
2016-02-08 SL8 完成
2016-02-08 凌晨，SL9 完成.第一稿发布

```
