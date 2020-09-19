---
layout: post
title: "KBAI 笔记 03 Semantic Networks"
date: "2019-01-01 08:34:11"
categories: 计算机科学
excerpt: "Representation has two things The Knowledgevocabulary The Content that g..."
auth: conge
---
* content
{:toc}

![Preview](/assets/images/计算机科学/118382-de746f8caa8f00e6.png)


![Knowledge representation](/assets/images/计算机科学/118382-3e6dc7463b22d1d9.png)

Representation has two things
* The Knowledge
  * vocabulary
* The Content that goes into the presentation
AI Has many representations and each has its own affordance and constraint.

## Introduction to Semantic Networks

![Example:  Find Knowledge representations for each figure](/assets/images/计算机科学/118382-1b43306bd77ee49a.png)

![Semantic Network of A and B](/assets/images/计算机科学/118382-826436223c60c740.png)
* A: label objects in A as nodes x, y and z and describe the relationship between these objects with links.
* B: Do the same to B, label objects and the relationship
* between A and B: actions taken were described with the dash line.

![Another example](/assets/images/计算机科学/118382-daf9597bdae3a093.png)

![Excersice](/assets/images/计算机科学/118382-4a4a33f3e1d95a90.png)

* Key: use only the existing vocabulary

![Excersie](/assets/images/计算机科学/118382-1f6452b10a93a0ab.png)

* the relationship of objects between C and 5 is not the same

![Structure of Semantic Networks](/assets/images/计算机科学/118382-bfc3853a7e22fc91.png)

## Characteristics of Good Representations

![goo representations](/assets/images/计算机科学/118382-e1892cefaa15ed0c.png)

![is food label a good representation?](/assets/images/计算机科学/118382-6c5f40a93ca905cc.png)

## Guards and Prisoners problem

![Guards and Prisoners problem](/assets/images/计算机科学/118382-595506f5e748fd76.png)

![Solving the Guards and Prisoners problem](/assets/images/计算机科学/118382-61f2b6c7fc3e339a.png)

* need to find out the legal and productive way of moving prisoners and guards from the left to the right side.

![Solving the Guards and Prisoners Problem](/assets/images/计算机科学/118382-cbe72c7f7ba866f5.png)

* the above moves were all legal, but two of them were not productive because they appeared in the previous steps.
* the power of semantic network representation is that it makes all the constraints of the states explicit and allows the problem be solved in a systematical way 

![Solution of the Guard and Prisoner Problem](/assets/images/计算机科学/118382-ebfcf51fd931dfd1.png)

* Please note that the state of the boat is also part of the system so that step 2 and 5 are not the same.

## Represent & Reason for Analogy Problems

Back to the original question,

![Example:  Find Knowledge representations for each figure](/assets/images/计算机科学/118382-1b43306bd77ee49a.png)

![5 is not the correct answer](/assets/images/计算机科学/118382-52f62bcd44551ad7.png)

we know that 5 is not the correct answer because the semantic representation of A->B does not match C->5. 

Now let's try C -> 2.

![Is 5 the correct answer?](/assets/images/计算机科学/118382-530e246812e1e278.png)

* we choose 5 as the best answer because the semantic network representation of C -> 5 matches the exactly that of A -> B. What if we don't find a 100% match?

## Exercise: How do we choose a match?

![exercise](/assets/images/计算机科学/118382-a6a3645e7dd5c6a2.png)

* 5 is the answer: inner object disappear
* 3 can also be an answer: outer object disappear and inner object expand.
* Why most of the people will choose 5 instead of 3? 

## Choosing Matches by Weights

![apply weights on ](/assets/images/计算机科学/118382-02e005c6ab91dfa3.png)

![exercise of weights: which on is the answer?](/assets/images/计算机科学/118382-93f0927823498728.png)

* 2 and 4 can both be an answer. However, C -> 2 is reflection which weights 4 points and C -> 4 is rotations which worth 3 points. In this case, 2 is the best answer because it has better weight

## Connection

![](/assets/images/计算机科学/118382-407f5400a3e9a6ae.png)

* To solve the problem, we need to save the representation of A -> B into the memory, also calculate the representation of C to all the options.
* The correspondent problem: one object in A corresponds to which object in B?
* In KBAI, the emphasis is on the relationships between object, not the features of an object (another weighting problem.

## Assignment 1

![](/assets/images/计算机科学/118382-9e60134e6fcc79ab.png)

The Cognitive Connection

How semantic networks connected to human cognition?
1. Semantic networks are kind of knowledge representation which can be used to represent knowledge and problems, thus can be used to solve the problem. The human mind can also represent knowledge and problem, and solve problems.
2.  Semantic networks can expand, like human memory. initial input could activate certain nodes, expand to related nodes on the semantic networks, and form a pathway. [John wants to become rich. He got a gun]

````
20170121 first draft
```
