---
layout: post
title: "KBAI 笔记 04 Generate and Test"
date: "2019-01-01 08:34:46"
categories: 计算机科学
excerpt: "Generate and Test Preview Optional reading: Winston Chapter 3, pp. 47-50..."
auth: conge
---
* content
{:toc}

# Generate and Test

## Preview
Optional reading: Winston Chapter 3, pp. 47-50

![Generate and Test is a method to solve problems](/assets/images/计算机科学/118382-68f7c0c2d5239fd6.png)

## Guards and Prisoners

KABI is a collection of three components: knowledge representations, problem-solving techniques, and architectures.

Generate and Test method has a generator to __generate__ all the possible next steps (a dumb generator) and a tester to __remove__ illegal solutions.

In the exercise below, list all the possible next steps a generator could come up.
![Exercise](/assets/images/计算机科学/118382-9e32047c7efeceb5.png)

Now, remember, the tester only removes illegal states, so which one/ones will be removed?

![](/assets/images/计算机科学/118382-46f5ca22a8373018.png)

## Dumb Generators, Dumb Testers

Dumb Generators, Dumb Testers can solve the problem but it is computationally expensive because it would not eliminate states that appeared before.

![Explosion](/assets/images/计算机科学/118382-32dc0c747f6a4513.png)

## Smart Testers

Smart Testers eliminate previously visited states and collate the path of problem-solving.

![smart testers](/assets/images/计算机科学/118382-ee5837001a91f0f1.png)

## Smart Generators

![](/assets/images/计算机科学/118382-6e1dd74dde96e781.png)

Smart Generators will not generate states that appeared previously.

When design an AI system, whether to make the generator smarter or tester smarter or balance the two is a practical question to ask.

## Discussion: Smart Generators and Testers

Then, for the dead-end paths, who should take the responsibility to terminate them, the generator or the tester? David said tester. Is he right?

![](/assets/images/计算机科学/118382-758adb5ae860ef37.png)

## examples of the intelligence question

![This problem is even more complicated](/assets/images/计算机科学/118382-a408f9b5af315313.png)

The transformation from C to the options are not discrete, so the space of the possibilities can become very large very quickly. So smarter generator and smart testers are critical.

Here is when the knowledge representation become helpful. 

* knowledge representation is a high-level abstraction of the problem and ignores a lot of low-level details.
* but knowledge representation alone could not solve the problem. it must coples with a problem-solving method

![](/assets/images/计算机科学/118382-94299efb2b04eaab.png)

## Generate & Test for Raven’s Problems II

![This problem is even more complicated](/assets/images/计算机科学/118382-a408f9b5af315313.png)

* The way humans solve the problem: learn a transformation rule for A -> B; apply the transformation to C, and get a possible solution, then compare the solution with the options provided. If there is no match, repeat by generating a new set of transformation rules, etc... until a match is found.

I The way knowledge representation + generate & test solve the problem: select an option to calculate semantic networks from C to the option, then compare the semantic networks with the semantic networks of A -> B. Do it repeatedly for all the options and then evaluate all the semantic networks and then select the one with the most possibility or weights.

## Wrap Up

![Paste_Image.png](/assets/images/计算机科学/118382-ff59ee5da85fafbb.png)

## The Cognitive Connection

Human beings uses generate and test all the time because we do not have the whole knowledge of the world and our computation ability is limited.

````
2017-01-21 first draft
```
