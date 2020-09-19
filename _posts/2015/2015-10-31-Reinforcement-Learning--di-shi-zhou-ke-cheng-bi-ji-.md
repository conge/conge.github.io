---
layout: post
title: "Reinforcement Learning 第十周课程笔记"
date: "2015-10-31 04:57:13"
categories: 计算机科学
excerpt: "This week watch *POMDPs. * The reading is Littman (2009). POMDP POMDPs g..."
auth: conge
---
* content
{:toc}

This week 
* watch *POMDPs. *
* The reading is *Littman (2009).* 

![Partially Observable MDPs](/assets/images/计算机科学/118382-d0c762ee64a9cb17.png)

## POMDP

![POMDP definition](/assets/images/计算机科学/118382-02856ea580f2ccbb.png) 

* POMDPs generalizes MDPs.
* In POMDP, MDP (represented by <S,A,T,R>) is not directly observable to the agent. we can only observe the states. Z are observables to the agent, Z is a set of states in S. 
* O(S,Z) is the mapping function of Z to <S,A> (e.g. Given Z, what's the probability of S).

![quiz 1](/assets/images/计算机科学/118382-0ea8aefefba47abc.png)

* When O(S,Z) = 1, the observable Z is S. So, Z and O together determines the relationship between S and Z in the POMDP.

![quiz 2: POMDP Example ](/assets/images/计算机科学/118382-671cb3a41b80aacb.png)

Solution:  

![Solution](/assets/images/计算机科学/118382-2a31e9646dc5c34a.png)

* keep track of probability of ending up in each state after each step.
* There is a normalization after each step (not the right thing to do but works.).

## State Estimation

![State Estimation](/assets/images/计算机科学/118382-dd48f36e60324c86.png)

* Belief state b(s) is a probability distribution vector of whether we are in s.
* using belief state can turn POMDP into belief MDP <b, a, z, b'>
> b'(s') = Pr(s'|b, a, z) 
= Pr(z|b,a,s') Pr(s'|b,a) / Pr(z|b,a)   
= Pr(z|b,a,s') sum Pr(s'|s,b,a) Pr(s|b,a) / Pr(z|b,a)   
= O(s',z) sum<sub>s</sub> T(s,a,s') b(s) / Pr(z|b,a) 

* Note: belief MDP has infinite number of belief states which make VI, LP, PI impossible because they can only deal with finite number of states.
 
## Value Iteration in POMDPs 

### Math

![Value Iteration in POMDPs](/assets/images/计算机科学/118382-cc7502ad8b6219d2.png)

* Initialized V<sub>0</sub>(b) as 0 
* V<sub>t</sub>(b) can be written as something similar to bellman equation
* Claim  V<sub>t</sub>(b)  can be represented by the maximum of a set of linear functions of b and α. α is a finite set of vectors. this is called piecewise linear and convex. 

![quiz 3: piecewise linear and convex. ](/assets/images/计算机科学/118382-ea0ffd6d6d73b636.png)

* Γ<sub>0</sub> should be a vector of zeroes.

![piecewise linear and convex](/assets/images/计算机科学/118382-7377a46c63733df3.png)

* Piecewise linear means V<sub>t</sub>(b) can be represented by V<sup>a</sup><sub>t</sub>(b),  V<sup>a</sup><sub>t</sub>(b) can be represented by V<sup>a,z</sup><sub>t</sub>(b) and V<sup>a,z</sup><sub>t</sub>(b) can be represented by something like a Bellman equation

![piecewise linear and convex](/assets/images/计算机科学/118382-4517de226631e99d.png)

* In a similar sense, Γ<sub>t</sub> can be represented by  Γ<sup>a</sup><sub>t</sub> , Γ<sup>a,z</sup><sub>t</sub> and something like a Bellman equation.
* Thus the belief MDP becomes computable.
* pomdp-solve is an existing solver for pomdp.
* Guaranteed to be exponential because size of Γ is exponential in respect to the size of observables: | Γ<sub>t</sub>| = | Γ<sub>t-1</sub>|<sup>|z|</sup> dot |A|
* the calculation could be faster if Q function (V<sup>a</sup><sub>t</sub>(b) is the Q function) has a small representation.

### algorithm

![algorithm for vector purge](/assets/images/计算机科学/118382-c22f477ddfd1de4d.png)

In the figure:
* all the linear functions (vectors) are dominated by the blue lines which involves three linear functions.
* function ① and ③  can be purged because they have no contribution to the overall vector


![Quiz 4: Domination](/assets/images/计算机科学/118382-44a16fda21e55833.png)

* Domination: if one vector is always less than (in this case) another vector, we say it's dominated by that another vector.
* Vector is purgeable if it does not contribute to the max

### Learning POMDP

![RL for POMDPs](/assets/images/计算机科学/118382-0ce90c853759dcee.png)

* Planning: if know the model of POMDP, can run value iteration. Since POMDP have infinite number of states, we can only get approximation of optimal policy.
  * VI may not be converge 
  * PI is not possible because infinite believe states 
* Difference between planning and reinforcement learning:
  * Planning: know the model - planning in POMDP is undecidable.
  * RL: we don't know the model have to interact to learn
* RL has 2 types:
  * Model based RL: learn the model (POMDP) and use it
  * Model free RL: don't learn the model but mapping observables and action.

![Quiz 4: relationship of POMDP and other Markov systems](/assets/images/计算机科学/118382-5b98d6c15ffd811b.png)

* MC: *Markov Chain*, observed but uncontrolled; HMM: *Hidden Markov Model*, partially observed and uncontrolled; MDP: observed and controlled. POMDP: partially observed and controlled. 
* EM: *Expectation Maximization*, an procedure to learn the hidden property in HMM or POMDP. 
* Model based Learning.

## Learning Memoryless Policies (Model free RL of POMDP)

![quiz 5:](/assets/images/计算机科学/118382-9173406f2d344664.png)

* in the MDP, There 3 blue states, to get to the green state, the agent needs to move to right in 2 of the states and move to left in another state. So the solution for this quiz is 1/3 and 2/3.

![验证quiz](/assets/images/计算机科学/118382-a63cdcbcb73523dd.png)

* solve and compare the value function based on the 50-50 probability (policy) and 1/3 - 2/3 policy.
> X = p \* (0.5 \* X) + (1 -p)(0.5 \* Y)  => X = 0.5 \* (1 - p)Y / (1 - 0.5p)
> Y = p \* (0.5 \* x) + (1 -p) => X = 2 *(Y - 1 + p) / p
> Z = p \* (1) + (1 -p) (0.5 \* Z) => 
> V = 1/3 \* (X + Y + Z)


## RL as POMDP:

![quiz 7:  Bayesian RL](/assets/images/计算机科学/118382-e83623b793fa63e0.png)

* we can be in MDP A or B but not C, and we will be in state 2.
* Next, we can take a purple action to figure out which MDP we are in.

![](/assets/images/计算机科学/118382-b2d2289d40dae8a6.png)

* So the optimal policy is figuring out which MDP we are in and get hight reward by exploiting in the belief state.
* RL itself is like POMDP which requires exploring and exploiting.

![Bayesian RL](/assets/images/计算机科学/118382-a4551ff84f46ca8f.png)

## Predictive State Representation

![Predictive State Representation](/assets/images/计算机科学/118382-2e5a6fa72a06bf5b.png)

![quiz 8: Using belief state to figure out Predictive State](/assets/images/计算机科学/118382-94385421de2f7518.png)

* The POMDP has 4 states but 3 observables represented by colors where the two red states are not distinguishable.
* We can do test to get predictions of states. (e.g, a test can be moving up, and see the probability of ending up at the blue test).  

![Predictive State](/assets/images/计算机科学/118382-4de05f4afd159cdc.png)

* Belief state and predictive state does not have a one-on-one mapping.
* Increasing number of tests will constrain the mapping.

![PSR Theorem](/assets/images/计算机科学/118382-64cba59d3e23c01b.png)

Why go to PSR? 
* We can not observe all the states in POMDP and they might not even exist.
* we can do some test to figure out what state we might be in.
* Learning a PSR sometimes is easier than learning a POMDP.
* Number of test is always going to be no more than the number of states


![ What Have We Learned?](/assets/images/计算机科学/118382-3b3c97e223cb009d.png)

```
2015-10-23 初稿
2015-11-03 补全
2015-12-04 reviewed
```
