---
layout: post
title: "Reinforcement Learning 第六周课程笔记"
date: "2015-09-26 04:17:30"
categories: 计算机科学
excerpt: "Advanced Algorithmic Analysis Value iteration 1 tells us that VI converg..."
auth: conge
---
* content
{:toc}

## Advanced Algorithmic Analysis

![Advanced Algorithmic Analysis](/assets/images/计算机科学/118382-dcc80797d291bfbd.png)

## Value iteration

![Value iteration](/assets/images/计算机科学/118382-dc5111ffe8d0c7c8.png)

* 1 tells us that VI converges in a reasonable amount  of time t* (finite). We know t* exists, but we don't know when that will happen.

* 2 Gives us an bound of difference between the policy now and optimal policy. We can take this bound and test when it is a decent time to stop VI and take the current policy.

* Both 1 and 2 encourage us choosing a small γ. (γ tells us how further in the future we should look). The effective horizon is H ~ __1/(1-γ)__.

* 3 applying Bellman Operator K times to Q functions will shrink the distance between Q functions.

## Linear Programming

* Only one way to solve MDP in polynomile time：solving Bellman equation through Linear Programming. A *linear programming* problem may be defined as the problem of maximizing or minimizing a linear function subject to linear constraints. ( Defination extracted form this [PDF](www.math.ucla.edu/~tom/LP.pdf))

* Bellman equation has one part that is not linear, the *max* function. But it can be expressed by a series of linear function and a objective function `min`.

![Primal](/assets/images/计算机科学/118382-585891a739bc1274.png)

* in the *primal*, the objective function is the minimum of sum of all the V<sub>s</sub>;
* in linear programming, we can change constraints to variables and variables to constraints, and the resulting linear program is equivalent to the old one.

![The Dual](/assets/images/计算机科学/118382-64cccbc4a27ad3fb.png)

* Dual is a new linear program comes from the old primal version of linear program (没有推导过程）
* q<sub>sa</sub> is "Policy flow", maximize the expected rewards of all states.
* For each possible next state, we wanted it to be true that the amount of policy flows going through the next state should be equal to the number of the state it has been visited.

## Policy Iteration

![Policy Iteration](/assets/images/计算机科学/118382-88626729aa22a69c.png)

* Initialize the first step Q value of all the states to be 0; improve the policy at time t; Apply the policy to calculate the Q value of t+1 step.
* Convergence time is an open question (but it is finite): >= linear, <= exponential

![the concept of Domination](/assets/images/计算机科学/118382-94c89a0e2d178055.png)

* For every state, if the value of it follows π<sub>1</sub> always equals or is larger than the value when it follows π<sub>2</sub>, we say π<sub>1</sub> **dominates** π<sub>2</sub>.
* if π<sub>1</sub> **dominates** π<sub>2</sub> and there exits states that V<sup>π<sub>1</sub></sup>(s) > V<sup>π<sub>2</sub></sup>(s), we say π<sub>1</sub> **strict dominates** π<sub>2</sub>.
* if for every state, the distance between the value following policy π and following the optimal policy π* is no larger than ε, then π is __ε-optimal__.

![Why Does Policy Iteration Work](/assets/images/计算机科学/118382-5c4b61f8e9a1e74c.png)

* B<sub>1</sub> makes the update follows π<sub>1</sub> and B<sub>2</sub> makes the update follows π<sub>2</sub>
* Applying B operator to  two Values will not make them further apart, if the two values are the same, applying B will not make them closer.

![B<sub>2</sub> is Monotonic](/assets/images/计算机科学/118382-e326b361a1163cde.png)

* Theorem: if V<sub>1</sub> dominates V<sub>2</sub>, applying B will keep the ordering: BV<sub>1</sub> >= BV<sub>2</sub>.

![](/assets/images/计算机科学/118382-086e6949e8da3d94.png)

* Q<sub>1</sub> is the fix point of B<sub>1</sub>;
* π<sub>2</sub> is greedy policy with respect to Q<sub>1</sub>
* B<sub>2</sub> is the Bellman operator of π<sub>2</sub>
* Applying B<sub>2</sub> (the greedy function wrt Q<sub>1</sub>) on </sub>Q<sub>1</sub> will add a bound to Q<sub>1</sub>, thus getting a better Q<sub>1</sub>. This is called **Value Improvement**.

![Quiz 1](/assets/images/计算机科学/118382-927cd9e981675b43.png)

![Quiz 1 answers](/assets/images/计算机科学/118382-6732e17c7cc47f0d.png)

* Value improvement (or value non deprovement): for each state, value will improved until it could not get better anymore.
* Monotonicity: Value can only get better after each iteration.
* Transitivity:  a >= b, b >=c, so a >=c.
* Fixed point. If we apply B<sub>2</sub> over and over again on Q1, we will reach the fixed point of B<sub>2</sub>,which is Q<sub>2</sub>.

![wrap-up](/assets/images/计算机科学/118382-ffddbf568bcc50bb.png)

* In Value iteration, greedy policy converges in finite step. This does not necessarily mean value function will converge.

```
2015-09-23 初稿
2015-09-26 完成
2015-12-04 reviewed and revised.
```
