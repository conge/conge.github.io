---
layout: post
title: "AI-笔记-Week-03-Search"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

> This week you should watch Lecture 2, [Search](https://www.udacity.com/course/viewer#!/c-ud954/l-6375179396), and read Chapter 3 in *AIMA *(Russell & Norvig).

![膜拜AI大神 Peter Norvig](/assets/images/计算机科学/118382-c17e70c3cd81eac3.png)

# challenge question

![Which algorithm to choose to solve a tri-city problem?](/assets/images/计算机科学/118382-dbf0035efa52ed3b.png)

![Challenge 2 Rubik’s Cube](/assets/images/计算机科学/118382-7a492517f55b0f8d.png)

Readings
Korf, 1997. [Finding Optimal Solutions to Rubik's Cube Using Pattern Databases](https://www.cs.princeton.edu/courses/archive/fall06/cos402/papers/korfrubik.pdf).
[God's Number is 26 in the Quarter-Turn Metric](http://www.cube20.org/qtm/).

# Introduction

![Intro](/assets/images/计算机科学/118382-04dcbd9a71cbdbcf.png)
* Problem-solving: the theory, and technology of building agents to plan ahead to solve problems
* A problem is unsolvable if there is no goal state.
![Definition of a problem](/assets/images/计算机科学/118382-3f90a80ddf06fe3b.png)

Elements of a problem
* initial state
* given a state, give a list of possible actions in the current state.
* result function: given the state and a selected action, then reach a result (not always new) state.
* goal test function tells the agent if the current state is the goal
* path cost is the cost if an agent taking the given path
* the step cost is the cost of taking an action from on state to reach a new state.

## Example Route Finding

![Route finding problem](/assets/images/计算机科学/118382-e0a7422a6199e7cd.png)
* Here we have 3 regions in the problem world: Frontier, explored and unexplored. the frontier is the states in the green region, they are the end state of the current path. Explored states are the states on the search path explored. The unexplored states are all the states in the search space which are not part of the searched pages yet.
* __Step costs__ are distances between cities and path cost is the sum of the step costs of all the steps on the path

# Tree Search

![Tree search algorithm](/assets/images/计算机科学/118382-c2a3126eee276472.png)
* Tree search is a set of algorithms: There are multiple ways to choose the frontier  

## Breadth-First Search
* with the Breadth-First search, the algorithm always choose to explore __the shortest path__. In the example above, Arad goes to Zerind, Sibiu and Timisoara are the three shortest paths ( short in terms of depth, not distance or cost).
* Quiz: Given Tree search, we are going to explore sibiu's next step, which city will be explored?

![the next fronts from "sibiu"](/assets/images/计算机科学/118382-b5af1ec53c0dadac.png)
* Answer: Rimic Vilcea, Fagaras, Oradea and __Arad__
* Note: tree search will not know if the search resulted in a back-track path. (Thus Arad was explored again).

![Back-track path in Tree search](/assets/images/计算机科学/118382-1f15926a1950fe58.png)
* So we need to track the "explored region" and the frontier region of the tree. By comparing the states in the frontier and the explored region and removing the states that are in both the region so that they won't be visited again to avoid repeated search, that's what Graph Search will be doing.

# Graph Search

![avoid repeated search](/assets/images/计算机科学/118382-8cc761178fd8dae9.png)

![Quize: frontier to add if we visit Zerind](/assets/images/计算机科学/118382-6a7211bfa08097ff.png)
* Question, given the current state (Zerind) and paths in the frontier, which states should be explored next?
* answer: nothing to add since Orada is already in the frontier and the path won't go back in a graph search algorithm because of the bread-first search


![Quiz: what' the next state and is the problem solved?](/assets/images/计算机科学/118382-bd899857115c2dd9.png)
* the next state is the target city Bucharest
* No, the problem is not solved, even the agent reached the target state.
* the search won't stop when we add the goal state to the frontier
* because the problem is not just to reach the target goal, but to meet the goal with the shortest path.
* in this case, the upper path has shortest steps, but the cost might not the smallest. To determine it, we have to keep expending the frontier. Only when a path expending out the goal state first, we can say the path it is under is the shortest in terms of __the total cost__.

# Uniform Cost Search (AKA cheapest-first search)

![Which path to choose?](/assets/images/计算机科学/118382-cfa8d96658dc7a3e.png)
* given Uniform Cost Search, the agent chooses the path with the __cheapest__ cost first, thus, the Zerind path is chosen first.
* after this, the cheapest path becomes Arad->Timisoara

![which to expand to next?](/assets/images/计算机科学/118382-3f6bc3548beac2f0.png)
* after each expansion of the frontier, the length of each available path will be evaluated and the cheapest path will be chosen to expand, until the goal state is reached.

![Expand the cheapest path](/assets/images/计算机科学/118382-ba700b96e0f462d8.png)

![expand rimnicu Vilcea](/assets/images/计算机科学/118382-a24fbadc419a03ef.png)

![Expean Eugoj to Mehadia, and then Fagars to Bucharest](/assets/images/计算机科学/118382-61032fd4788cb088.png)
* The search won't stop when it reaches the goal state. why? because the path reaches the goal the first because the path before it reaches the node before goal was the shortest, but it could travel very long to get to the end.
* The search will stop when it is __moved out__ of the frontier not when it is added to the frontier

![](/assets/images/计算机科学/118382-9cc3a5e05616e252.png)
* the search going and we will find the path with a cost of 418 is the one pop out the goal state from frontier first.
* and this is how the uniform cost search guaranteed the search of the cheapest path

# Search Comparison
Breadth-first V.S. Cheapest-first V.S. Depth-first

![Find the search order and if the algorithm optimal](/assets/images/计算机科学/118382-e9a9143f11a0e94b.png)
* Optimal means the algorithm is guaranteed to find the results 
* for BFS, it is the path to the goal with shortest steps, for CFS, it is the path to go with the smallest cost
* for depth-first search, it is not guaranteed to find goal because the goal might not even be selected if it is not on the path of the longest depth.

![Is all the search algorithms are complete?](/assets/images/计算机科学/118382-a87f0830913a6df4.png)
# Complete means if the search tree or graph is infinite, the search algorithm can still manage to find the end goal.
* Breadth-first and cheapest-first are complete
* Depth-first is not complete given infinite steps of the tree if the goal is not on its search path.
* But the depth-first tree saves search space ( uses less memory).

> Clarification on cheapest first search:
>
> Consider an infinite path whose costs are as follows: 1 + 1/2 + 1/4 + 1/8 + 1/16 + 1/32 + ... The infinite sum of this series in the limit is 2. If the shortest path to the goal node has a cost greater than 2, the cheapest first search will be incomplete.


# More On Uniform Cost

Uniform Cost will cost a lot of time when the search space is large.
* Greedy best-first search can use smaller steps to reach the goal
* but when there are obstacles on the way, the greedy best-first search will spend more time to find the goal
* solution: combine Uniform Cost with Greedy Best-First search, that is A<sup>*</sup> search

## Greedy best-first search
![Greedy best-first search](/assets/images/计算机科学/118382-2ccd4b7e715b3a9b.png)
* It needs some new knowledge, e.g. use the straight-line distance between the current state to the goal to guide the search direction. it means to expand the node with the shortest distance to the goal first. but it will not be guaranteed to find the shortest path when there are obstacles ( see the graph below). 
* But there is a solution the combine the best of Uniform cost search and greedy best-first search. It is the A<sup>*</sup> ( A-star) search. 

![Greedy best-first search with obstacles](/assets/images/计算机科学/118382-d6f27d87a0cc4c9f.png)

# A<sup>*</sup> Search

![formula](/assets/images/计算机科学/118382-7863524c8c231eb4.png)

![example](/assets/images/计算机科学/118382-75540e3423269240.png)

* In A<sup>*</sup> Search, we need to minimize _g_ and _h_ functions at the same time so that we will have the cheapest the path and also focus on reaching the goal.

![Quiz: which path should we choose to explore next](/assets/images/计算机科学/118382-0fd51e53d1655e10.png)
* here, _g_ is the cost, _h_ is the estimated the strait-line distance between each city to the goal.
* A* chooses the smallest _g + h_ as the path to explore
* for the paths, see figures below

![keep spending with A*](/assets/images/计算机科学/118382-72bdd9f63214641e.png)

![expanding...](/assets/images/计算机科学/118382-6b877a687472c1ec.png)

![The algorithm does not stop when the agent add the goal state into the frontier](/assets/images/计算机科学/118382-bd5da14ba8472714.png)

![A* finds the optimal paths](/assets/images/计算机科学/118382-66b3f6b5c3e938c0.png)

![Will A* always find the optimal?](/assets/images/计算机科学/118382-e20a7451001a4c53.png)
1. The algorithm does not stop when the agent adds the goal state into the frontier, it only finds the shortest path when the goal state was popped out of the frontier.
2. A* finds the optimal paths
Will A* always find the optimal?
* No. In the example above, h always shortens as g increases
* what if reaching the goal requires both _g_ and _h_ increases?

![Conditions h should meet](/assets/images/计算机科学/118382-0aa396158b7578fc.png)

## Optimistic Heuristic

![](/assets/images/计算机科学/118382-aff576ca0e4900c2.png)
* f(p) < f of other paths since it reached G the first
* h(s) < true cost of S-> G, for the next step, f(s) =g(p)+g(s) -h(s) > f(g), so p will pop the G state out of the frontier, thus ends the search with the path _p_. (the argument is for tree search)

# Vacuum world

Quiz: State Spaces

![How many states are in the space?](/assets/images/计算机科学/118382-aa57928cead7f97d.png)

How many states are in the space?
* robot position = 2,  cleaness of the position (clean/dirty) 2<sup>2</sup>
* 2 x 2<sup>2</sup> = 8

![all the states and connections between states](/assets/images/计算机科学/118382-ba74bb69a9c46d7f.png)

![state space 2](/assets/images/计算机科学/118382-3bf8977e7d4c0043.png)
* 3 x 2 x 5 x 10 x 2<sup>10</sup> =307200 
* ( here the robot can be in the 10 positions. the 10 positions can have dirt or not (2<sup>10</sup>).

## Sliding Blocks Puzzle

![Sliding Blocks](/assets/images/计算机科学/118382-9dcd9823d68c6d2b.png)

Which function is admissible?
(what is admissible?)

Assume that a move in this game is moving a single block into the empty space (and cannot be a shift of multiple blocks).
* _h1_ is admissible: each tile in the wrong position must be moved at least once to be in the correct position. it never overestimates
* _h2_ is admissible: each tile in the wrong position can not move more than 1 blocks 
* _h2_ >= _h1_

Can the AI come up heuristic functions by itself?

![Generate h function be relaxing constrains](/assets/images/计算机科学/118382-5f489d5c3032cc4c.png)
* Where the heuristics can come from?
* loosen the restriction of the problem can generate heuristic
* relaxing restriction equals to adding operators in the problem and make the problem easier but never overestimates, thus, is admissible.

![Search only works when:](/assets/images/计算机科学/118382-615fa2dd6c10ae04.png)


![implementing Search](/assets/images/计算机科学/118382-545a442fb4ac2835.png)
* path is linked nodes by parent pointer.
* Notes can be dealt with data structure Frontier and Explored list
* Frontier: moving best items and add items in the queue; membership check
* Explored list: add new members and membership check. simple set: table or hash table

# Readings

* AIMA: Chapters 1-3
* Korf, 1997. [Finding Optimal Solutions to Rubik's Cube Using Pattern Databases](https://www.cs.princeton.edu/courses/archive/fall06/cos402/papers/korfrubik.pdf).
Further Information:
* Goldberg, 2011. [Reach for A∗ : An Efficient Point-to-Point Shortest Path Algorithm](http://www.cc.gatech.edu/~thad/6601-gradAI-fall2015/02-search-01-Astart-ALT-Reach.pdf) (slides).
* Goldberg & Harrelson, March 2003. [Computing the Shortest Path: A∗ Search Meets Graph Theory](http://www.cc.gatech.edu/~thad/6601-gradAI-fall2015/02-search-Goldberg03tr.pdf).
* Gutman, 2004. [Reach-based Routing: A New Approach to Shortest Path Algorithms Optimized for Road Networks](http://www.cc.gatech.edu/~thad/6601-gradAI-fall2015/02-search-Gutman04siam.pdf).

# Challenge Question Revisited

![challenge question](/assets/images/计算机科学/118382-1fcab3ec6df0614e.png)
* avoid repeatedly visiting explored notes
* tri-directional search or A* search need to identify an admissible h function

# Peter's Take On AI

Definition of AI: program computer to do the right thing when you don't know that the right thing is.


```
20170907 first try, stopped at "sliding block" 150 min
20170908 finished the rest 
```
