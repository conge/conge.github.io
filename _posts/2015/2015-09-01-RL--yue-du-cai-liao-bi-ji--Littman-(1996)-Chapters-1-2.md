---
layout: post
title: "RL 阅读材料笔记 Littman (1996) Chapters 1-2"
date: "2015-09-01 10:16:07"
categories: 计算机科学
excerpt: "Littman, 1996, chapter 1,2 Chapter 1: Introduction 1.1 Core concepts of ..."
auth: conge
---
* content
{:toc}

> Littman, 1996, chapter 1,2

# Chapter 1: Introduction

## 1.1 Core concepts of Sequential decision making

Purpose: producing policies that maximize a measure of long-term reward to an agent following it in a specific environment.

### Elements of Sequential decision making

* Agent: the system responsible for interacting with the world and making decisions.
* Environment: change from state to state (*s*) in response to the actions (*a*) of the agent according to a fixed set of rules (T). Environment can be stationary(<-main focus of the paper) or nonstationary (<-hard to model). Environment can have multiple agents.
* Reward: the purpose of agents' action is to maximize rewards. Reward is a defining property of models.
* Policies: Agent's prescription for actions. plan-> conditional plan -> universal plan or "stationary policy" -> stochastic policy. **Stationary policy** is the most important one in this paper.

![Elements of Sequential decision making](/assets/images/计算机科学/118382-88859cc624f06a91.png)

In the figure above, *s* is state, *a* is action, T is transition function which changes *s* given *a*. R is the reward function and *r* is the reward of the state. O is perception function (usually it is an identity function) and *z* is the agent's perception of the environment.

### Problem scenarios：

* **Planning**: the complete model of the environment is known and a planner takes the model and generate policy.
* **Reinforcement Learning (RL)**: the learner only knows the agent's perception of the world and action it can take. Environment is unknown. It's up to the agent to generate a policy and follow it.
* **Model based RL**: building a model with the limited information known to the agent, and then use a planning algorithm to generate a policy.
* **Simulated RL**: in this case, the model is known but the agent acts like it is not known and use RL algorithm to generate policy. It is used when the environment is too complicated. 
 
![Problem scenarios](/assets/images/计算机科学/118382-6ad9674f224346bd.png)

## 1.2 Formal Models

To simplify the problem, the properties of the environment model must follow the following conditions:

> finite state space; finite actions; sequential environment; accessible and inaccessible environment; Markovian environment (prediction can be made by environment's state); fixed environment; stochastic or deterministic transitions; synchronous environment ( environment won't change until the agent takes an action); with one or two agent.


![Markovian Models](/assets/images/计算机科学/118382-dc7bbf7e2929cc62.png)

## 1.3 evaluation criteria

**Evaluating Policies**: an objective function takes all the <s, a> sequences and their probabilities to generate value. The optimal sequence maximize the objective function. 1) for each <s, a> sequences, objective function replace each transition with a "goodness" value; 2) the values are truncated according to the finite horizon; 3) transition values were summarized for each sequence; 4) this sequence value are summarized to  get a policy value; 5) in multiagent environment, other agent can change transition value.

**Evaluating Planning algorithms**: 1) All criteria above; 2) whether an optimal policy can be reached; 3) algorithm efficiency.

** RL algorithms**: RL algorithms tries to achieve what planning can do without complete knowledge of the whole environment. If the algorithm can reach optimal policy (converge), then it's good.

![Paste_Image.png](/assets/images/计算机科学/118382-5cd6a2ed1c142795.png)

----

# Chapter 2: Markov Decision Process

![The problem to address is, given complete and corrent dynamics of environment find the best way to behave](/assets/images/计算机科学/118382-aa84fe211dde76e5.png)

Core concept of MDP below is extracted from [my notes](http://www.jianshu.com/p/881ab7e41adb) of the course lecture.

> ![MDP](/assets/images/计算机科学/118382-62523e167fc61b2a.png)

> **States**: set of tokens which describe every state that one could be in,  

> **Model/Transition Function**:  probability that you'll end up transition to s' given you are in state s and taking action a. This is 'physics' or rules of the world(not changeable) . 

> **Action**: A(s), things you can do in a given state, a function of state, rule you can play; or A, a set actions not depends regardless of state.

> **Reward**: scalar value that you get for being in a state. Usefulness of entering a state/and taking an action/and ending up into s' 

> **S, T, A and R define the problem**, policy is the solution,

> **Policy**: the solution, a function that takes up a state and tells an action that you'll take <s,a> while *a* is the correct action you want to take to maximize the reward 

> **\*Special policy**:  π\*, optimized, maximize long term expected reward. (note, from <s,a,r>, you know *s*, a and then know the *r*, based on rewards, find π\*) r-->z s-->x a-->y, π-->f 

## Algorithms

![Value function algorithm](/assets/images/计算机科学/118382-dd3e20cd1a05ad50.png)


![Value Iteration algorithm](/assets/images/计算机科学/118382-cb4377a287cbb947.png)

![Policy iteration algorithm](/assets/images/计算机科学/118382-2610cafe3b60422e.png)


![Linear Programming](/assets/images/计算机科学/118382-baa2c95445e5f84e.png)


![Linear programming dual](/assets/images/计算机科学/118382-aa5df06007d39cfe.png)


![Paste_Image.png](/assets/images/计算机科学/118382-e871fa461fff1828.png)

```
2015-08-26 第一章完成

第二章待续
```
