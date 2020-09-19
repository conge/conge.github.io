---
layout: post
title: "Reinforcement Learning 第七周课程笔记"
date: "2015-09-30 02:54:06"
categories: 计算机科学
excerpt: "This week's tasks watch Reward Shaping. read Ng, Harada, Russell (1999) ..."
auth: conge
---
* content
{:toc}

![](/assets/images/计算机科学/118382-5130b0de811fc710.png)

## This week's tasks

* watch *Reward Shaping*. 
* read *Ng, Harada, Russell (1999)* and* Asmuth, Littman, Zinkov (2008).*
* office hours on Friday, October 2nd, from 4-5 pm(EST). 
* Homework 6.

## Why changing RF?

![Why changing MDP](/assets/images/计算机科学/118382-8266bfdd6ee09ca4.png)

Given an MDP, RF can affect the behavior of the learner/agent so it ultimately specifies the behavior (or policy) we want for the MDP. So changing rewards can make the MDP easy to solve and represent 

1. **Semantics**: what the agent are expected to do at each state;
2. **Efficiency**: speed (experience and/or computation needed), space (complexity), and solvability .

## How to change RF without changing optimal policy.

![How to Change RF](/assets/images/计算机科学/118382-060f9fe65c9e2e60.png)

Given an MDP described by <S, A, R, T, γ>, there are three ways to change R without changing optimal solution. (Note, if we know T, then it is not a RL problem any more, so this part of lecture if for MDP not RL specifically).

1. Multiply by a positive constant ( non-zero 'cause multiply by 0 will erase all the reward information)
2. shift by a constant
3. non-linear potential-based

### 1. Multiply by a positive constant

![Quiz 1](/assets/images/计算机科学/118382-ce3893e4ffd59041.png)

* Q(s,a) is the solution of Bellman function with the old RF R(s,a).
* R'(s,a) is a new RF with is the old RF multiplying by a constant.
* What's the new solution Q'(s,a) with respect to the new RF R'(s,a)  and old Q(s,a)?

Here is how to solve the problem:

1. Q = R + γR+γ<sup>2</sup>R + ... + γ<sup>∞ </sup>R)
2. Q' = R' + γR'+γ<sup>2</sup>R' + ... + γ<sup>∞ </sup>R'
3. Replace R' with c\*R, 
Q'=(c\*R) +γ(c\*R)+γ<sup>2</sup>(c\*R) + ... + γ<sup>∞ </sup>(c\*R)
  =c(R + γR+γ<sup>2</sup>R + ... + γ<sup>∞ </sup>R) 
  =c\*Q 

### 2. shift by a constant

![Quiz 2: Add a scalar](/assets/images/计算机科学/118382-b11b96e380510abf.png)

![Solution and proof of Quiz 2](/assets/images/计算机科学/118382-9dc4a4660fed5fd6.png)

> 1. Q = R + γR+γ<sup>2</sup>R + ... + γ<sup>∞ </sup>R)
> 2. Q' = R' + γR'+γ<sup>2</sup>R' + ... + γ<sup>∞ </sup>R'
> 3. Replace R' with R+c, 
Q'=(R+c) +γ(R+c)+γ<sup>2</sup>(R+c) + ... + γ<sup>∞ </sup>(R+c)
  =(R + γR+γ<sup>2</sup>R + ... + γ<sup>∞ </sup>R) + (c+γc+γ<sup>2</sup>c + ... + γ<sup>∞ </sup>c)
> 4. The first part is Q and the second part is geometric series. So,
Q'  = Q + c/(1-γ)


### 3. nonlinear potential-based reward shaping

![Quiz 3: potential-based reward shaping](/assets/images/计算机科学/118382-efa41453eb9c20b6.png)

> 1. Q = R + γR+γ<sup>2</sup>R + ... + γ<sup>∞ </sup>R)
> 2. Q' = R' + γR'+γ<sup>2</sup>R' + ... + γ<sup>∞ </sup>R'
> 3. Replace R' with R-ψ(s) + γψ(s'), 
Q'=(R-ψ(s) + γψ(s')) +γ(R-ψ(s') + γψ(s''))+γ<sup>2</sup>(R-ψ(s'') + γψ(s''')) + ... + γ<sup>∞ </sup>(R-ψ(s<sup>∞ </sup>) + γψ(s'<sup>∞ </sup>))
  =(R + γR+γ<sup>2</sup>R + ... + γ<sup>∞ </sup>R) + (-ψ(s) + γψ(s') +γ(-ψ(s') + γψ(s''))+γ<sup>2</sup>(-ψ(''s) + γψ(s''')) + ... + γ<sup>∞ </sup>(-ψ(s<sup>∞ </sup>) + γψ(s'<sup>∞ </sup>))
> 4. The first part is Q. In the second part, most of the elements are cancelling each other out and only has the very first and last elements left. So,
Q'  = Q + (-ψ(s) + γ<sup>∞ </sup>ψ(s'<sup>∞ </sup>)
5. Given γ is in (0,1), so γ<sup>∞ </sup>=0. Then we have Q':
Q' = Q - ψ(s)

## Q-learning with potential

Updating the Q function with the potential based reward shaping, 

1. Q function will converge at Q*(s,a).
2. we know that Q(s,a) = Q\*(s,a) - ψ(s). If we initialize Q(s,a) with zero, then  Q\*(s,a) - ψ(s) =  Q\*(s,a) - max<sub>a</sub>Q*(s,a) = 0, that means a is optimal.
3. so Q-learning with potential is like initializing Q at Q*

![Q-learning with potential](/assets/images/计算机科学/118382-22ebfa9051884003.png)

## What have we learned?

![Summary](/assets/images/计算机科学/118382-1a8dc85f3abe5f75.png)

* Potential functions is a way to speed up the process to solve MDP
* Reward shaping might have suboptimal positive loops which will never converge?

```
2015-09-29 初稿
2015-12-04 reviewed and revised
```
