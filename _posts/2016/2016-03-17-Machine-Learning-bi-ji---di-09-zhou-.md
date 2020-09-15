---
layout: post
title: "Machine Learning笔记 第09周"
date: "2016-03-17 13:31:54"
categories: 计算机科学
excerpt: "The aim of Feature selection can be find the knowledge in data and reduc..."
auth: conge
---
* content
{:toc}

![Reason for Feature selection](/assets/images/计算机科学/118382-0025b730f21b8bc5.png)
* The aim of Feature selection can be find the knowledge in data and reduce dimentionality of data.
  * with less features, it's easier to interpret data and get insight with data
  * the amount of data needed for solving ML problems grows exponentially as the number of features grows. So it's better to reduce the number of features.

![Quiz 1: How hard is the feature selection problem?](/assets/images/计算机科学/118382-56ae0fe2f33262cb.png)
* It is NP-hard and it is exponential.

## Filtering and Wrapping

![Filtering and Wrapping](/assets/images/计算机科学/118382-ff4531b86d7c2a71.png)
* Filtering is forward flow, there is no feedback from learning to the searching algorithm
* Wrapping has the searching algorithm inside with the learning algorithm and allows feedback from learning to the search algorithm.

![Filtering example](/assets/images/计算机科学/118382-62375ec95a44847f.png)
* Filtering
  * Pros: fast
  * Cons: 1. slow for isolated features; 2 ignores the learning problem
* Wrapping
  * Pros: 1. takes into account of model bias; 2. takes into account of learning
  * cons: very slow.
* example of filtering: use DT to select important features for the learning algorithms (e.g. kNN).

![How to do filtering and wrapping](/assets/images/计算机科学/118382-5455964f407d26a4.png)

For filtering Criteria: 
* Information gain
* variation, entropy
* independent/non-redundant

How to do Wrapping:
* hill climbing
* randomized optimization
* Forward search: find the best feature first. then in the rest feature, find one and combine with the first selected feature which give the best the score and keep it; then find the one which get the best score when combined with the selected……
* backward search: remove one, for the rest of combinations, keep the one does the best, repeat... until the score change too much?

![Quiz2: using filtering, choose the features to get zero training error](/assets/images/计算机科学/118382-0f474435b2d483a8.png)
* For DT, it's easy. when a == 0, then label is -; when a == 1, then split on b, and when b == 0, label is -; when b == 1, label is +. This is a AND B.
* For the perceptron (w<sup>T</sup>x > 0), it is not that easy to see the results. With a and b, the problem is not solvable. adding c with weight of -1, the problem can be solved. Although c does not offer any information, it is still useful in this case.

![Relevance](/assets/images/计算机科学/118382-6009f57c5f0e788c.png)
* B.O.C:Bayes optimal classifier. Relevance only concerns B.O.C.
* Strongly relevant: removing x degrades B.O.C, then x is strongly relevent
* weakly relevant: when x is not strongly relevent and exits subset of features that addig x to it improves B.O.C
* irrelevant: NOT( strongly or weakly relevant)

![Usefulness](/assets/images/计算机科学/118382-56bb7e0a60dc8efd.png)

![Wrap up](/assets/images/计算机科学/118382-5f9a3a4eb343f910.png)

```
2016-03-16
```
