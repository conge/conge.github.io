---
layout: post
title: "KBAI 笔记 09 Case-based reasoning"
date: "2017-02-20 08:17:16"
categories: 计算机科学
excerpt: "preview Recording Cases to Case-Based reasoning exercise The block is no..."
auth: conge
---
* content
{:toc}

# preview

![](/assets/images/计算机科学/118382-c8c51baa1cc54304.png)

# Recording Cases to Case-Based reasoning

## exercise
![What the color of the new block will be?](/assets/images/计算机科学/118382-0607b5bdb89d0fae.png)

The block is not in the world so "learning by recording cases" does not work. To accomplish the job, one must used to existing cases to learn some rules to reason the solution.

## the process of case-based reasoning

![Process](/assets/images/计算机科学/118382-e8685f6452c99184.png)

* retrieval: retrieve solutions from memory
* adaption: adapt solution to solve the current problem
* evaluation: evaluate the adapted solution
* storage: save the solution to the case memory for use later

## Assumptions of Case-Based Reasoning

![](/assets/images/计算机科学/118382-64055186f7b97ec7.png)

* the second assumption is not always valid (touch screen example and shoe lace example)

# Case Adaptation

![](/assets/images/计算机科学/118382-3152eb5dd8608d66.png)

The adaption is usually very small tweak. e.g. cooking, programming.
There are three ways to do case adaption

## Case Adaptation by Model of the World

![](/assets/images/计算机科学/118382-b69748eccd3ad680.png)

* Examples: python API for programming.

* use models to adapt, evaluate, and store cases.

## Case Adaptation by Recursive

![](/assets/images/计算机科学/118382-c53feffa5f17bdb2.png)

case was solved by dividing the problem into parts, and solve the sub-problems to get  partial solution and then enter the unsolved part back the the agent to solve the rest of the question recursive.

* reading:  Vattam, S. S., Helms, M. E., & Goel, A. K. (2008). Compound analogical design: interaction between problem decomposition and analogical transfer in biologically inspired design. In Design Computing and Cognition'08 (pp. 377-396). Springer Netherlands.

## Case Adaptation by Rules

use heuristic rules to solve problems.

# Case evaluation

evaluate the solutions from the program adaption
* Test the design with data
* evaluate the design by other designers, etc...

# Case Storage

![](/assets/images/计算机科学/118382-f6035e74bf046acc.png)

## Case Storage by Index

![index structor helping with case storage](/assets/images/计算机科学/118382-3d3110dcb5e37afc.png)

## example

![Paste_Image.png](/assets/images/计算机科学/118382-919fc0e9b5f97040.png)

* When the dimension of the problem increase, the indexing method could become inefficient.

## Case Storage by Discrimination

![Discrimination Tree](/assets/images/计算机科学/118382-49e43645fe408962.png)

discriminate the cases by cutting points and build a tree from it.

## exercise

![exercise](/assets/images/计算机科学/118382-3845f2446fba9fb1.png)

Where do Y belong to on the discrimination tree? By following the tree from the root, Y is with A. The the question becomes: how to discriminate Y from A.


![How to differentiate between A and E? ](/assets/images/计算机科学/118382-5a755ee5c6e5dfa8.png)

# Case Retrieval Revisited

![](/assets/images/计算机科学/118382-1dda11a3c93ff807.png)


![Exercise](/assets/images/计算机科学/118382-be33bc1e0b330a72.png)

# Advanced Case-Based Reasoning

![](/assets/images/计算机科学/118382-34d413996fdf2cfa.png)

* if the evaluation result is bad: try redo adaption or retrieval again.
* storing failure cases might also useful to avoid failure ( learn the failure is learning). But storing failure must be very strategic.

# Assignment
![assignment](/assets/images/计算机科学/118382-67a7b722422e4550.png)

# Wrap Up

![](/assets/images/计算机科学/118382-33f99d423d69c934.png)

# The Cognitive Connection

Reasoning: tweak the solution and apply it
Learning: evaluate the solution and store the ones that solve the new problem
memory: memory enables the storage and retrieval of the cases.
