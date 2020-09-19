---
layout: post
title: "AI 笔记 Week 15 Planning under uncertainty"
date: "2018-12-02 17:11:33"
categories: 计算机科学
excerpt: "Link to the videosLink to the video transcripts Introduction This lectur..."
auth: conge
---
* content
{:toc}

> [Link](https://classroom.udacity.com/courses/ud954/lessons/6889127738/concepts/69398612260923) to the videos
> [Link](https://github.com/conge/OMSCS6601_Transcripts/blob/master/lesson10.md) to the video transcripts

## Introduction
This lecture will focus on marrying planning and uncertainty together to drive robots in actual physical roles and find good plans for these robots to execute.

## Planning Under Uncertainty MDP
![](/assets/images/计算机科学/118382-0327f22f4faeb2ac.png)

* Planning + uncertainty: MDPs (Markov decision process) and POMDPs (partially observed MDP)
* Planning +  uncertainty + learning: Reinforcement Learning

![](/assets/images/计算机科学/118382-1ed1347466b8b3e1.png)

Methods categorized based on the characteristics of the world (observability and certainty).
* MDP deals with situations where the world is stochastic and fully observable.

![MDP](/assets/images/计算机科学/118382-a56bf08d752c38c8.png)

* MDP has states, actions and state's transition matrix and a reward function. (it can attach to state, or action or transition?)
* it becomes Markov if the outcomes of actions are somewhat random.
* planning problem is depended on actions to each possible state. But the operational goal becomes maximizing total reward.

## Robot Tour Guide Examples
![](/assets/images/计算机科学/118382-b2cc9d1b575ea4ec.png)

All these robots need to deal with uncertainties and observabilities to do their jobs (tour guide or mine explorer).

## MDP Grid World
![image.png](/assets/images/计算机科学/118382-9b2dbfeef01f4fd2.png)

__Absorbing states__: search will end if the agent is at the absorbing states.
__Policy__ assign action based on the state the agent is in.

## Problems With Conventional Planning 1
![](/assets/images/计算机科学/118382-5e87dc252488f50a.png)

## Policy Question 
![](/assets/images/计算机科学/118382-f8741ae743a580ef.png)
Question: what is the best action to take when an agent is in states a1, c1, c4 and b3?

## MDP And Costs

The reason that the agent should be avoiding the b4 state is the cost.
![](/assets/images/计算机科学/118382-3597f117909d764e.png)

* The goal is to find the best path wich cost less with finite steps.
* The discount fact can bound the max result.

## Value Iteration 

![](/assets/images/计算机科学/118382-a75fc02831914964.png)

* value function can determine the policy based on the total reword.

![Intuition of VI functions](/assets/images/计算机科学/118382-16b011014945ccdd.png)


* The value function is a potential function that leads from the goal location all the way into the space so that hill climbing in this potential function leads you on the shortest path to the goal. 
* The algorithm is a recursive algorithm and it converges, and you have a grayscale value that really corresponds to the best way of getting to the goal. 
![Bellman equation](/assets/images/计算机科学/118382-31673e55db2b25ec.png)

## Quiz
### Determistic question:
![](/assets/images/计算机科学/118382-add4356c9bc81b7a.png)
I Quiz: calculate Value when an agent was at each state.

### Stochastic Question :
![](/assets/images/计算机科学/118382-8701cbb732608bd8.png)
Calculation is complicated here because the reward of each action must be evaluated.

## Value Iterations And Policy

![](/assets/images/计算机科学/118382-b51744dcfed36099.png)

The policy can be defined by the value function after the value of each cell is calculated. The action policy is to choose the action which leads to the highest path reward. 

![](/assets/images/计算机科学/118382-ef64d7e3cd16bbe0.png)

If the cost of each state is positive, the policy will encourage action to stay in the current state.
![](/assets/images/计算机科学/118382-0c441011b4ec2cde.png)

If the cost is too low, the value of each state might become so low that the agent will try to end the search as soon as possible without looking for an optimal solution

## MDP Conclusion

![Conclusion](/assets/images/计算机科学/118382-e6e0843725292462.png)

-----

## POMDP Vs MDP

![](/assets/images/计算机科学/118382-1400007f7aa70143.png)

* MDP is for fully observable environments and planning in stochastic environments.
* Partially observable environments, or POMDPs address problems of optimal exploration versus exploitation, where some of the actions might be __information-gathering actions__; whereas others might be goal-driven actions. 

## POMDP

![conventional planning](/assets/images/计算机科学/118382-6f60d72514190217.png)
* When the world observable and the action is deterministic, Conventional planning will work and plan the best path to the goal state.

![MDP](/assets/images/计算机科学/118382-e9e8911e2818cf76.png)
* When the world observable and the action is stochastic, MDP will work and find the best path to the goal state.

![POMDP](/assets/images/计算机科学/118382-2f904876d2da5a09.png)
* When the world partially observable (e.g. we don't know where the absorbing states are) and the action is stochastic, POMDP will need to gather information and then work to find the best path to the goal state.

![POMDP wouldn't work](/assets/images/计算机科学/118382-bcac7d03d18a3c1b.png)

POMDP would not work when there are two worlds
So here's a solution that doesn't work: Obviously, the agent might be in 2 different worlds and it does not know. Solving the problem for both of these cases and then put these solutions together will not work because the average result will never let it go south to gather information.

![POMDP will work](/assets/images/计算机科学/118382-71b9f9f58b6c1b3e.png)

POMDP on belief states will work. If the agent goes south and reaches the sign. 50% chance it will go the right-side belief state. if MDP was performed, then it will reach the +100 state. the same will happen if it goes to left-side belief state (50% chance).


> ## Readings on Planning under Uncertainty
> 
> AIMA: Chapter 17
>  
> ### Further Study
> 
> Charles Isbell and Michael Littmann’s ML course:
> 
> *   [Markov Decision Processes](https://classroom.udacity.com/courses/ud262/lessons/684808907/concepts/last-viewed)
> *   [Reinforcement Learning](https://classroom.udacity.com/courses/ud262/lessons/643978935/concepts/last-viewed)
> 
>  Peter Norvig and Sebastian Thrun’s AI course:
> 
> *   [Reinforcement Learning](https://classroom.udacity.com/courses/cs271/lessons/48724471/concepts/last-viewed)

```
2018-12-01 First draft
```
