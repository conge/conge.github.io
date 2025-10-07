---
layout: post
title: "8803 RL Fall 2015 期末复习笔记精简版"
date: "2015-12-09 00:33:05"
categories: 计算机科学
excerpt: "简介： 这是在复习Reinforcement Learning的期末考的时候做的复习笔记。基本内容就是平时的课堂笔记（参见2015秋季学期笔记 ..."
auth: conge
---
* content
{:toc}

## 简介：

这是在复习Reinforcement Learning的期末考的时候做的复习笔记。基本内容就是平时的课堂笔记（参见[2015秋季学期笔记 8803 RL and 6440 HIT](http://www.jianshu.com/p/9985a7b4067c)）的精简版本，涵盖每一张的基本知识点，方便在短时间内快速回顾。

这个笔记的顺序是从后向前，这是我当时的复习顺序，这里就不重新树立了。因为时间关系，我也没有能完成对全部笔记的精简，对于没有的部分，也不打算补充了。

这个学期结束，是时候放松一下，读一些书，投一些简历，然后为下一学期做准备了。

## Coordinating, communicating and coaching

### Decentralized POMDP

* Shared Reward
* multiple independent agent
* Optimal solution balance the benefit communicating and cost of not communicating
* example: finding each other in a museum

### Inverse RL

* Agents generate reward function after experiencing the world and a set of behaviors
* MLIRL: Maximum likelihood IRL (dynamic reward shaping??)

### Policy shaping: 
* Human commentary on Agent's action.
* Human might not be always correct.
* The knowledge about the world comes from multiple sources (e.g. human and agent)
* combining info by calculating the probability that all the sources agree (multiplying the values)
	
### Ways that machine can learn from human

* Demonstrations: IRL
* Reward shaping:
* Policy shaping:
* An example Drama Management: treating story as MDP
	* Target Trajectory Distribution-MDPs
	* Trajectories are states, actions are story actions; Model is the probability of given action (a) and trajectory (t) and ending at new trajectory (t'), P(t'|a,t).
	* optimal policy is the policy that will lead to the TTD

----

## Game Theory I

* Game theory is mathematics of conflict of interests, and it generalizes the RL to multiple agents.
* Pure strategy V.S. Mixed strategy.
* MinMax and Maximin: all agents tries to maximize their own reward. minMax have one same result.
	* In 2-player, zero-sum deterministic game of perfect information: minMax ≡ MaxiMin and there is always a optimal pure strategy;
	* In 2-player, zero-sum __non__-deterministic game of perfect information: minMax ≡ MaxiMin and there is always a optimal pure strategy (the same as above);
	* In 2-player, zero-sum non-deterministic game of __hidden__ information (mini-pocket game): minmax ≠ Maximin and there will be no optimal pure strategy; e.g.  there will be mixed strategy (intersect of strategy lines).
	* In 2-player, __non__-zero-sum non-deterministic game of hidden information (Prisons' Dilemma): both prisoners will always defect ( in a Nash equilibrium)
* Nash Equilibrium
	* in the n-player pure strategy game, if elimination of strictly dominated strategies eliminates all but one combination, that combination is the unique NE.
	* Any N.E. will survive elimination of strictly dominated strategies
	* if n is finite, for each set of finite strategies, then there will be at least one strategy is N.E.
	* if agents are in a Nash Equilibrium, any agent will have no good reason to change strategy ( pure or mixed)
	
## Game Theory II

* Iterated Prisoner's Dilemma (IPD), 
	* when the last a few games are known, Prisoners will always defect.
	* when the last a few games are unknown (with probability of γ that the same will continue), it opens door for cooperation.	In this case, using TfT, IPD will reach new NE, which is always being cooperative.
* Tit For Tat: the first round Cooperate, then copy opponent's previous move.
* Folk Theorem describes the set of payoffs that can result from Nash strategies in repeated games.
	* Feasible payoff are average payoff of some joint strategies.
	* acceptable payoff are average payoff of joint strategies better than minMax profile. MinMax profile or security level profile are pair of payoffs that represent the payoffs that can be achieved by a player defending itself from a malicious adversary.
	* Folk Theorem: any feasible payoff profile that strictly dominates the minimax profile can be realized as a Nash equilibrium payoff profile, with sufficiently large discount factor.
	* Proof: the minimax profile can be used as threat.
	* but threat is not always plausible when it is not subgame perfect.
	* Subgame perfect: it is stable if taking test response independently
	* Pavlov V.S Pavlov is NE and subgame perfect. TfT V.S. TfT is NE but not subgame perfect
* Computational Folk Theorem: can build Pavlov -like machines for any game and construct sublime perfect NE for any game in polynomial time.

### Is Stochastic games solvable (solved)?

* Stochastic Games is generalization of both MDP and single agent RL. MDP:RL :: Stochastic game:multi agent RL
* Restrict some parameters of SG, will get MDP (make only one agent matter), Zero sum stochastic game (set rewards to be adding up to a constant) and repeated games (|S|=1).
* Zero sum stochastic games can by solved by using Minimax in a Bellman-like equation. VI works for the situation, minimax-Q converges, and Q* is unique, policies can be computed.
* General-Sum Games are not solved currently but we have hope
	* repeated stochastic games
	* cheap talk --> correlated equilibria
	* cognitive hierarchy -> best responses
	* Side payments (CoCo values) 
	
## Game Theory III

* Correlated equilibrium and the chicken game: 
	* Chicken game has 2 NE, CD or DC. But the 2 NE is not stable. The mixed strategy gives an expected payoff of 14/3
	* introducing a middle man who sees the cards and tell agents what to do. the agents will get a new NE which is aways listening to the middle man. This new NE is called correlated equilibrium。 CE will get payoff of 15/3 which is better than 14/3.
	* CE can be found in poly time；all mixed Nash are correlated；all convex combination of mixed Nash are correlated
* Cooperative-Competitive Values
	* coco(U,Ubar) =MaxMax((U +Ubar)/2) + MinMax((U-Ubar)/2); P =coco(u,Ubar)-U(a\*,a\*bar)
	* coco decompose game into some of two games. it has unique solution, can be extended to stochastic games, but not necessarily equilibrium and does not generate to n > 2.
* Mechanism Design: based on wanted behavior to build/make a game.
	* Peer teaching: student +1 when get one question correct. teacher +1 when student makes mistake on easy question and get correct on hard question.
	* Baby devision: asks A B, if both yes, A pays a small fine but B announces a V, ask again, if A say yes, A keep baby and pay V, and if A says no, B keeps baby and pay V. Assumption, baby worth more to real mom and less to fake mom.
	
----

## Options

### Temporal Abstraction and options

* Temporal Abstraction is representing many actions with one or a few options
	* Option = <I, π, β>. I is __I__nitiation set of states, β is termination set of states and probability of ending at state s. π is policy
	* Bellman-like equations can be written using o to replace a and F(s,o,s') to replace T(s,a,s') and discount factor is hidden.
	* using option changes MPD to Semi-MDP
	* example: the Pac-Man problem
	* Options have computational benefits. If done right, it can also decrease state space.

### Goal Abstraction and Modular RL

* Options give ways to think actions as accomplishing parallel goals.
* Modular RL sees options as sub-agents with different goals.
* But only one goal can be active at a given time. To choose a goal, one can choose 
	* greatest mass Q-learning(summing up all the Q of each action and excuse the option with largest Q), 
	* Top Q-learning (choose the action with highest Q, doesn't work for multiple action with the highest Q)
	* negotiated W-learning: Minimizing loss.

### Monte Carlo Tree Search

* Procedure: Select, expand, Simulate, back up and repeat.
	* Select actions based on policy π, for all known states
	* when reach unknown states, simulate actions and sample. Based on the simulation, calculate value of unknown state and backup and expend π. and then repeat.
* Trade-off is between number of state and how deep to search.
* the MCTS can be seen as policy search. When reach a state we are not confident, a inner loop is executed to do some RL.

----

## Partially Observable MDPs

* in POMDP, MDP is not directly observable, agent can only observe states. Z is observables, O is the probability of agent in S when sees Z.
* We can estimate states the agent are in using believe states which turns MDP in to belief MDP <b, a, z, b'>.

### VI in POMDP

* Vt(b) can be represented by the maximum of a set of linear functions of b and α. α is a finite set of vectors. this is called piecewise linear and convex.
* Some linear functions are purgeable if it does not contribute to the max
* two types of RL: model based and model free. but both need to interact with the MDP.
* Expectation Maximization is a procedure to learn the hidden property in POMDP.

### Bayesian RL

* take action to figure out which MDP we are in.
* RL requires exploring and exploiting, which is like MDP.
* Piecewise polynomial and convex

### Predictive State representation

* We can do test to get predictions of states
* But belief states and PSR does not have a one-on-one mapping
* Any n-state POMDP can be represented by a PSR with no more than n tests, each  of which is no longer than n steps.
* Using PSR to do some test can help us figure out what state we might be in and learning PSR sometimes is easier than learning a POMDP. and we need no more than n tests.

----

## Generalization

* some problem have Zillions of states, Learning all of them are not practical.
* Solution:  use features to represent states 
* Method: applying supervised learning method 
* Generalization can happen on three levels
	* value function (which maps state/actions to expected return)
	* Policy (which maps state-action)
	* Model (which maps transition and reward)
* value function approximation
	* Q value for an action is represented by features and a set of weight
* success stories: averager, TD gammon, Atari
* failed stories: Baird's counter
* Linear approximation need not work

```
2015-12-06 初稿
2015-12-08 发布
```
