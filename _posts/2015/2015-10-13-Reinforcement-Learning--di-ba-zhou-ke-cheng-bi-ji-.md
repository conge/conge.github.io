---
layout: post
title: "Reinforcement Learning 第八周课程笔记"
date: "2015-10-13 11:01:08"
categories: 计算机科学
excerpt: "This week Watch Exploration. The readings were *Fong (1995) *and Li, Lit..."
auth: conge
---
* content
{:toc}

This week  
*  Watch *Exploration*. 
* The readings were *Fong (1995) *and *Li, Littman, Walsh (2008).*

![Exploration: Specific to RL ](/assets/images/计算机科学/118382-cc685f5f28f0c812.png)

![Sub topics of Exploration](/assets/images/计算机科学/118382-2a07bcc776fb8522.png)

|Type  | state transition | Stochastic | solution|
|--  |--  |-- |-- |
|Bandits|✘ | ✔ | hoeffding bound to do stochastic decision making|
|Deterministic MDPs: |✔ |✘ |Rmax to do sequential decision making|
|Stochastic MDPs|✔ |✔ |both hoeffding bound and Rmax|

## K-armed Bandit Problem

* Each slot has a probability to get certain payoff or no payoff
* Payoff or the associated probabilities are unknown.
* what's the best thing to do? **Exploration**.

## Confidence based exploration 

!Quiz 1: K-Armed Bandits, given the observed data, which arm gives the ightest expected payoff and which arm are most comfident](/assets/images/计算机科学/118382-6578df35f8c00073.png)

* arm d gives 1 pay off in the smallest number of try
* arm g gives most reliable output since it's been pulled the most and gives a good payoff.

![Confidence-based Exploration](/assets/images/计算机科学/118382-6d78c0df33788cb4.png)

* Maximum Likelihood: ① Given current info, figure out the best expected action based on best likelihood -> ② act, and get new info -> repeat ① ② will always choose b 
* Maximum Confidence: ① Given current info, figure out the best expected action based on best confidence -> ② act, and get new info -> repeat ① ② will also choose b only
* Minimum Confidence: ① Given current info, figure out the best expected action based on smallest confidence -> ② act, and get new info -> repeat ① ② will also choose to alternating between a and b. But it will not favor the better arm.
* __Exploration-exploitation dilemma__: combine maximum maximum likelihood and minimum confidence. The latter allows to try different actions and the former allows us to choose the best reward.

## Metrics for Bandits

![Metrics for Bandits](/assets/images/计算机科学/118382-0803c0a9cf9a2a6c.png)

