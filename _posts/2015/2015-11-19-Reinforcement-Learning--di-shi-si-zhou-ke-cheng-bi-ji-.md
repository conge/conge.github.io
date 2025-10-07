---
layout: post
title: "Reinforcement Learning 第十四周课程笔记"
date: "2015-11-19 13:12:22"
categories: 计算机科学
excerpt: "This week should watch CCC. The readings are: Zeibart et al. (2008). Bab..."
auth: conge
---
* content
{:toc}

This week 
* should watch CCC. 
* The readings are: *Zeibart et al. (2008)*. *Babes et al. (2011)*. *Griffith et al (2013*). *Cederborg et al (2015)*.* Roberts (2006*).* Bhat (2007).*

![CCC](/assets/images/计算机科学/118382-d9d3c7b8b970a327.png)

![Coordinating and communicating](/assets/images/计算机科学/118382-fa5073a5b18b16b3.png)

![The decentralized partially observable Markov decision process (*Dec*-*POMDP*)](/assets/images/计算机科学/118382-f5be2d492b469d83.png)

* Dec-POMDP has some perspectives of game theory and MDP
* Multiple agent working on getting a common reward. (if the rewards are separated for all the agents, then it's a POSG _partially observable stochastic game_)

![DEC-POMDPs properties ](/assets/images/计算机科学/118382-f8488655296809fa.png)

![DEC-POMDPs example](/assets/images/计算机科学/118382-170934e4e006cc4b.png)

* two agents, they know where they are but don't know the other's position. when the two are in the same room, they win.
* Strategy: go to a shared room. But my knowledge of my current position could be wrong ( partially observable world).

![Communicating and Coaching](/assets/images/计算机科学/118382-ec3c9aeda7b3a039.png)

* agent 1 wants to set up some kind of reward function to move agent to do something (e.g. get the apple for me).

## Inverse Reinforcement Learning

![Inverse Reinforcement Learning](/assets/images/计算机科学/118382-97621fa6b9936be6.png)

* Inverse Reinforcement Learning: the agent experience the environment and a set a behavior and then generate a reward function based on the inputs.

![MLIRL: Maximium Likelyhod inverse reinforcement learning.](/assets/images/计算机科学/118382-36fcd3662d7f418a.png)

![MLIRL result](/assets/images/计算机科学/118382-db84d25a91887fe5.png)

![CCC](/assets/images/计算机科学/118382-ec5b508388ef8972.png)

## Policy Shaping

![Policy Shaping](/assets/images/计算机科学/118382-6dd7ab85ee188417.png)

* if a human is giving feedback (commentary) about weather the agent's action is good or bad, s/he is doing policy shaping.
* policy shaping could be realized by reward shaping which is replace reward of an action with a new reward?
* Agent need a mechanism to learn from the environment and the commentary to decide what policy to take (not just listening to the commentary, cause the commentary might not be always right).

![quiz 1:  Policy Shaping ](/assets/images/计算机科学/118382-aca5004a17fca297.png)

* If human is alway correct, given the feedback, what's the probability that the action (x, y, or z) is optimal?
* answers in the slides above.

![Quiz 2: Policy Shaping](/assets/images/计算机科学/118382-51707cf58b48d58e.png)

* what if human is 0.8 probability of right?
* counting method:
  * saying x is optimal is liking saying y and z is not optimal.
  * since human is 0.8 correct, then x, y, z being optimal is 0.8, 0.2, 0.2. 
  * normalize the numbers above, will get 2/3, 1/6, 1/6.

![Policy Shaping probabiligy calculation](/assets/images/计算机科学/118382-2a5a956943f0a4c3.png)

* Δ<sub>a</sub> is coming from data of action a (d<sub>a</sub>). C is the probability of correct of the people giving commentary.
* The formula above give the method of calculating probability of action a is optimal. 
* Note: the final probability will need to be normalized against the probabilities of other actions.

![quiz 3: How to combine info from multiple sources in Policy shaping?](/assets/images/计算机科学/118382-ee6691a542969101.png)

* in the policy shaping case, information are coming from multiple sources.
* E.g. π<sub>a</sub> and π<sub>H</sub> are policy info from agent exploring the world and human giving feedback.
* Some algorithm decrease the importance of π<sub>H</sub> as time goes. One need to know that π<sub>a</sub> already incorporated the information of human uncertainty (C).
* the way to combine the two sources is to calculate the probability that the two policy will agree: a<sub>opt</sub>=argmax<sub>a</sub> p(a|π<sub>1</sub>) \* p(a|π<sub>2</sub>).
  * in the quiz x<sub>opt</sub> = 1/15, y<sub>opt</sub>=1/60,a<sub>opt</sub>=2/15. So we should choose z as optimal.

## Drama Management

![Drama management world](/assets/images/计算机科学/118382-8545ffce1cb91298.png)

* the way a human can communicate to an agent
  * demonstration: show the agent what's the correct action (inverse RL)
  * reward shaping: giving reward for agent's actions
  * policy shaping: commentary on the agent's actions
* author convey his intent to the agent so the agent can 

![Drama Management: what's a stroy](/assets/images/计算机科学/118382-cc8697a542352e5d.png)

* story can be defined as a trajectory through plot points

![Trajectories as MDP](/assets/images/计算机科学/118382-0b35723e5c3ad7dd.png)

* above a some mapping of MDP elements to trajectory MDP elements
* Problems
  * large number of sequence of states (hyper exponential)
  * Since MDP will maximize rewards, treating story as an MDP will only make the author happy and force the player to experience the story.

![TTD-MDP: Targeted trajectory distributions MDPs](/assets/images/计算机科学/118382-748b50e7957bcf24.png)

* p(t'|a,t) is the probability that the player at trajectory t and take action a then ended up in trajectory t'. P(T) is a target distribution.
* the action is not player's action but the story action
* the optimal policy is the policy that will lead to the targeted trajectory distribution P(T)
* the calculation time is linear and dependent on the length of the story.

## what have we learned

![recap](/assets/images/计算机科学/118382-00d77a30851db60e.png)

```
2015-11-18 初稿 完成
```

