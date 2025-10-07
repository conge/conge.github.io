---
layout: post
title: "KBAI 笔记 10 Incremental Concept Learning"
date: "2019-01-01 08:36:27"
categories: 计算机科学
excerpt: "Preview Exercise: Identifying a Foo I background knowledge is important ..."
auth: conge
---
* content
{:toc}

# Preview  

![Preview](/assets/images/计算机科学/118382-65656a6586fbe0ab.png)

## Exercise: Identifying a Foo I

![quiz](/assets/images/计算机科学/118382-c6b0ef43e6a72553.png)
* background knowledge is important to make the judgement whether the fourth graph shows the concept of foo.

## Exercise: Identifying a Foo II
![quiz 2](/assets/images/计算机科学/118382-d72d1e73f60443bc.png)

## Exercise: Identifying a Foo III

![quiz 2](/assets/images/计算机科学/118382-7f500a01735da568.png)

* yes or no answer could be correct. yes is a generalization and no is a specification
* learning is incremental (learn from one example at a time)
* examples are labeled.
* examples come from specific order
* differ from K space reasoning
* the number of examples is small.
* what to learn is going to be a hard question( over generalization or over specification)

# Incremental Concept Learning

![Process of Incermental concept learning](/assets/images/计算机科学/118382-32534e6aa163bb18.png)

Example of over generalization and over specification using children as example. what is a dog.

## Variabilization

![](/assets/images/计算机科学/118382-29b1005d0907d75f.png)

AI representation of an Arch.

## Generalization to Ignore Features


![New Arch example](/assets/images/计算机科学/118382-710821d2281ff9e2.png)

![Drop-link heuristic](/assets/images/计算机科学/118382-43918abb4fd7022a.png)

## Specialization to Require Features

![](/assets/images/计算机科学/118382-881c3f6bc34b11e6.png)

![require-link heuristic](/assets/images/计算机科学/118382-69fc874f1e2ab7da.png)

## Specialization to Exclude Features

![](/assets/images/计算机科学/118382-e6e3363913e75f85.png)

!["forbid-link" heuristic](/assets/images/计算机科学/118382-b2cf829e63b00c61.png)

## Generalization to Abstract Features


![](/assets/images/计算机科学/118382-592af1a5fb59245e.png)

!["enlarge" heuristic](/assets/images/计算机科学/118382-37ce9b0f0d24551b.png)

## Generalization with Background Knowledge

!["clime tree" heuristic](/assets/images/计算机科学/118382-5fef482a99bd30b6.png)

## An Alternative Visualization

![](/assets/images/计算机科学/118382-dd0ea14fdde94aee.png)

## Heuristics for Concept Learning

![Summary of Heuristics](/assets/images/计算机科学/118382-8c8a617bc8b074d8.png)

## Exercise: Re-Identifying a Foo I

![](/assets/images/计算机科学/118382-965c2681528884ff.png)

## Exercise: Re-Identifying Foo II

![](/assets/images/计算机科学/118382-ea2175d07c6c3a42.png)

## Exercise: Re-Identifying Foo III

![](/assets/images/计算机科学/118382-5066ae8e1dc00d1b.png)

![](/assets/images/计算机科学/118382-a2dff30922207214.png)

The concept of block can be brick or Cylinder.

![backgroup knowledge](/assets/images/计算机科学/118382-cfbc9aeae4cdaae4.png)

## Exercise: Re-Identifying Foo VI

![Do nothing](/assets/images/计算机科学/118382-8d48c7ca8b8c58f4.png)
* the example is not a concept and the current COncept is already exclusive. we don't need to do anything or learn anything.

## Final Concept of a Foo

![](/assets/images/计算机科学/118382-51630a0c25d0765c.png)

* when there is limited number of examples, Agent has to use its background knowledge and use all the examples to incrementally learn the concept.

# Assignment 

![](/assets/images/计算机科学/118382-f38ee891da6f859f.png)

# Wrap Up

# The Cognitive Connection
In real life, cognitive agent like humans are usually given one example after another. Incremental concept learning is the closed way of how human learn new concept. 

