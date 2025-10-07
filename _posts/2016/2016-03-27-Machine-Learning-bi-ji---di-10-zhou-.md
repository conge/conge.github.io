---
layout: post
title: "Machine Learning笔记 第10周"
date: "2016-03-27 23:27:45"
categories: 计算机科学
excerpt: "第十周根本没时间上课，只能利用第11周的春假补全。 This week: going over Feature Transformation t..."
auth: conge
---
* content
{:toc}

第十周根本没时间上课，只能利用第11周的春假补全。

This week: going over Feature Transformation this week, and starting on Information Theory.

![Defination of Feature Ransformation](/assets/images/计算机科学/118382-5203ad0fff64c169.png)
* Feature selection is a subset of feature transformation
* Transformation operator is linear combinations of original features

## Why do Feature Transformation

![Example of words](/assets/images/计算机科学/118382-302ead862e35ce2b.png)

* XOR, Kernel methods, Neural networks already do FT.
* __ad hoc Information Retrieval Problem__: finding documents within
a corpus that are relevant to an information need specified using a query. (Query is unknown)
* Problems of Information Retrieval:
  * Polysemy: e.g. a word have multiple meanings; cause false positive problem
  * Synonymy: e.g. a meaning can be expressed by multiple words. can cause false negatives problems.

## PCA


[This paper ](http://www.cs.princeton.edu/picasso/mats/PCA-Tutorial-Intuition_jp.pdf)does a fantastic job building the intuition and implementation behind PCA

An *eigenproblem* is a computational problem that can be solved by finding the eigenvalues and/or eigenvectors of a matrix. In PCA, we are analyzing the covariance matrix (see the paper for details)

![PCA](/assets/images/计算机科学/118382-81eb2ea72b9d0253.png)
PCA Features
- maximize variance
- mutually orthogonal (every components are perpendicular to each other)
- Global algorithm: the resulted components have a global constraint which is that they must be orthogonal
- it gives best reconstruction

- EigenValue monotonically not increasing and 0 eigenvalue = ignorable (irrelevant, maybe not useful).

- It's well studied and fast to run.
- it's like a classification. and using a filtering method to select dimensions to use. 
- PCA is about finding

## ICA

ICA has also been applied to the information retrieval problem, in [a paper](http://www.cc.gatech.edu/~isbell/papers/isbell-ica-nips-1999.pdf) written by Charles himself

![ICA](/assets/images/计算机科学/118382-7c249ef746608986.png)

![](/assets/images/计算机科学/118382-7d4d4f528cba175f.png)

- find components that are statistically independent from each other using mutual information.
- Designed to solve the blind source separation problem.
- Model: given observables, find hidden variables.

![quize 1: defining features for PAC and ICA](/assets/images/计算机科学/118382-1cdec1677aa3a6cc.png)

![More PCA vs ICA](/assets/images/计算机科学/118382-dfd7190bb9198258.png)

* ICA is more suitable for BSS problems and is directional.
* Eg, 
  * PCA on faces will separate image based on brightness and average faces. ICA will get features such as nose, mouth etc, which are basic components of a face.

## Alternatives:

![RCA](/assets/images/计算机科学/118382-5b604c9fdfad5424.png)

Random components Analysis: generates random directions 
- Can project to smaller dimensions (m << n)but in practice often have more dimensions than PCA.
- Can project to higher dimensions (m > n)
- It works and works very fast.

![LDA](/assets/images/计算机科学/118382-4cb09d5cf333a79e.png)

* Linear Discriminant analysis: find a projection that discriminates based on the label

## wrap up

![Wrap up](/assets/images/计算机科学/118382-fc64778d86882031.png)

[This excellent paper ](http://computation.llnl.gov/casc/sapphire/pubs/148494.pdf)is a great resource for the Feature Transformation methods from this course, and beyond



```
2016-03-17 初稿
2016-03-26 补完
```
