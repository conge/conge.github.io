---
layout: post
title: "KBAI 笔记 13 Planning"
date: "2019-01-01 08:37:13"
categories: 计算机科学
excerpt: "Course Preview Block Problem Revisited 前情提要：之前用来解决这个问题的方法是？ Painting a C..."
auth: conge
---
* content
{:toc}

## Course Preview
![Preview](/assets/images/计算机科学/118382-28c5a00f7f18451f.png)

![preview](/assets/images/计算机科学/118382-adff275c50e2d93b.png)

## Block Problem Revisited

![](/assets/images/计算机科学/118382-b518486365012760.png)

前情提要：之前用来解决这个问题的方法是？

## Painting a Ceiling

![Paint ceiling problem](/assets/images/计算机科学/118382-1cdd509d2d5404e8.png)

* the problem that the robot is facing is to paint the ceiling and the ladder.
* human will quickly figure out s/he should paint the ceiling witht he help of the ladder and then paint the ladder.

## Represent the Painting a ceiling problem.

![Representation of the goal state](/assets/images/计算机科学/118382-405ae247998bb827.png)

## States

![States](/assets/images/计算机科学/118382-392e2c1d5a3c1ed0.png)

* initial state 
* intermediate state. Note, there is no description of the ladder, so there should be no ladder mentioned in the logic.

## Operators

![Operators](/assets/images/计算机科学/118382-982f4a4d75023cf6.png)

* the operator will be carried out if and only if the precondition exists.

![Exercise](/assets/images/计算机科学/118382-ee9a7ad111c0774a.png)
* the not Dry state is interesting .

## Planning and state spaces:

![Planning](/assets/images/计算机科学/118382-9da88a1412ddc391.png)

* in each state, different operators can generate many possible states and the state space could explode very quickly.
* How to do operator selection?
* how to figure out the route (with the guidance of the goal state)
* control knowledge from the goal state.
* Since operator selection can be affected by goal setting, and the operator selection actually control the state selection.
* Operator selection is very much like action selection

![](/assets/images/计算机科学/118382-08560a099eec9afc.png)

* a plan is like states with operators.
