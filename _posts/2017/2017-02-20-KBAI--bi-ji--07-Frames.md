---
layout: post
title: "KBAI 笔记 07 Frames"
date: "2017-02-20 06:58:18"
categories: 计算机科学
excerpt: "Preview Frames are the first step of commen sense reasoning Exercise: As..."
auth: conge
---
* content
{:toc}

## Preview
* Frames are the first step of commen sense reasoning 

![Preview](/assets/images/计算机科学/118382-eab2224bae3759f0.png)

![Preview](/assets/images/计算机科学/118382-968f8ea50ba5eb09.png)

## Exercise: Ashok Ate a Frog

![Excercise](/assets/images/计算机科学/118382-d3c2e1f98ef4e669.png)

From the statement, there is no mentioning of the questions on the left. But human beings can answer the questions with some common sense knowledge and reasoning.

## How do we make sense of a sentence?

![Semantic representation of the sentence](/assets/images/计算机科学/118382-0f5b66c8083f1fdc.png)

* Above is a semantic representation of the sentence "Ashok ate a frog". It can be represented by the action "Ate" with a list of attributes. The attributes are pairs of __slots__ and __fillers__. 
* Some slots have default value (e.g. the filler of the slot Object-alive is false, because once the object is eaten, it should be dead), or it can be extracted from the sentence (e.g., the subject of the action "ate" is Ashok, which is from the sentence. 
* __A frame is a knowledge structure__ with slots and fillers to fill the slots. Frame stores stereotypical situation.

![Exercise: Making sense of a sentence](/assets/images/计算机科学/118382-bda518e57f1e4b6e.png)

Reflection of the exercise:
* Frames are rigid, sometimes could not represent the new situation (e.g., now slot to put "dad" in the frame)
* Common sense is likely to be the default values of the  frames

## Complex Frame Systems


![complex Frames](/assets/images/计算机科学/118382-e5d8be047181fc2b.png)
* Frame can represent verb and nouns
* Frames can be connected so that some frames can be the filler of other frames.
* frames are used for sentence level of __understanding__ here. But with the two property above, Frames can be used to represent and understand group of sentences by connecting Frames together.

## Properties of Frames

![Inheritance](/assets/images/计算机科学/118382-0fcbef6b253d876e.png)
* The way that Class and instance works is very much like the objects in the object-oriented programming.

## Exercise: Interpeting a Frame System

![](/assets/images/计算机科学/118382-1278f3b81cf17f08.png)

## Frames and Semantic Nets

![Frame to represent Semantic Nets](/assets/images/计算机科学/118382-67fe94ad07cbd338.png)

![Exercise](/assets/images/计算机科学/118382-a6b815b0279690fd.png)

## Frames and Production Systems

![](/assets/images/计算机科学/118382-131761feb26f6bd4.png)

# Exercise: Frames & Complex Un

![Paste_Image.png](/assets/images/计算机科学/118382-963373aed64e116f.png)

## Assignment

![](/assets/images/计算机科学/118382-9606eda99a5f1ae1.png)

For this assignment, discuss how you'd use frames to represent Raven's Progressive Matrices. At a basic level, what are the slots and
llers associated with different Raven's problems? Where are these frames going to comefrom? Is the agent going to receive the problem
in terms of frames initially, or it going to generate these frames based on its own reasoning? Once it has these frames, what exactly are the reasoning methods it's going to use to solve the problem But what about a frame representing the problem, as a whole? What about a
frame representing individual shapes within g-ures? How would representing the problems at that dierent level of abstraction, help the agents solve the problem more easily. What are frames going to enable us to do, that we couldn't do otherwise?

## recap

![recap](/assets/images/计算机科学/118382-d9740eb9bc207e51.png)

##

Frames are structures of knowledge representation (molecules in stead of atoms).

Top down and bottom up reasoning?

Frames provide knowledge representation of stereotypes, which facilitate cognition efficiency ( by the use of default values).

```
20170214 first draft
```
