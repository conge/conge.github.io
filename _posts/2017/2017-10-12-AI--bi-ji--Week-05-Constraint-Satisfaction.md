---
layout: post
title: "AI 笔记 Week 05 Constraint Satisfaction"
date: "2017-10-12 02:23:52"
categories: 计算机科学
excerpt: "This week: watch Lesson 4, Constraint Satisfaction, and read Chapter 6 i..."
auth: conge
---
* content
{:toc}

> This week: watch **Lesson 4**, [Constraint Satisfaction](https://classroom.udacity.com/courses/ud954/lessons/6227538598/concepts/66437293300923), and read **Chapter 6** in *AIMA* (Russell & Norvig).
> **Assignment 2: Tridirectional Search**
**Due: September 24! Here is the [GitHub repo](https://github.gatech.edu/omscs6601/assignment_2).  

# I need to read the book to understand this chapter.
----

![Constrint Satisfaction Problem](/assets/images/计算机科学/118382-ae367dacbb59087a.png)

# challenge question

![Quiz: GSP Challenge Question](/assets/images/计算机科学/118382-4e010568574aca49.png)
* use the techniques mentioned in the quiz to solve a problem like this

# Map Coloring problem

* question: color the map with a minimum number of colors while no states adjacent will be colored the same.

![map](/assets/images/计算机科学/118382-541a4c9ae2fbdbdc.png)

The map-coloring problem has the following components:
1. Variables
2. Domains
3. Constraints: or rules to specify the problem.

* Unary constraints concerns only one variable. 
* The problem can be illustrated by a Constraint Graph if the constraints are binary.

# Constraint Graph

![Map coloring](/assets/images/计算机科学/118382-6d256ced0eff2c11.png)
1. Nodes are variables
2. Arc (Edges) represents constraints.

![quiz](/assets/images/计算机科学/118382-30fce52cad8b29a8.png)

![quize: my answer](/assets/images/计算机科学/118382-8c7baad2ee541a59.png)

There are multiple solutions to the quiz. But all the solutions must follow the rules (satisfy the constraints).

* Constraints can be multi-nary and soft constraints.

# Constraint Hypergraph for the challenge question

![image.png](/assets/images/计算机科学/118382-dd49c7d1be05e569.png)

# Backtracking Search

![psuedo code](/assets/images/计算机科学/118382-6b961570778c0ec6.png)


![Example](/assets/images/计算机科学/118382-36053ccb91c0812b.png)

* backtrack search is like depth-first search, it goes deeper and deeper until it reaches a "dead-end"
* In case of dead-end, the algorithm backtrack up to the upper division to try another branch.
* repeat these steps until the solution is reached.

There are ways to improve the search efficiency

1. choose the least constraining value for each step
2. choose the variable with the fewest legal values

![Least constraining value](/assets/images/计算机科学/118382-9041071e2c6277f2.png)
* in the image above, in the branching step, which area should we choose to color? Least constrain value will choose the right-upper corner because it has more color to choose from. if we choose orange again, we will leave green to be unused (or lest constrained).  

![Minimum remaining values](/assets/images/计算机科学/118382-ad1b411895ae0049.png)
[Minimum remaining values]: or we can choose the middle-lower region because it has the least color to choose from.
![Degree Heuristic](/assets/images/计算机科学/118382-051f287092d80770.png)
When there is a tie, a heuristic could be used to select the next step/ area to explore.

# quiz
![quiz](/assets/images/计算机科学/118382-ad1fd03f5378f1a5.png)

* we can use minimal remain values to choose the region adjacent to the red and blue blocks because this will make it region only have 2 colors to choose from (minimum remaining values)
* Or we can choose the one on the top if it since it only has one color to choose from (least constraining values) since it only have Green to use.


# forward checking
* we can also use forward checking as a warning system for dead-end branches

![forward checking](/assets/images/计算机科学/118382-8a2aa0e5c5ae7421.png)
* forward checking keeps track of the available domain for each variable in each step
* a dead-end is reached when there is no domain for an unresolved variable.


![Arc Consistency](/assets/images/计算机科学/118382-72f192f664951abc.png)

* Arc Consistency: all the variables have at least a value in the possible domain.
* Neighbors should not have the same color, thus a selection of a color can have a chain effect on the domain for variables.
* when we find a region has no value available to assign, return 'Failure' to the problem.

![quiz](/assets/images/计算机科学/118382-6af2326e48982e8f.png)
__Question__: select all the possible values for each region and indicate whether the entire network arc consistent or not.

# Structured CSPs

![Structured CSPs](/assets/images/计算机科学/118382-30ff0d86a3c4d7bb.png)


![Conditioned CSP as tree](/assets/images/计算机科学/118382-5cff0db0515bd9af.png)
* How fast the algorithm will be?

# Iterative Algorithms
![Iterative Algorithms](/assets/images/计算机科学/118382-c2532c50dc4d0a86.png)

*  Iterative Algorithms works very well then the solutions are plenty or very few.
* the problem becomes hard to solve when the ratio of constraints and solutions reaches a critical ratio 


![](/assets/images/计算机科学/118382-c95f36421c6340a1.png)

# the challenge question

![challenge question](/assets/images/计算机科学/118382-2c446f6693ca4375.png)

can be resolved by forward-checking: checking the available domains for values.

#s Readings

AIMA: Chapter 6
