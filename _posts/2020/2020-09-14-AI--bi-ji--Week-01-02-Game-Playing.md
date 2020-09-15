---
layout: post
title: "AI-笔记-Week-01-02-Game-Playing"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

* [Course schedule](https://docs.google.com/document/d/1ZF2w0QQCiZ0RZleryr31m4YMaapff8x0BJqqShCuJnA/pub)
* [syllabus](https://docs.google.com/document/d/1RU6_rKYLb4z8Hy1bHuN819qfFZyEgzqkxPGiz6lsXcg/pub)

# Week01学习内容：

1. [Game Playing](https://www.google.com/url?q=https://classroom.udacity.com/courses/ud954/lessons/4747398595/concepts/64060360780923&sa=D&ust=1503342538913000&usg=AFQjCNHYJDPD0QTO3B-rK6luDLT8UEJgww) through Depth-limited Search; 
2. review/learn Python; play each other in Isolation; 
3. Chapter 1-2; Chapter 5.0-5.2
4. R&N slides on [Game Playing](https://www.google.com/url?q=http://www.cc.gatech.edu/~thad/6601-gradAI-fall2015/chapter06.pdf&sa=D&ust=1503342538914000&usg=AFQjCNFFTOSwnqSjVHOTwC_aEvnXYsk-KA) 

# Week 01 任务清单：
* Introduction on Piazza
* Start-of-Course Survey

> Book used in the class [Artificial Intelligence: A Modern Approach (3rd edition](https://www.google.com/url?q=http://aima.cs.berkeley.edu/&sa=D&ust=1503342538910000&usg=AFQjCNFndl5xgBJahvwyP9-F38C1XedVNg)) by Russell and Norvig (R&N).
 *[下载链接一](https://dcs.abu.edu.ng/staff/abdulrahim-abdulrazaq/courses/cosc208/Artificial%20Intelligence%20A%20Modern%20Approach%20(3rd%20Edition)11111.pdf)*，*[下载链接二](https://raw.githubusercontent.com/tuzz/autonomous_exploration/master/Miscellaneous/References/Artificial%20Intelligence%2C%20A%20Modern%20Approach.pdf)*(expired)

----

# Lesson 1： Game Playing

![Intro](/assets/images/计算机科学/118382-ec137d446092ff54.png)

![Couse outline](/assets/images/计算机科学/118382-94566ab2e5927930.png)

![Goal of the lesson](/assets/images/计算机科学/118382-30f7d1917245de9f.png)

* to build an AI to play the games such as "Isolation" - deterministic games
* apply minimax algorithm to play games and use alpha beta pruning to speed up the minimax algorithm
* with some modification,  "expectimax" algorithm,  we can also build AI's to play games "have an element of chance."

## Challenging Quiz


![Quiz 1: mark the branches of the tree that can be pruned out using probabilistic alpha-beta pruning, i.e., do not need to be explored any further.](/assets/images/计算机科学/118382-ec1e9e5b1c4681ce.png)

## The Isolation Game 

* The game has two players: x and o. The players take turns, with player x moving first at the beginning of each game.
* Player x starts at position (1,1) while o starts at (8,8).
* a player can move like a queen in chess (in any of the eight directions) as long as her path does not cross a square already filled in or occupied ~~by the other~~.
* After moving, the space vacated by the player is designated as filled and cannot be moved to again. Notice that only the space that was occupied is filled, not the entire path.
* The game ends when one player can no longer move, leaving the other player as the winner.

## Building a Game Tree

![game tree](/assets/images/计算机科学/118382-c87f3c68bc59b749.png)
* Game tree illustrates all the possible steps of the "isolation" game.
* by examing the tree, we can identify branches that lead to a "lose" situation and warn the computer player.
* the entire tree is[ here: Isolation game tree with leaf values](https://s3.amazonaws.com/content.udacity-data.com/courses/ud954/images/isolation-L6_leafValues.svg)

## MiniMax

![Open book](/assets/images/计算机科学/118382-107d37570a2e8476.png)
* the win (+1) and lose (-1) leaves indicated the result of each branch of the tree
* The question becomes how to figure out which first-move is the best automatically
* Minimax algorithm: computer player (AI) wanted to maximize the score to win, and opponent wanted to minimize the score to win.
* start at the maximizing level
* to determine wins or losses of a game, we need to Propagating Values Up The Tree.
* the win or lose is determined by who will make a choice at the level and how the win/loss situation is under the node.
* at the max node, choose the max value and at min level, choose the min value.

## quiz

![quiz 2](/assets/images/计算机科学/118382-05f98addb9b25720.png)
* from top-down, the second level (max level), the AI has the move so it can decide which branch to go down. Although there are two branches can lead to loss, the AI can avoid them to go to the right branch which guarantees a win.
* [here is the whole tree with every node marked, download to see](https://s3.amazonaws.com/content.udacity-data.com/courses/ud954/images/isolation-L6_minMax_complete.png)

----

> Optional Reading: Artificial Intelligence - A Modern Approach (AIMA): Chapter 5.1-5.2

> ![Minimax](/assets/images/计算机科学/118382-e31c8f77d6f0d225.png)
> * _s_ is state or note of the game tree
> * the minimax value of the leaf nodes are known
>  * when the node is max, the minimax value of the node is the max of all the values down below
> * when the node is min, the minimax value of the node is the smallest of all its subnodes.
> * the decision of actions at each stage (minimax decision) depends on the minimax algorithm

> The minimax algorithm performs a complete depth-first exploration of the game tree. If the maximum depth of the tree is _m_ and there are _b_ legal moves at each point, then the time complexity of the minimax algorithm is O(b^m). The space complexity is O(bm) for an algorithm that generates all actions at once or O(m) for an algorithm that generates actions one at a time.

> # Multiplayer, non-zero sum games are more complicated
> for each state, its minimax value becomes a vector which contains the value for all the players
> there will be dynamically forming alliances, for example, A and B play against C.
> collaboration can also occur with just two players in a non-zero sum game.

----

# Max Number of Nodes Visited
* on a 5x5 isolation board, the number of possible nodes is bounded to 25!, but it's no big deal. see Quiz below: In the third move, move to which square will result in maximum options for next move?

![Quiz 3](/assets/images/计算机科学/118382-72c9a02aac22594b.png)

* my answer is the middle square. it has eight directions to go in the next move.
* the maximum possible number of moves from the state is 16.

## the branching factor
* the branching factor indicates how many options for each move in the isolation game.

![Quiz 4](/assets/images/计算机科学/118382-756dc2f34b5f3ef1.png)
* I guessed this one and got it right. My rationale:
  * branching factor (b) is roughly the number of possible move options in each level of moves. there are d levels, so the number of nodes that the minimax should visit is about b^d. b*d and d^2 are underestimated. d^b is over estimated.

an average branching factor can be calculated through game simulation.

![average branching factor](/assets/images/计算机科学/118382-31171b99c7fc897a.png)

* the average b = 8. but still, there are 8^25 nodes to visit, which might take millions of year.
 * The goal is, to not let the human player wait for more than 2 seconds.
* Say if the computer can visit 10^9 nodes in a second, so we need 2 seconds. based on this we can calculate the maximum depth of the game.
* 2*10^9 = 8^x; x < 10.3; here, x is the depth of the search.
* this is depth limited search: limit the depth of the search so it can finish within a deadline.

Now the question becomes "at level 9, how can we tell which node is good or bad" based on the level 10 nodes.
* an evaluation function will be needed. one way the evaluation function can be constructed to count the possible moves left for the computer player(count-my-move).

## Quiz

![Quize](/assets/images/计算机科学/118382-a23e70fc50370788.png)

* Solution method: count the possible moves. Max level: select maximum of the lower level nodes; Min level: select the minimum of the lower level nodes

![Quiz: testing the evalutation function with level 3 tree](/assets/images/计算机科学/118382-2b31a1684f268a34.png)

* Click to open: [Isolation Game Tree - Level 3](https://s3.amazonaws.com/content.udacity-data.com/courses/ud954/images/isolation-L3_minMax.svg)
* do the calculation for the whole tree.


![Quize: test evaluation question with level 2 of the tree](/assets/images/计算机科学/118382-df0f22594750eda8.png)
 
The results do not agree with the results of level 3 tree. Which means when to search for level 2 and level 3, the evaluation function will give a different answer.

* It does not mean the evaluation function does not work
* it might mean the search is not deep enough.
* we can go deep to reach the point that when deeper in levels did not change the result.

# A problem
* we try to avoid going deeper because the number of nodes increases exponentially as we go deep.
* **Quiescence search** is an algorithm typically used to evaluate minimax game trees in game-playing computer programs. It is a remedy for the horizon problem faced by AI engines for various games like chess and Go.
* Trick: interactive deepening.

## interactive deepening.
* the problem: return the best answer before time run out (2 seconds).
* Steps: 
  1. search level 1, record the best answer, answer 1.
  2. if time is up, return answer 1, if not, search level 2 and get the best answer.
  3. check time, if time is up, return level 2 answer, if not, deepen the search to next level ...

As we deepen the search, the number of nodes on the tree and the interactive deepening nodes increase

![Quize: Exponential B](/assets/images/计算机科学/118382-006ec22f688c0b08.png)
* when b = 2, n = 2 <sup>(d+1)</sup> - 1
* when b = 3, n = (3 <sup>(d+1)</sup> - 1)/ 2
* when b = k, n = (k <sup>(d+1)</sup> - 1)/ (k -1)

## interactive deepening on Isolation game
1. branching factor of the Isolation game varies
2. at the beginning of the game, branching factor (B) is large, and searching needs more time.
3. at the end of the game B is smaller, and searching is shallow. 
So, we might need to develop strategies to allow the player to take more time at the beginning or the middle of the game, but less time in the end game.

## Horizon Effect

![](/assets/images/计算机科学/118382-2165be77c79a8ba7.png)

In the above situation, it is very easy for a human player to observe that O takes the move next to X will when because it will allow X to have 6 moves but O has seven (because a partition is created). 

But it will take the computer to search 13 levels to figure this out (which we don't have enough time to do).

This is the __horizon effect__.

So we need evaluation functions. to check partition. but it might increase the search time. So good evaluation function need to balance between dealing with horizon effect and simplicity or effectiveness.

![Quiz: Good Evaluation Functions](/assets/images/计算机科学/118382-11558e2986aecdad.png)
* the answer was chosen based on that it is more likely to be positively correlated with the chance of winning
* the new evaluation question can lead to the correct move for this board. Evaluation function should represent a good winning strategy (but it is not always guaranteed).

* my-moves - #opponent_moves might be an even better evaluation question.

## Alpha-Beta Pruning

![](/assets/images/计算机科学/118382-78d637eda04ab925.png)

Alpha-Beta Pruning allows the AI to skip a section of the game tree but still get the same answer of the minimax algorithm. [More efficient than minimax]

It can reduce the search time to b<sup>d/2</sup> ~ b<sup>3d/4</sup>
![image.png](/assets/images/计算机科学/118382-9eae860c1eae4d29.png)


![minimax](/assets/images/计算机科学/118382-76e785ec776835ac.png)



![image.png](/assets/images/计算机科学/118382-02c0104b5818264e.png)

![Alpha-Beta Pruning Quiz 1](/assets/images/计算机科学/118382-38abfa17ade208a8.png)


![Alpha-Beta Pruning Quiz 2](/assets/images/计算机科学/118382-b0a0e34785e95d2c.png)

# Searching Complex Games
Reading AIMA: Chapter 5.3-5.4 [Done, did not track time]

## Solving 5x5 Isolation
Some strategies for the 5x5 game: open game search table; check for reflections to minimize the open game; occupy center; reflex move; minimax and alpha-beta pruning.

## 3-Player Games

![3-Player Games](/assets/images/计算机科学/118382-0915c3f0524efe3f.png)

* minimax doesn't apply for a 3-player game, instead, we evaluate each node based on which players move at each move.
* the end node will be a vector of utility for each player.
* max-N algorithm

![3-Player Games quize](/assets/images/计算机科学/118382-91288babb3963c63.png)

## 3-Player Alpha-Beta Pruning

* Question: can alpha-beta pruning work for 3-player games?
* Answer: as long as the game utility has a lower-bound and individual utility has an upper-bound, then yes.

E.g., shallow pruning and Immediate pruning are possible, but not deep pruning (why?)

![alpha-beta pruning](/assets/images/计算机科学/118382-912cb838a8b654e8.png)

![3 player pruning](/assets/images/计算机科学/118382-d32b990e76e12a89.png)

* from the most left nodes, we get (3,3,3) for move 2 based on player 2's preference
* Thus, player one should have a value which is >= 3.
* in the middle branch, after evaluating the most left node, player 2 will update its value when the value is >=7, and make value for player 1 to be <= 2, but player 1 already had a better solution, then there is no need to look for the other 2 nodes in the middle branch.
* same logic will determine the last node can be pruned.

# Probabilistic games

One type of probabilistic games is that each action might lead to two or more states with a certain probability. Sloppy isolation is an example:

## Sloppy Isolation

![Sloppy Isolation](/assets/images/计算机科学/118382-bb6110de0419e38d.png)


![Sloppy isolation with constrain](/assets/images/计算机科学/118382-c637d137c3373fe3.png)

In this version of isolation, the player might overshoot or undershoot with a 10% chance for each error, and the player will have 80% chance meet the goal.

This can be complicated as the player's moves were limited by available of squares. E.g., sometimes there will be no chance of undershoot or overshoot (see pic above). In this case, the change of hitting the target will be 90%, and the chance of overshoot/undershoot will still be 10%.

## expectedMax
![expectedMax](/assets/images/计算机科学/118382-500e42ed061a133e.png)

When populating the game tree, we need to generate branch and leaves based on a probability of hit or miss the target.

Pruning might still work.

##   


![Expectimax Alpha-Beta Pruning](/assets/images/计算机科学/118382-11075616c0ca08f4.png)

# Further Reading
Peter Norvig and Sebastian Thrun’s lectures on [Game Playing](https://classroom.udacity.com/courses/cs271/lessons/48720299/concepts/482718700923) and [Game Theory](https://classroom.udacity.com/courses/cs271/lessons/48716317/concepts/484037340923).

----

# Games


![Games type and techniques](/assets/images/计算机科学/118382-a57879650dee97e1.png)
* St: stochastic games: MDP is for ST
* PO: partially observable games: POMDP is for partially observable environment
* U: Unknown games: RL deals with Unknown environment
* CL: Computational limitations: A\* search, h functions, and Monte Carlo focus on computational limitations.
* A: Adversaries: there are more than one players play against each other.

![Quize: match games with features](/assets/images/计算机科学/118382-03ba71c5f221a4f5.png)

## Single Player Game

![Single player game](/assets/images/计算机科学/118382-c835eec5451a22b6.png)
* to solve a single player game, the player needs to explore the game tree until finding the goal state, and then backup to find the path to the goal state.
* On the left of the screen, parameters to describe a game are listed. state, player,  action, transition function, utility function, terminal state checker, etc.

## Two Player Game

![Chess as an example](/assets/images/计算机科学/118382-9b7ffb3b2317d749.png)
* Two player adversary games can be solved by MiniMax algorithm while player Max will maximize its utility, and player Min will minimize Max's utility.
* The tree search will go all the way down to the terminal state. Utility function will define the utilities of terminal states. When the search reaches the terminal, the value of the path will back-up to the start state. the player will choose the path based on its utility in each state.

![Function and pseudo code for two player games](/assets/images/计算机科学/118382-254df759013529ea.png)

![Quiz: Time Complexity Question](/assets/images/计算机科学/118382-5d84e8b273cd692b.png)
* b is branching factor, m is the depth of the game tree.

![Space Complexity Question](/assets/images/计算机科学/118382-a6eb0ccee9c761cc.png)
* the space complexity is better than the time complexity.

![Complexity of the Chess game](/assets/images/计算机科学/118382-5bdff31d7b82d641.png)

* given b=30, m= 40, and we can use all the computers in the world, search through the tree of a chess game will take forever.

![Complexity reduction](/assets/images/计算机科学/118382-3d1deabbb915a384.png)
* to deal with complexity problem, we need to try to reduce b, m and the structure of the game representation.

![Queston review of miniMax](/assets/images/计算机科学/118382-c501dcb4ea85eb45.png)
* fill in the utility for each node.

## reduce B

![Pruning](/assets/images/计算机科学/118382-305b09bf1cf24bbd.png)
* the first path in the middle node can define the value of the second node in the min level will be less than 2, which can never be large than 3, so no matter that value of the two terminal nodes will be, the results of the top node will not change. Thus, the player doesn't need to visit the two nodes. Pruning means to ignore some nodes to reduce the branching factor b.


![Qize: which node can be pruned?](/assets/images/计算机科学/118382-865ee176b715e3e5.png)

* the 8 does not need to be visited since the upper node needs to be less than 1 to be updated, which is smaller than the current best answer for the top node.

## Reduce M

![Reduce M](/assets/images/计算机科学/118382-eeb17a60cd14adb3.png)

* Cut off the search at a certain depth. Since we did not reach terminal yet, we can not use utility function. Instead, we can use __evaluation function__.
* Here, the evaluation function will be the keep to win the game. and this method is the Alpha-Beta pruning.
* Alpha-Beta pruning can reduce the game from a O(b<sup>m</sup>) problem to a O(b<sup>m/2</sup>) problem if the tree nodes are ordered perfectly.


![Updating the pseudo code for the value function](/assets/images/计算机科学/118382-a05e6355ebdf8c8d.png)

![Updating the pseudo code for maxValue function](/assets/images/计算机科学/118382-a7a45d88fe1b8a15.png)

![ Horizon Effect](/assets/images/计算机科学/118382-f6621feaef8fdbcc.png)
* Cutting off depth of search can suffer from Horizon Effect
* When in the certain cutting off the depth of search preventing the player to see the real winning path, it can give the wrong answer. Unless the searching depth gets deeper, the player will never reach the node which can decide the winning path.

## Dealing with stochastics 

![Dealing with Stochastic Games](/assets/images/计算机科学/118382-bfed94ad9410618c.png)
* using the expected-value function for the chance node.

![Game tree of example of a Stochastics game](/assets/images/计算机科学/118382-475e909b7cb4d259.png)

![Quiz: fill out the values for each node](/assets/images/计算机科学/118382-92d3fb9e877df6d0.png)

![possible end note of the game if players play rationally](/assets/images/计算机科学/118382-e259bab9f37451a7.png)

* The game could start at the left or the right branch. if starting at 5, player max will choose b, if start at 3, it will choose A...

![Evaluation Function 1](/assets/images/计算机科学/118382-c83df0de5f527ee4.png)

![Evaluation Function 2](/assets/images/计算机科学/118382-2ffd1570c3b5f0f7.png)
* The above two quiz showed how evaluation question can affect the player's choice.

# Conclusion

![components of solution of games](/assets/images/计算机科学/118382-405b5708e84a2250.png)
* Minimax algorithm uses maxValue() and minValue() to find out the value of a state. 
* if the state is the terminal state, then its value is defined by the utility function.
* to reduce the complexity of the problem, we can cut-off the search at a depth level and use Evaluation function to determine the value of the states.
* When a state is stochastic, it's value is determined by a expValue() function.
* alpha and beta will be used for pruning the tree.

Example codes for [Games, or Adversarial Search. (Chapters 6)](http://aima.cs.berkeley.edu/python/games.html)

-----

```
2017-09-10 First draft, took 6 hours
To do: all the readings in the section. Notes of the reading should be done.
