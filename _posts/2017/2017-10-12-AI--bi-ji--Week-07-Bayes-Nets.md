---
layout: post
title: "AI 笔记 Week 07 Bayes Nets"
date: "2017-10-12 02:24:19"
categories: 计算机科学
excerpt: "Week 07 This week you should watch Lesson 6, Bayes Nets, and read Chapte..."
auth: conge
---
* content
{:toc}

**Week 07**

> This week you should watch Lesson 6, [Bayes Nets](https://classroom.udacity.com/courses/ud954/lessons/6381509770/concepts/64119686570923), and read Chapter 14 in AIMA (Russell & Norvig).
 > 
> Assignment 3:  Bayes Nets Sampling
Due: October 10 at 11:59PM UTC-12 ([Anywhere on Earth](https://www.timeanddate.com/time/zones/aoe) time)

# Challenge Question

![Graduation and job offer](/assets/images/计算机科学/118382-acc3dc26ae2db0b5.png)

* given the Bayes net, what is the probability of P(O2|o1), that is the probability of the students get an offer from company  2 when s/he got an offer from company 1.

![Answer](/assets/images/计算机科学/118382-a0add7bc6201bfc7.png)

# a simple Bayes net

![bayes net quiz](/assets/images/计算机科学/118382-4e2de29fca94b896.png)
* How many parameters (probabilities) are needed to specify the Bayes network above? (answer is 3)

# Computing Bayes Rule

![normalizing pseudo probablility](/assets/images/计算机科学/118382-e59aa7e780774276.png)
* the Bayes net can be calculated without knowing P(B) which is hard to calculate at first place.
* Since we know P(A|B) + P(-A|B) = 1, we can use the pseudo probability method. We only calculate the numerator of the Bayse rule and normalize the result with a normalization factor.

## Two Test Cancer example

![](/assets/images/计算机科学/118382-d435df9e41c311a3.png)
* note here `P(C|+,+) =P(c, +,+)/[P(c,+,+) + P(-c,+,+)] `

![](/assets/images/计算机科学/118382-4e882b8d32bbc817.png)
* simillary,  `P(C|+,-) =P(c, +,-)/[P(c,+,-) + P(-c,+,-)] `

# conditional independence

![](/assets/images/计算机科学/118382-11c8617a9e0ac4fc.png)
* When C is known, T1 and T2 are independent. 
* what if we don't know C?

![](/assets/images/计算机科学/118382-996ac0d34fea806d.png)
* the answer is that not knowing C, T1 and T2 might not be independent.

![Quiz on Conditional independece](/assets/images/计算机科学/118382-6f492632aa91cecc.png)

* the hard part for me is to come up with __P(+<sub>2</sub>|+<sub>1</sub>)=P(+<sub>2</sub>|+<sub>1</sub>,C)P(c|+<sub>1</sub>) + P(+<sub>2</sub>|+<sub>1</sub>,-C)P(-C|+<sub>1</sub>)__
* _the calculation of P(C|+<sub>1</sub>) is covered in the lecture of Week 06._  __P(C|+<sub>1</sub>) = P(+<sub>1</sub>|C)P(C)/P(+<sub>1</sub>)__

## the relationship between absolute and conditional independence

![quiz](/assets/images/计算机科学/118382-c0a009151185eed1.png)

## Independence

![](/assets/images/计算机科学/118382-fb959c8e1d80a707.png)
* S and R (Sunny and Raise) are not related in the Bayes Network

![](/assets/images/计算机科学/118382-f1ecc80bcbf18c19.png)

* still the first part of the Bayes rule, I did not get
* the point here that the lecture is trying to make is that P(R|S) = P(R) since R and S are independent
* this is called __Away effect__

![quiz: calculate P(R|H)](/assets/images/计算机科学/118382-81fa0b547b1ec844.png)
* apply Bayes rule so that P(R|H) = P(H|R)*P(R)/P(H), P(H) is known
* calculate P(H) is the key here
* P(H|R) is easy, the steps are similar to the calculation of P(H)

![](/assets/images/计算机科学/118382-c3d7beec572d0a85.png)
* Similar to the P(R|S,H)

## Conditional Dependence

![Conditional Dependence](/assets/images/计算机科学/118382-d33d611211d3cf6d.png)
* we know that R and S are independent, but adding the information about H, it created a dependence between the two. E.g. being happy in a not-Sunny day increases the probability of raise.

![independence does not imply conditional independence](/assets/images/计算机科学/118382-53db00389d1219b7.png)

# general definition of Bayes Network

![Bayes Network requires fewer parameters to represent the probability distributions](/assets/images/计算机科学/118382-efd22bd3ca72d93e.png)

![quiz: Number of parameters needed](/assets/images/计算机科学/118382-9f7e43d8edcfc3f8.png)


![quiz: Number of parameters needed 2](/assets/images/计算机科学/118382-f13b66b2d857f21d.png)

![quiz: Value Of A Network 3](/assets/images/计算机科学/118382-0f71f6425a9931a3.png)
* the quizzes above showed the advantage of Bayes network v.s. unstructured networks. Bayes net is more concise.

# D Separation

![quiz:D Separation1](/assets/images/计算机科学/118382-4096b2dd25184b23.png)

* A and C are not independent because A can determine B and then determine A through B. But if B is known, then A becauses irrelevant.
* C and D is not independent because knowing D can infer the knowledge of A and then can influence C. But if A is known, then D can not inference A or C anymore.
* E and C are similar to C and D, they are independent if A, B, or D is known. if A, B, D is unknown, the C and E can be dependent.

![Quiz: D Separation2](/assets/images/计算机科学/118382-31c4a53909fa38d0.png)
* A matters in determine E so does B. Because Both A and B can influence C and C influence E. If C is known, A or B becomes irrelevant to E.
* A and B are independent but if C is known, we can use A to infer B or vice versa. they are then not independent anymore in the case that C is known. __This is the explain away effect__.

![D Separation Rules](/assets/images/计算机科学/118382-a9cb571005b7d8f8.png)
* Active means dependence of the nodes the unknown nodes.


![Quiz: D Separation 3](/assets/images/计算机科学/118382-6e05c9243ad600bf.png)
* notice that the third one is the application of the last rule in the previous slide.

---------

Now the application of Bayes Network:

# Probabilistic Inference

In the remaining part of this lesson, you will learn about probabilistic inference using Bayes Nets, i.e. how to answer questions that you are interested in, given certain inputs.


![Evidence, query and hidden nodes](/assets/images/计算机科学/118382-a9245bdccf19d0a8.png)
* With Bayes net, we can infer the probability distribution of some nodes given certain input.
* the input is called __evidence__, the output is called __Query__ and all the other nodes are called __Hidden nodes__.

![quiz: what is evidence, hidden and query when trying to solve P(B|M)?](/assets/images/计算机科学/118382-761e53f99c102423.png)

Enumeration

![](/assets/images/计算机科学/118382-9165521874239af7.png)

![Enumerate f(+e, +a)](/assets/images/计算机科学/118382-b7eab1d643c42c8d.png)

The calculation becomes reading from the Bayes net table and summarize them. But when the number of nodes becomes larger, this method requires a lot of calculation.

![Technique 1: pulling out terms that won't change with the loop variable](/assets/images/计算机科学/118382-a788890895ac5bd1.png)

![Technique 2: maximize independence](/assets/images/计算机科学/118382-2823431e7b6af6b3.png)
* e.g., if A is unknown, J and M are dependent.

## Bayes net in Causal direction

![Causal direction](/assets/images/计算机科学/118382-de69707271c8191e.png)



## Value elimination

Value elimination is a two-step operation: eliminate some fac
Joining factors and elimination

![](/assets/images/计算机科学/118382-d8a72b410de459a0.png)

![example of joining factors](/assets/images/计算机科学/118382-815cb2b480932c38.png)


![Example of elimination](/assets/images/计算机科学/118382-3e3bd7d6e091af34.png)


![Value elimination 2](/assets/images/计算机科学/118382-11f67dd8d9c7a92d.png)


![Value elimination 3](/assets/images/计算机科学/118382-c231266edf7af2d6.png)

## Approximate Inference

![approximate by sampling](/assets/images/计算机科学/118382-2a8a82d90724b5d3.png)


![Quiz: sampling, give R and S, what's the rows to consider to sample from, and where W should be positive?](/assets/images/计算机科学/118382-bebc4e2032821a8d.png)
* the sampling procedure will get the probability distribution to be close to the truth if repeated infinitely. This is called __consistent__.
* the sampling method can be used to generate the complete joint probability or individual probability
* to generate conditional probability, we can still use the sampling method, but need to cross-off the irrelevant joint probabilities. E.g, if we need to know P(R|C), then all the cases when c is not true will need to be thrown away. this is called __rejection sampling__.

## Rejection Sampling
* the problem of rejection sampling is that when the condition we care about is at a lower odds, the rejection sampling will reject a lot of samples which is a waste of resources. We can solve the problem by fixing the conditional variable, this is called __likelihood weighting__.

![Likelyhood weighting](/assets/images/计算机科学/118382-9d2188c9cc94b3ff.png)

* the problem of likelihood weighting, is that it is __inconsistent__. In another word, sampling with likelihood weighting cannot get true probability distribution unless it is properly weighted.

## Likelihood Weighting

![quiz: Likelihood Weighting](/assets/images/计算机科学/118382-edeb647075dbd78f.png)
* Specify the weight for w+ and +s when constraining them when sampling. In the quiz, we need to constrain the +2 with the probability of 0.99 since we already know its parents are +S(due to constraining) and +R(due to sampling).

* With likelihood weighting, we can make rejection sampling consistent
* but it does not solve all the problems, for example

![Likelihood weighting fails helping P(C|+s, +r](/assets/images/计算机科学/118382-201d5748381e4d9c.png)
* Likelihood weighting with sampling will get good values for WetGrass because S and R determine W.
* However, the sampling of C will not look at S or R, so the process will still generate C with values that do not go well with R and S, in this case, a lot of rejections will happen.

## Gibbs Sampling

![image.png](/assets/images/计算机科学/118382-cd5ac4b99e2da7a1.png)
* Markov Chain Monte Carlo (MCMC): 1) sample by randomly sampling all nodes at the first time, then, 2) randomly identify one node from the first sample, and resample the node while keeping all others consistent with the first one to generate the second sample, and 3) repeat 2) with the second sample to generate the third sample, and so on...
* MCMC is consistent.

## Monty Hall Problem

![remember, the host will never reveal the door that the player selected in the second step, so be revealing one door, we did not know more about the door selected, but the door not selected got updated by the information provided by the revealing door](/assets/images/计算机科学/118382-78b2c4dba0470e0d.png)

* Even Monty Hall himself does not understand the Monty Hall problem.
