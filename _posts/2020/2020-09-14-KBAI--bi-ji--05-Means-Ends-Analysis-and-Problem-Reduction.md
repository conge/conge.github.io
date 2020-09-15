---
layout: post
title: "KBAI-笔记-05-Means-Ends-Analysis-and-Problem-Reduction"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

# Preview
![](/assets/images/计算机科学/118382-fc27acbf1071556c.png)

* Means-Ends analysis and Problem reduction are very useful for well-defined problems. 
* Both are problem-solving methods.

![Means-Ends analysis and Problem Reduction are part of the fundamentals of KBAI](/assets/images/计算机科学/118382-012ae6b9a6024973.png)

## Exercise: The Block Problem

![](/assets/images/计算机科学/118382-6e8faed63fdf63bc.png)

![](/assets/images/计算机科学/118382-d8007843d89eb909.png)

The real question is, how can we design an AI agent to come up and accomplish the series of operations.

## State Space

![State Space](/assets/images/计算机科学/118382-9bb096a82b1bb342.png)

A state space contains an initial state, a goal state, and many other states. We need to figure the path from the initial state to the goal state.

![an example of state path](/assets/images/计算机科学/118382-a07a03d02b44b4bd.png)

## Differences in State Spaces

One way to find the path is at each state (current state), select an operation that will reduce the difference between the current state and the goal state (end). the application of the operator is the means. --> __means-ends analysis__.

![Paste_Image.png](/assets/images/计算机科学/118382-931489549f1f30d9.png)

![](/assets/images/计算机科学/118382-96dc4c5b3f4790bc.png)
* from initial, there are three possible states can be generated, the distance of the states to the goal can be calculated.
* with each step, the distance between current state and the goal state are decreasing.

## Process of Means-End Analysis in Summary

![](/assets/images/计算机科学/118382-b451e9b9a7fc1a36.png)

## Quiz 1 Block Problem I

![write all possible next states of the initial state](/assets/images/计算机科学/118382-bc5fb2e9312a1502.png)

![calculate distance between each state to the goal](/assets/images/计算机科学/118382-fff0073a10a3e577.png)

* so the AI agent need to choose the third option since Means-Ends analysis always seeks to reduce the distance.

![number of possible states?](/assets/images/计算机科学/118382-0a69ee264f574d0f.png)

* there is only one state can reduce distance, that's moving "A" onto "B". But I could not lead to the goal state due to the fact that we can only move one block from the top if they were stacked together.

![The states are all moving the state away from the goal](/assets/images/计算机科学/118382-3ae8ffae664bfc84.png)

* Means-Ends analysis could not always lead us close to the goal.
* But the method is still a powerful method to many questions

-----

## Problem Reduction

![Break hard problem into easy sub-problems](/assets/images/计算机科学/118382-01f45821a62f182f.png)

![The Block Problem: now the sub-goal is "C" over "D"](/assets/images/计算机科学/118382-02820243d5390402.png)

## exercise with the sub-goal
![a possible next states](/assets/images/计算机科学/118382-6b0b809cfa293b57.png)

![Distance to goal](/assets/images/计算机科学/118382-a03f57e56ef95856.png)

![operation sequence to get to the sub-goal](/assets/images/计算机科学/118382-88865268aded9f43.png)

![operation sequence to get to the goal](/assets/images/计算机科学/118382-a5a3828d5a62309c.png)

Once again, Problem reduction does not guarantee success.

## Means-Ends Analysis for Raven's Problem Matrix

![RMP v.s. Means-Ends Analysis](/assets/images/计算机科学/118382-ad80ef9aa5bef355.png)

* The transformation between images can be expressed as the sequence of operators. The same operators are then applied to the other images.
* the correspondence of objects can be identified by relationship described by semantic networks. In the upper images, diamond inside a circle, in the lower image, circle inside the triangle. the correspondence are "Circle -> triangle" and "diamond -> circle".
* from the __Problem Reduction__ point of view, the RPM problem is decomposed into three sub-goals: 1) extract operators from "A" to "B"; 2) apply the operators on "C" and come up with some candidates for "D"; and 3)  test the candidates and select the best option.
* There is also "generate and test" method in the process.
* SN can support all the three problem-solving methods.
* These are the "weak" methods because the coupling of the method with the knowledge representation is weak.

![recap](/assets/images/计算机科学/118382-9617c5f22d04abe5.png)

The methods introduced today are closely related to lecture 12 logic and lecture 13 planning.

```
2017-01-23 first draft
```
