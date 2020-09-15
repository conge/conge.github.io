---
layout: post
title: "AI-笔记-Week-04-Simulated-Annealing"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

> This week you should watch Lesson 3, [Simulated Annealing](https://classroom.udacity.com/courses/ud954/lessons/5609649268/concepts/66957111270923), and read Chapter 4 in *AIMA *(Russell & Norvig). 

> **Assignment 2: Tridirectional Search** Due: September 24

# Traveling Salesman Problem

# NP hard: Non-deterministic polynomial time

![Optimal solution: not cross pathes](/assets/images/计算机科学/118382-07091a3519caa456.png)

# Quiz: Challenge Question
![Challenge Question.png](/assets/images/计算机科学/118382-90c072f5273e0a7a.png)

* iterative improvement problem

# 4-Queens

![4-Queens](/assets/images/计算机科学/118382-f6fa933b54b79db0.png)

* N-Queens problem: On an N x N board, place N queens.
* Move queens so that they won't be able to attack one another. That is, no queens on horizontal, vertical or diagonal lines.


![Try some stupid things first and then add intelligence until we solve the problem](/assets/images/计算机科学/118382-1a8ed5d1f21ff7b7.png)

* an effective way to solve the problem is to start with the Queen have most attacks and solve it first.

![Solving a 5-Queen problem](/assets/images/计算机科学/118382-7a40edc51a7dd751.png)
* Note: there are multiple solutions here.


![N-Queens Heuristic Function](/assets/images/计算机科学/118382-2288dfe9262e3b3d.png)

* to solve the question, we can use the "stupid" strategy to take the move to reduce the number of attacks.
* but, it is possible that there would be no move to reduce the number of attacks. See below.

## n-queens with local minima 
![local minima](/assets/images/计算机科学/118382-74bc91798bcf2b2c.png)
* in the current board above, there is only one attacks happening between the queen in column 4 and 7. 
* moving any queen on the board will increase the number of attacks on this board.

# Hill Climbing

![local Maximum](/assets/images/计算机科学/118382-a53c865310b0b229.png)
* Goal: to find the global maximum
* method, select a state (initial state), climb the hill to both directions by a small step. The direction that increased the objective function will be chosen for next hill climbing.
* problem: it could get stuck at local maximum ( shoulder, "flat" or pointy local maxima)
* Solution: Random Restart

## Random Restart

![radom start](/assets/images/计算机科学/118382-1d08f82acdfc226f.png)
* we can randomly select a starting point for hill climbing. If we select enough start points of start, then we can find the maximum value and its corresponding state.

* the problem is that we never know if enough sampling was done.
* Taboo search: when randomizing the starting state, use "sampling without replacement". Once visited, the randomization will not revisit the state visited before.

## quiz

![quiz](/assets/images/计算机科学/118382-3fbacabe36cba0c6.png)

* using hill climbing algorithm, figure out the value of each particle.

## step size 

* If the step size is small, the algorithm can stick at flat shoulder or maxima.
* If the step size is large, the algorithm might skip the hilltops, ends up oscillating between lower values and never converge.
* solution: start with large steps but end with small steps. Very similar to annealing.


![Quiz](/assets/images/计算机科学/118382-2e9fd067c5386e69.png)
 * assuming step size = 2. where each particle will end up with?

# Annealing

* In physics, when molecules are allowed to move, they often form structures/patterns to preserve energy, which is minimum energy constructions.
* Annealing: increase the temperature to allow molecules to move and lower the temperature to let them form new structures until desired structure is achieved.

* Simulated Annealing: heating and cooling idea was borrowed into hill climbing algorithm. The heating means increasing randomness and gradual cooling means decreased randomness. use heating to get out of local maxima and cooling to reach global maxima.

Image sources:
* [Mud cracks / sewage sludge](https://en.wikipedia.org/wiki/Sewage_sludge) - Wikipedia
* [Honeycomb](https://pixabay.com/en/queen-cup-honeycomb-honey-bee-337695/) - Pixabay
* [Columnar basalts](https://commons.wikimedia.org/wiki/File:Columnar_basalt_Brei%C3%B0afj%C3%B6r%C3%B0ur_2012-07_B.JPG) - Wikipedia (this one is actually from Iceland)
* [Heat treating (atomic lattice)](https://commons.wikimedia.org/wiki/File:IronAlfa%26IronGamma.svg) - Wikipedia
* [Heat treating (sword making)](https://commons.wikimedia.org/wiki/File:Katana_hardened_edge_pic_with_inset_of_nioi.JPG) - Wikipedia

## simulated annealing

![annealing algorithm](/assets/images/计算机科学/118382-8ca8e9611bd2c5ab.png)
* T is the simulated temperature at time t, which reduces from a high value at the beginning to near zero eventually.
* ΔE is the change in energy going from current to next.
* when T -> ∞, e<sup>ΔE / T</sup> = e<sup>0</sup> = 1 and the simulated annealing allows large randomness, so it can visit a lot of states.
* when T -> 0, say T = 0.01, and the current status have a -1 energy, ΔE = -1. Then e<sup>ΔE / T</sup> = e<sup>-1/0.01</sup>  = e<sup>-100</sup>, which is very small and the position will not be taken due to the small posibility.
* when at shoulder or flat maximum, ΔE = 0. no matter what T is, e<sup>ΔE / T</sup> =  e<sup>0</sup> =1. the algorithm will take a random start to the agent out of the local maxima 

## Local Beam Search

![LBS](/assets/images/计算机科学/118382-3070306aff0f734b.png)
* track multiple particles at the same time
* generate neighbors randomly and compare them to keep the best ones for next iteration.
* stochastic Beam Search: when the generation of neighbors, some randomness was considered when dicide the fitness

# Genetic Algorithms

## representation N-Queens problem

![coding system for n-queens problem](/assets/images/计算机科学/118382-2047c87c6527f4ef.png)
the maxim fitness of n-queens problem

![Maxim number of attaching queens is n!/(n-2)!/2!  ](/assets/images/计算机科学/118382-ac4e884e848bb0f6.png)

* Maxim number of attaching queens is n!/(n-2)!/2! 
* fitness = n!/(n-2)!/2!  - # of attacking queens

## GA example

![image.png](/assets/images/计算机科学/118382-cbc345c66aed82cf.png)
* four random board, first, find their fitness based on the fitness function.
* normalize the fitness value and roll dice of 100 and choose the parent based on the dice #. for example, choose parent 1 when the number is 1 ~ 31, choose parent 2 when the number is 32 ~ 60, and so one...
* when four parents are chosen, children can be generated by crossover, switching part of the sequence with another parent to form a new one. Hopefully, this process will bring the better part of both the parents together.

## mutation
![mutation](/assets/images/计算机科学/118382-04f253e8620cfeac.png)
* it's possible that a critical step is not on any of the parents. In this case, more randomness is needed and one can randomly change one queen's position.
* The mutation is like to randomly occasionally chose a direction and simulated annealing while the randomness part is more like **sochastic beam search**.

## GA quiz

![image.png](/assets/images/计算机科学/118382-3ac158f4a9b91c6a.png)

## challenge question revisited
![challenge question](/assets/images/计算机科学/118382-bba3a26ff2e5cfa1.png)

For another viewpoint and some extensions, check out Charles Isbell and Michael Littman’s course section on this topic: [Randomized Optimization](https://classroom.udacity.com/courses/ud741/lessons/521298714/concepts/5344086080923)

```
20170917 - v01: 3 hours
```
