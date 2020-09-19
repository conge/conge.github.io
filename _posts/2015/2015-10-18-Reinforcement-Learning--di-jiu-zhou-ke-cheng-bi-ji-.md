---
layout: post
title: "Reinforcement Learning 第九周课程笔记"
date: "2015-10-18 02:41:40"
categories: 计算机科学
excerpt: "This week Watch Generalization. The readings are Gordon (1995) and Baird..."
auth: conge
---
* content
{:toc}

This week  
* Watch *Generalization*. 
* The readings are *Gordon (1995) *and* Baird (1995).*

![Generalization](/assets/images/计算机科学/118382-9310c266d53d3bb7.png)

![Example](/assets/images/计算机科学/118382-15a6061d8c8cd348.png)

* When there are a lot of states, we can use features to represent states (e.g. grouping states using some common features or using some base states to represent other stats)
* Inductive bias: refer to the way algorithm prefer one solution against another.
* representation can stay unchanged even when states changed(?)

![Generalization idea](/assets/images/计算机科学/118382-f4afb986d8264ff0.png)

* In RL, the goal is to learn some input-output mapping. 
  * e.g. Policy maps state -> actions 
  * value function maps state/actions to expected return
  * Model maps T/R (transition and reward)
  * Generalization can happen on all these levels 
* Most researchers are focused on __value function__ approximation.

![Basic Update Rule](/assets/images/计算机科学/118382-89f07fed7553e314.png)

* Q is represented by function approximator F(w<sup>a</sup>, f(s)). w<sup>a</sup> is some kind of weights, f(s) takes a state _s_ and generate a series of features.
* experience tuple <s,a,r,s'> comes in, and do an update.
* TD error= the difference between predicted value (reward + discounted value of next state) and value of current state. TD error tells us the direction to move the parameters _w_. (the prediction is high, low or just right).
*  α is learning rate.

## Linear Value Function Approximation

![Linear value function](/assets/images/计算机科学/118382-d9994c638a29f0ff.png)

* Q value for an action is represented by features and a set of weights
* _w_<sup>a</sup><sub>i</sub> are weights of features f<sub>i</sub>(s), which represent importance of features

![Quiz 1](/assets/images/计算机科学/118382-626ee8bf2b94526e.png)

## Success and fail stories

![Does it work?](/assets/images/计算机科学/118382-cd110eb4ef5a32b6.png)

* 3-layer back prop: decision making in Jeopardy
* CMAC([wikipedia](https://en.wikipedia.org/wiki/Cerebellar_model_articulation_controller)) : 


![Baird's Counter example](/assets/images/计算机科学/118382-510b8512f8a6cf7c.png)

![Quiz 2: Bad Update Sequence](/assets/images/计算机科学/118382-54563d182803acda.png)

* V(s') = V(7) =8; V(s) = V(1) =3, derivative is w =1; so  Δw<sub>0</sub> = 0.1( 0 + 0.9 * 8 -3)*1 = 0.42;
* Δw<sub>0</sub> is 0.42, and Δw<sub>i</sub>, i = [0, 6] are all positive, so weight will increase with each update
* Δw<sub>7</sub> is negative when we update <7,0,7>, but w<sub>7</sub> will still increase because it's original value is >> |Δw<sub>7</sub>|
* So, even the algorithm is doing the right thing, the updates will never converge

![Quiz 2: What if we initialize all the weights as 0](/assets/images/计算机科学/118382-aaacf7d55655c05f.png)

* in this case, the temporal differences are all zeroes because w<sub>i</sub> is 0, which means no updates (changes) are going to happen. __Sticky__
* If at any circumstance, when all values are zero, it could not escape the circumstance unless reward (*r*) is non-zero. __If reward is also zero, we can call the circumstance the solution of the MDP__.
* this holds when MDP is __deterministic__.
* the lesson: Shared weights can "not converge"!

![Averagers: looks like  Linear Value Function Approximation but is non-linear](/assets/images/计算机科学/118382-4879e276577c7384.png)

* Problem: given a certain points of value, estimate the function of line. How to estimates the points in-between?
*  Naturally, weighted average of neighbours and get convex combinations of anchor points
* for points that are far from anchor points, are good estimate will be the average of the anchor points.
* more anchor points lead to less error in MDP estimation.

![quiz 3](/assets/images/计算机科学/118382-1740031ded7636c1.png)

![Connection to MDPs](/assets/images/计算机科学/118382-c36f7d653a5bbd00.png)

* Using base states, we can respresent the original MDP with MDP over S<sub>b</sub>s

## What have we learned

![recap](/assets/images/计算机科学/118382-85ea45dc5fa114f6.png)

* __Need__ for generalization: some problem have Zillions of states; Method: applying supervised learning method .
* Methods: Linear function approximation.
  * 1) value functions 2) policies; 3) models;
* Success: TD gamma, Atari, Fitted Q-iteration (but still have need not work cases)
* Problem cases: even linear need not work (baird counter problem)
* Averagers: can be viewed as MDP itself. Use anchor points to represent the whole MDP.
* __LSPI__: Least Squared policy iteration


```
2015-10-13 初稿 upto quiz 1
2015-10-17 完成
2015-12-04 reviewed and revisted
```
