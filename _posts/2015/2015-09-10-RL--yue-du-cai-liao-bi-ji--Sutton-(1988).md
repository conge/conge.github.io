---
layout: post
title: "RL 阅读材料笔记 Sutton (1988)"
date: "2015-09-10 00:54:37"
categories: 计算机科学
excerpt: "1. Intro The learning to predict problem:  using past experience with an..."
auth: conge
---
* content
{:toc}

## 1. Intro

The **learning to predict** problem:  using past experience with an incompletely known system to predict its future behavior.  Important advantage: training examples can be taken directly from the temporal sequence of ordinary sensory input: no special supervisor or teacher is required.

Temporal-difference (TD) methods are driven by the error or difference between temporally successive predictions; with them, learning occurs whenever there is a change in prediction over time.

TD methods are both more *accurate* and *easier* to compute ( more incremental).

## 2. Temporal difference and supervised learning approaches to prediction.

**Supervised Learning**: given input-output pairs, the learner learns the system so it can give output if presented with an input. It ignores the sequential structure of the problem.

### 2.1 Single-step vs multi-step learning

* In **single-step prediction problems**, all information about the correctness
of each prediction is revealed at once. 
* In **multi-step prediction problems,** correctness is not revealed until more than one step after the prediction is made, but partial information relevant to its correctness is revealed at each step.

In real life, prediction are often based on information coming in as a temporal stream other than getting all the observation-outcome pairs all at the same time. the **multi-step** model is more in line with real life.

### 2.2 Computational issue

TD procedure is incremental and requires less computation power. 


```
2015-09-08 初稿
```
