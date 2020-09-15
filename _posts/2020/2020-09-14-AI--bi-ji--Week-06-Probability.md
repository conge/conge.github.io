---
layout: post
title: "AI-笔记-Week-06-Probability"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

**Week 6 Announcement**
> This week you should watch Lesson 5, [Probability](https://www.udacity.com/course/viewer#!/c-ud954/l-6385118556), and read Chapter 13 in AIMA (Russell & Norvig).
> Assignment 3:  Bayes Nets Sampling

# Challenge question
![chanllenge question](/assets/images/计算机科学/118382-bdd581be592c90cf.png)

![Solution](/assets/images/计算机科学/118382-b95fbf265cace06f.png)

![Solution](/assets/images/计算机科学/118382-1217680c12f9222b.png)
* P(x) is the probability of the disease without other constraints
* P(Y) is calculated P(Y| ~X)P(~X) + P(Y|X)P(X)

# Intro To Probability And Bayes Nets

![Bayes network example](/assets/images/计算机科学/118382-a6ffea0d2051c208.png)
* in the above example, we have random variables represents events which are connected by arrows to describe the relationships.
* the arrows indicate that the child nodes are influenced by their parents, and the influence can be a deterministic or probabilistic way.
* __Bayes net is a compact representation of the distribution of the large probability distribution of all the variables__.
* With Bayes net, we can *specify* the distribution, *observe* certain variables and *compute* probabilities of unobserved variables.

## outline

![outline](/assets/images/计算机科学/118382-a9ebad4988c97484.png)

# Probability / Coin Flip

![Probability](/assets/images/计算机科学/118382-f95b8610e7d2877c.png)

* P(T) = 1 - P(H)
* since H and T are __independent__ events, P(H,H,H) = P(H) x P(H) x P(H) 

![Probability 2](/assets/images/计算机科学/118382-d23e09d4a1b93018.png)
* remember, P(H) and P(T) are independent

## Summary

![Complementary and independence](/assets/images/计算机科学/118382-314c1b2bd63f4715.png)

# Dependence

![Dependence](/assets/images/计算机科学/118382-f8728423729c5b6b.png)

![](/assets/images/计算机科学/118382-4f484b1880b69f47.png)

# quiz: Weather


![quiz](/assets/images/计算机科学/118382-062107c02e5afa59.png)
* complementary rule applies for the first 2 quiz questions.

![quiz](/assets/images/计算机科学/118382-8db3032fff45cb3a.png)
* dependence rule applies to the calculation of P(D2 = Sunny) and P(D3 = Sunny)
* P(D2 = Sunny) = P(D2 = Sunny | D1 = Sunny) x P(D1 = Sunny) + P(D2 = Sunny | D1 = Rainy) x P(D1 = Rainy) 
* Simillarly, * P(D3 = Sunny) = P(D3 = Sunny | D2 = Sunny) x P(D2 = Sunny) + P(D3 = Sunny | D2 = Rainy) x P(D2 = Rainy) 

## Quiz: Cancer

![joint probability](/assets/images/计算机科学/118382-ec2a14fcb5e1abf4.png)

* joint probability of a and b is P(a, b) = P(a) x P(b)

![](/assets/images/计算机科学/118382-3049aa872c2cfa90.png)

* P(C | +) = P( +,C) /(P(+,C) + P(-,C))
* this is the Bayes rule!

# Bayes Rule
![Bayes Rule](/assets/images/计算机科学/118382-da772d3644cb4754.png)
* Prior
* Posterior
* Likelihood
* Marginal likelihood (Total probability)

```
20171006 初稿
```
