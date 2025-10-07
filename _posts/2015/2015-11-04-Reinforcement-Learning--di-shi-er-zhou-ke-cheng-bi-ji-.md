---
layout: post
title: "Reinforcement Learning 第十二周课程笔记"
date: "2015-11-04 11:01:52"
categories: 计算机科学
excerpt: "This week watch Game Theory. The readings are Littman (1994), Littman an..."
auth: conge
---
* content
{:toc}

This week
*  watch *Game Theory.* 
* The readings are *Littman (1994), Littman and Stone (2003),* *Greenwald and Hall (2003)*, *Munoz de Cote *and *Littman (2008).*
* Assignment 10 is up.

![Game Theory III](/assets/images/计算机科学/118382-9b254b5b7180567a.png)

![Definition of Game Theory](/assets/images/计算机科学/118382-8179a16827ff6419.png)

* Game theory is mathematics of conflict of interests.
* It generalizes the RL from single agent to multiple agents. 
* It is of the interest of economics, politics, sociology or even biology since these fields often deal with agents with many many agents with conflicts of interests.

## Example
![Quiz 1: simple game example](/assets/images/计算机科学/118382-c525e118b091d2fa.png)

* The example game is represented as a tree, nodes are states, edges are transitions and leafs are rewards.
* the example game has 2 agent  (_a_ and _b_), all the rewards added up to be a constant ( zero-sum), no stochastic transitions. The leafs show the reward that agent _a_ can get and _b_ gets (-1 \* reward).
* Strategies: what action should the agent take at each state it could be in. (equivalent to policy in RL)
* __The agents are assumed to be rational__.

![Quiz 2: Represent the tree using a matix](/assets/images/计算机科学/118382-bc72bd67a07404a9.png)
* this is a simple example of 2-agent zero-sum game
  - zero-sum means the reward of A and B will sum to 0 for any strategy.
* A matrix is enough to represent a game.
* once the matrix is here, the tree doesn't matter now.
* need to learn to generate the matrix from the tree.

### Minimax

![MiniMax](/assets/images/计算机科学/118382-f09694462ec01c5d.png)

* A and B has the same goal, maximize their own reward ( and minimize others reward).
* If A and B behave rationally, they will reach the same strategy.

![Von Neumann theorem](/assets/images/计算机科学/118382-988f9efa92a72c7f.png)

This is important so I am writing it down:

* In a 2-agent, zero-sum, deterministic game of perfect information, Minimax ≡ Maximin, 
* and there always exist an __optimal pure strategy__ for each agent.
* Based on the strategy matrix, one can always build at least one tree.

Now, to make the problem a bit more complex, we change the game to be non-deterministic:

![quiz 3: strategy matrix for non-deterministic game](/assets/images/计算机科学/118382-50c6fbb3c28d9c12.png)

* Introduce the __chance box__, so that transition is non-deterministic.
* construct the strategy matrix based on tree ( but could not reconstruct tree based on matrix)
  * note: from the matrix, we don't know if the tree is deterministic or not.
* the minimax theorem (Von Neumann theorem) still holds
  * Minimax ≡ Maximin
  * Optimal pure strategy exists.

### Minipoker

![Mini-Poker: description](/assets/images/计算机科学/118382-9cd1c457cf0b0b85.png)

![Mini-Poker: Tree and Matrix](/assets/images/计算机科学/118382-5f3f27c2ca021e58.png)

* In the minipoker game, b will not know all the information, so it's a 2-agent, zero-sum, non-deterministic game of __hidden__ information
* In this case, Minimax ≠ Maximin and there will be no optimal pure strategy.
* but there will be mixed Strategy, which is a distribution of strategies.

### Mixed Strategy

![Quiz 5: Given B's strategy, we can figure out A's expected profit](/assets/images/计算机科学/118382-0bc6ece04f4063ec.png)

* A's expected strategy are linear equation, which can be represented by lines.

![Quiz 6: A's expected value is dependent on B](/assets/images/计算机科学/118382-f9aff2e241589354.png)

* the mixed strategy should be at the intercept of the two lines in this case.
* if the two lines both have positive slope, the mixed strategy should be at the far right; if negative slope, the strategy should be at the far left.
* the expected value of the game is deterministic still.
* although the strategy is mixed, there is still an expected value, in this case, the expected value is when p is 0.4, and value is __1__.

### Snitch

![Prisonders' Dilemma](/assets/images/计算机科学/118382-0e0fe0d8c2a33ba9.png)

* Now, we are making the game non-zero-sum.
* The prisoner's dilemma is a 2-agent, __non-zero-sum__, non-deterministic game of __hidden__ information
* Assume the agents are rational, both of them should defect.

## A Beautiful Equilibrium

![Nash Equilibrium](/assets/images/计算机科学/118382-c64a9d2c87418480.png)

* in practice, if we are in a Nash Equilibrium, any agent will have no good reason to change strategy ( pure or mixed).

![Theorem](/assets/images/计算机科学/118382-366db8dc4353b059.png)

* in the n-player pure strategy game, if elimination of strictly dominated strategies eliminates all but one combination, that combination is the unique NE.
* Any N.E. will survive elimination of strictly dominated strategies
* if n is finite, for each set of finite strategies, then there will be at least one strategy is N.E.

![Play the game multiple times: won't change NE](/assets/images/计算机科学/118382-4aa471fa4c640944.png)

* what if playing the game multiple times?
* only the last game matters-> the last game will be N.E -> since the last game is known now, the last game moves to the game before it.-> the last game will be N.E. -> repeat.... ->all the game should will be N.E.

## Recap

![Recap](/assets/images/计算机科学/118382-fe3248dded8f62ec.png)

[Andrew Moore's slides on Zero-Sum Games](http://www.autonlab.org/tutorials/gametheory.html)
[Andrew Moore's slides on Non-Zero-Sum Games](http://www.autonlab.org/tutorials/nonzerosum.html)
```
2015-11-03 初稿
2016-04-26 复习并添加部分内容
```