1. identify optimal arm in the limit: exploration
2. maximize (discounted) expected rewards: exploration ＋ exploitation, but computationaly expensive
    * [Gittins index](https://en.wikipedia.org/wiki/Gittins_index): a real scalar value associated to the state of a stochastic process with a reward function and a probability of termination.
    * Gittins index works well with Bandits, should not generalize to other RL.
3. Maximize expected reward in finite horizon - similar to value iteration
4. Identify near-optimal arms (ε) with high probabilities ( 1- δ) in time τ(k, ε, δ) (polynomial in k, 1/ε, 1/δ) - The __"get there" goal__ is to find near optimal arms. similar to [PAC learning](https://en.wikipedia.org/wiki/Probably_approximately_correct_learning): probably approximately correct.
5. Nearly Maximize reward (ε) with high probabilities ( 1- δ) in time τ'(k, ε, δ) (polynomial in k, 1/ε, 1/δ): the __"how to get there" goal__ is to accumulate as much more rewards as possible in finite time τ'.
6. Pull a non-near optimal arm (ε) no more than τ''(k, ε, δ) times with high probabilities ( 1- δ): The __"control error" goal__ is to minimize mistakes.

## Find Best Implies Few Mistakes

![Find Best Implies Few Mistakes](/assets/images/计算机科学/118382-5aa7c24743690dc5.png)

* τ' is the total number of mistakes when we find ε' close arm 
* τ' is bounded to τ.

## Few Mistakes Implies Do Well

![Few Mistakes Implies Do Well](/assets/images/计算机科学/118382-4ae23f39551df6b2.png)

* is it true that the smaller the _m_ is, the smaller the _n_ is? not always.
* but it is true that the smaller the _m_ is, the small the _n_ could be.
* "Do well" means algorithm C can lead to ε' close to optimal arm where ε' < ε.

## Do Well Implies Find Best
![Do Well Implies Find Best](/assets/images/计算机科学/118382-35d051f87aeecd1e.png)

![Putting it together](/assets/images/计算机科学/118382-bcfd6dfd62f191bf.png)

* Given algorithm of one goal, we can derive algorithms to reach the other two.
* So there is no need to pick one.
* need to know that the three goals are not always solvable (so you might have to pick one?).

## Hoeffding

![Hoeffding bounds](/assets/images/计算机科学/118382-2def5eb63bf51061.png)

* 0 <= δ <=1. The more confident we are the smaller the δ -> the larger the Z<sub>δ</sub> -> the larger the confidence interval
* the larger the _n_ is, the smaller the confidence interval

## Combining Arm Info

![Combining Arm Info](/assets/images/计算机科学/118382-dcb0bdc2c48298e0.png)

* the length of the bar, ε, is the confidence interval of μ<sub>k</sub>.

## How Many Samples?

![quiz 2](/assets/images/计算机科学/118382-9fc0b5d222933312.png)

* C depends more on ε and less on δ (δ is in _ln_)
* PAC-style bounds for bandits.

## Exploring Deterministic MDPs

![MDP optimization Criteria](/assets/images/计算机科学/118382-b5d196bdd7e3bad9.png)

* in MDP, we can only choose action but not state
* we can treat action selection as bandit problem (e.g. _k_ action is a _k_ arm bandit).


![Exploring MDP](/assets/images/计算机科学/118382-6f43b8cc91674522.png)

* __Rmax__: assume any state we have not full explored  (unknown state-action pair) has a self-loop of reward Rmax.
* This way, the learner is encouraged to explore the whole MDP.

## Rmax Analysis

![Rmax Analyis](/assets/images/计算机科学/118382-d08d9ab4e8bc5d29.png)

* the example: even with Rmax, there is a possibility that the learning stops visiting unknown states
* discount factor is important to determine if the agent is going to explore unknown edge.

![Lower bound using a special kind of MDP: sequential combination lock](/assets/images/计算机科学/118382-ac865f9b41abceb0.png)

* We have a upper bound saying the algorithm can solve the problem with n<sup>2</sup>k steps
* now we are proving that no other algorithms can take less than n<sup>2</sup>k steps
* The sequential combination lock has _n_ states, in each state the learner can take _k_ actions.
* at _i_ th state, one action can send the learner to next state (_i + 1_), all other actions will take the learner to state 0, to get back to state _i_, the learner has to take at least _i_ steps (the worst case deterministic MDP).
* In the worst case, it might take kn<sup>2</sup> steps to solve a deterministic MDP before stopping make mistakes.

## General Rmax
![](/assets/images/计算机科学/118382-9e07aa0a27aa783e.png)

For Stochastic properties, applying hoeffding bound. For sequential deterministic MDP, Rmax can solve the problem.  Now applying both, we can solve the stochastic MDP.

![General Rmax](/assets/images/计算机科学/118382-1c3713b7d5b72723.png)

* For Rmax algorithm, define Unknown s, a pair as: if tried fewer than C times. Then use maximum likelihood estimate.
* the C part is hoeffding bound.

Some key ideas for this to work: Simulation Lemma and Explore-or-Exploit Lemma

### Simulation Lemma

![Simulation Lemma](/assets/images/计算机科学/118382-0b75d0382f17fb58.png)

* if we get an estimated MDP that is close to real MDP, then the optimizing the reward based on the estimate will be very close to the optimal policies for the real MDP.
* α is the difference between __estimated__ and __real__ MDP.
* α could be different if transition possibility and reward are not in the same scale, but we can alway rescale things to that α is between 0 and 1.

![the difference between estimated and real MDP (α) is polynomially related to the error in value of actions (ε)](/assets/images/计算机科学/118382-0b12d8740e47f3b7.png)

* α is related to ε 
* α is used to determine C
* using **Hoeffding bound** and **union bound** to find a big enough C which can estimate an MDP which is close enough to real MDP.

### Explore-or-Exploit Lemma

![Explore-or-Exploit ](/assets/images/计算机科学/118382-2cdf5dabb90f2860.png)


## What Have We Learned?

![Recap](/assets/images/计算机科学/118382-194b003340c3e668.png)

* Hoeffding bound and Union bound let us know how certain we are about the environment
* Rmax makes sure we "visited" things enough to get accurate estimates

```
2015-10-06 初稿 up-to quiz 1
2015-10-07 updated to Exploring Deterministic MDPs
2015-12-04 reviewed and revised
```
