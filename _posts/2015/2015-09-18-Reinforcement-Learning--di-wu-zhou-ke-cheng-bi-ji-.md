---
layout: post
title: "Reinforcement Learning 第五周课程笔记"
date: "2015-09-18 11:05:48"
categories: 计算机科学
excerpt: "本周三件事：看课程视频 Convergence. 读 Littman and Szepesvari (1996), 作业四。 no action..."
auth: conge
---
* content
{:toc}

本周三件事：看课程视频 *Convergence*. 读 *Littman and Szepesvari (1996)*, 作业四。


![](/assets/images/计算机科学/118382-cf2b6693fcc36b03.png)


![Learning without control:](/assets/images/计算机科学/118382-8db8c4fe2150fa34.png)

* no actions by learner. The value function is that value equals reward R(s) plus discounted expected value of the next state. (T(s, s') is transision function.  
* The new estimated value function for the state the learner just left is TD(0).

![Learning with control/actions.](/assets/images/计算机科学/118382-68ab733666d61e66.png)

Q function is used to estimate the value at current state, take a action then get a reward and ended up in a new state < s<sub>t-1</sub>, a<sub>t-1</sub>,r<sub>t</sub>,s<sub>t</sub> >.  The Q updating rule takes care of two approximations: 1) if model is known, it can be used to update Q; 2) if Q* is known, it can also be used to update Q.

And both will converge.

![Quiz 1: Bellman Operator](/assets/images/计算机科学/118382-d53c693f855032f6.png)

* See value iteration [here](http://www.jianshu.com/p/881ab7e41adb)

![Contraction mapping def: If applying the B operator makes the distance between two functions smaller than the the distance between the original functions.](/assets/images/计算机科学/118382-7c3977dbd01f8714.png)

![Quize 2: ](/assets/images/计算机科学/118382-fa0691820356d664.png)

* Practically, if B is multiplying a number in \[0,1), B is contraction mapping.
* take the first option for example: ||B(x) - B(y)||=||x/2 - y/2|| =1/2 ||x - y||, so there exists γ >=1/2 makes ||B(x) - B(y)|| <=γ||x - y||. So B(x) = x/2 is a contraction mapping.

![Contraction Properties](/assets/images/计算机科学/118382-dd729fbea44b9ed8.png)

* ① and ② are true, so that BF<sub>t-1</sub> = F<sub>t</sub>, F<sub>t</sub> will converge at F* through value iteration.

* If there is two fix point, G* and F*, Putting them into the B operator will not change the distance of them because both of them are fixed, and this violates the definition of B. 

![](/assets/images/计算机科学/118382-9bf2051b7eafe222.png)

* Applying B operator to Bellman equation and unpacking ||BQ<sub>1</sub> - BQ<sub>2</sub>||<sub>∞</sub>.
* Not combining the *max* a' because the a' are not the same in Q<sub>1</sub> and Q<sub>2</sub>

![](/assets/images/计算机科学/118382-f8ea3d21e4bd4b5e.png)

* stop here, first, will go back. that's call this the unfinished proof.

![quiz 3](/assets/images/计算机科学/118382-340442f9bfd6c502.png)

![](/assets/images/计算机科学/118382-a49f5787c0ee1ee1.png)

* Max is non-expansion: ||maxf(a) - maxg(a)|| <= max|(f(a) -g(a)|. Using this

![Statement of therom](/assets/images/计算机科学/118382-0f4d33c91c04799c.png)

The three properties need to be true for Q<sub>t</sub> to converge to Q*. and they are true

So, Q-learning converges.

![](/assets/images/计算机科学/118382-5d6cfb5b05d86892.png)

B<sub>t</sub> is the operator we are going to update Q at *t* time step. *Q(s,a)* is the Q function value of the state we just left and Q function *w* is the Q value of the state we just arrive. In regular Q Learning update, Q and *w* are the same, here we separated them in the theorem.

So, rule number one is saying if we know the Q* and use the updating rule (in pink) to update the Q function,  the expected value of the one-step look ahead (*w*) can be calculated and the stochasticity will be averaged out.

![](/assets/images/计算机科学/118382-eda5a85c25ff1978.png)

If we hold the Q(s,a) fixed and only varies the way we calculate the one-step look ahead, the distance between the Q* and Q can only get closer with each update.

The third condition is the learning rate condition.  which is needed for Bellman equation.


![Quiz 4: 1. decision making on estimated value based on best next action (regular MDP). 2. The environment puts you in the worst possible state and you choose the next best action given the state (risk averse); 3. The state is the expected value but the action to take is based on ranking of the action(exploration-sensitive, min, max, mediocre ); 4. (zero-sum game)](/assets/images/计算机科学/118382-c3439dd875346192.png)

* the take home messages are, these generalized MDPs all converges.
* so the correct answers are: (from top to bottom) worst possible decision, not-optimal decision, two agent competing decision making (the zero-sum game).

![Recap](/assets/images/计算机科学/118382-5587b8046cfcadd7.png)

Generalized MDP can be seen as redefine fix point. Contraction might be something like "收敛" in Chinese. Q-learning converges to Q*. Generalized Convergence theorem uses two Q-functions to prove the convergence of Bellman Equation.
