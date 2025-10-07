---
layout: post
title: "Machine Learning笔记 第06周"
date: "2016-02-19 14:52:00"
categories: 计算机科学
excerpt: "Week 06 tasks: Lectures: Randomized Optimization. Reading: Chapter 9 of ..."
auth: conge
---
* content
{:toc}

Week 06 tasks:

- Lectures: Randomized Optimization.
- Reading: Chapter 9 of Mitchell, as well as the overview on the No Free Lunch Theorem.


![Randomized Optimization](/assets/images/计算机科学/118382-caf3c9112399c651.png)

![Optimization](/assets/images/计算机科学/118382-793ee932acc99772.png)

* optimization is to find a x<sup>*</sup> in input space X to make the objective function has the maximum (or close to maximum).

## Optimize Me

![Quiz: best x](/assets/images/计算机科学/118382-c84e02010ff65c18.png)
* The first question, since the input space is small, we can plot the function and find the largest f(x).
* the second the functions, we can try to use calculus: Set the derivative f(x) to 0 and solve the derivative function ( which will be hard to solve since it's a cubic function). Alternatively, we can try to plot the data using subgroup of x.

## Optimization Approaches

![Optimization Approaches](/assets/images/计算机科学/118382-915c869fca69aa8b.png)
* Three approaches:
  * generate & test: when we have a small input space but a complex function
  * using calculus: when the function has derivative and the derivative function is solvable when its value is set to 0
* Newton's method: when the function has derivative and it can be improved iteratively.
* When these approaches does not work, then __Randomized Optimization__.

![Hill Climbing](/assets/images/计算机科学/118382-ba928c8c03ef0b4f.png)
* the hill climbing algorithm will stuck at a __local maxima__.

![Quiz 2: find my word](/assets/images/计算机科学/118382-c39d7c1515aca84c.png)

## Random Restart Hill Climbing

![Random Restart Hill Climbing](/assets/images/计算机科学/118382-273a0bb7f5b14d05.png)
* how to avoid the unlucky starting point?
  * checking and make sure the starting point is not visited before
  * make sure the starting point is faraway from known local maxima

![Quiz3: randomized Hill climbing](/assets/images/计算机科学/118382-90b89394de06def1.png)
* The six points under the maxima hill are special
  * 4 points under the global maxima will take average 4 steps to get to the global maxima. and that's the 4/28*(4)
  * the 2 basin points, half of the time will lead up in global maxima, and half of the time will lead to local maxima (and restart).
* all the other 22 points will lead to local maxima and then start a new round with a randomized starting point.
* if keep track of the points visited, the algorithm might do better than 28 on average.
* if the attraction basin under the local maxima is large, hill climbing will do better.

## Annealing algorithm

![Simulated Annealing](/assets/images/计算机科学/118382-6c9f354d70ee651e.png)

* One step further than hill climbing: allow downwards to "explore"

![Annealing algorithm](/assets/images/计算机科学/118382-85b6a8cdb56911b6.png)

* if f(x<sub>t</sub>) and f(x) is very close, then f(x<sub>t</sub>) -f(x) is close to 0 and p will be 1.
* If T is really big, say infinity, then f(x<sub>t</sub>) -f(x) doesn't matter then. P will be 1, and x will jump to x<sub>t</sub>
* if T is really small, close to 0, p will climb, not jump.

![ Properties of Simulated Annealing](/assets/images/计算机科学/118382-65210d36eff5b72a.png)

* T -> 0: like hill climbing
* T-> ∞: random walk
* Desearse T slowly:  As T decreases, it's harder and harder to jump over local maxima, and algorithm will reach global maxima

## Genetic Algorithms

![GA](/assets/images/计算机科学/118382-2e25936150f0be16.png)

* GA is like random restart but doing the restart in parallel.
* Crossover - population holds information.

![ GA Skeleton](/assets/images/计算机科学/118382-6c6754dbf31031e0.png)
* Define "most fit"
  - top half or truncate selection:the half individuals with the largest score
  - weighted prob. or roulette wheel: weighted fitness function with probability.
* what's crossover?

![Crossover Example](/assets/images/计算机科学/118382-9d43da8681c2a253.png)

* Uniform crossover: randomization at each position

![Recap](/assets/images/计算机科学/118382-b778c74f2f9ab60f.png)

## MIMIC

* [Charles' paper on MIMIC](http://www.cc.gatech.edu/~isbell/papers/isbell-mimic-nips-1997.pdf)

![MiMIC](/assets/images/计算机科学/118382-6bc2056cc3077470.png)

![Quiz 4:](/assets/images/计算机科学/118382-c361ac5d21a7e5a3.png)

* when θ is min, then P is the uniform distribution of X
* when  θ is max, we get the maxima or optima of the distribution

![Pseudo code](/assets/images/计算机科学/118382-c6fbe26d31b05f63.png)
* Given a threshold θ<sub>t</sub>, generate samples from P<sup>θ<sub>t</sub></sup>(x), then set θ<sub>t+1</sub> to be n<sup>th</sup> percentage and retain only those samples, s.t. f(x)>=θ<sub>t_1</sub>
* instead of using these samples, we estimate P<sup>θ<sub>t+1</sub></sup>(x), and then generate new samples from it. then repeat the process again and again until converge.
* Two assumptions:
  * P<sup>θ<sub>t</sub></sup>(x) is estimable
  * P<sup>θ<sub>t+1</sub></sup> is close enough to P<sup>θ<sub>t</sub></sup>
* this is a lot like Genetic algorithm but P<sup>θ</sup> and P<sup>θ＋ ϵ</sup> can preserve the structure.

![Estimating Distributions](/assets/images/计算机科学/118382-c3e4aa7a8aafd90a.png)
* P(x) is the combination of the p of each x in X=[x1 x2 .... x<sub>n</sub>] given others in X. To estimate P(x) this way, we will need huge amount of data ( exponential to n).
* Dependent tree: each node only have one parent.
  * it can represent relationships
  * and sampling dependent tree is easy
  * it's a general form of crossover and it does not require locality.

## Finding Dependency Trees

![Finding Dependency Trees](/assets/images/计算机科学/118382-92f96ba174026094.png)
* Minimize Divergence of P and P_hat<sub>π</sub>, Divergency can be written as entropy.
* build a cost function by remove -h(p) and add entropy -h(x<sub>i</sub>), then we get the mutual information between x and **π**
* Finding Dependency Trees is now converted to a problem to maximize mutual information between x and it's parent. or in another word, to find the parent who knows the most about the node.

![Finding Dependency Trees](/assets/images/计算机科学/118382-e4f4cd310aea0f3b.png)
* This can be solved by solving the maximum spanning tree. Using Prim.
* The prim algorithms is fairly fast algorithm ( polynomial to the number of edges of a graph) and it's good for dense connected graph.

![back to pseudo code](/assets/images/计算机科学/118382-786b60e3a31ce2fc.png)
* dependent tree is used to estimate P given the samples from the previous step.

![Quiz 5: Probability Distribution](/assets/images/计算机科学/118382-5ae60dc9cb79b77f.png)

* what distribution can represent the maxima of the problems on left column.

![Practical Matters](/assets/images/计算机科学/118382-e7908601e6234331.png)

* MIMIC evaluate cost function less when comparing to Simulated Annealing, but it usually takes longer to run.
* MIMIC will get more information in and out


```
2016-02-17 完成 Genetic Algorithms
2016-02-19 初稿
```
