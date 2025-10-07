---
layout: post
title: "Machine Learning笔记 第16周 "
date: "2016-05-01 09:24:18"
categories: 计算机科学
excerpt: "Machine learning 从第10周之后我就没再更新。一个原因是自己根本没时间学习，另一个原因是剩下的部分中所有内容，都是在我去年上过的..."
auth: conge
---
* content
{:toc}

Machine learning 从第10周之后我就没再更新。一个原因是自己根本没时间学习，另一个原因是剩下的部分中所有内容，都是在我去年上过的另外一门课 Reinforcement Learning 中讲到了。需要那些笔记的话，直接去往下面的链接。 [Reinforcement Learning 第一周课程笔记](http://www.jianshu.com/p/881ab7e41adb) : MDP；[Reinforcement Learning 第十二周课程笔记](http://www.jianshu.com/p/e294d3f5237c)： Game Theory I；[Reinforcement Learning 第十三周课程笔记](http://www.jianshu.com/p/ee3f9a553cd2)： Game Theory II & III。 

下面的这部分内容是RL课中没有，而本课独有的内容。

Reinforcement Learning

![RL](/assets/images/计算机科学/118382-a9cb8480f4a9d306.png)

![API](/assets/images/计算机科学/118382-b9929cc2fc5d8c40.png)

* MDP: Model -> planner -> policy
* transitions(sars) -> leaner -> policy

![Reinforcement learning history](/assets/images/计算机科学/118382-2c2d0012ea52b74b.png)

* RL = reward maximization.

![More RL "APIs"](/assets/images/计算机科学/118382-4560d8ce19d2d326.png)


![What do you call these?](/assets/images/计算机科学/118382-802590c140a63e59.png)


![Three ways of solving RL problems](/assets/images/计算机科学/118382-272eed3d844b7348.png)

- From Direct use/ indirect learning -> indirect learning/direct use of the policy.

* Policy search: find the optimal policy which can get the right action in given state (s).
* Value-function based: find U which can return the best value (v) for state (s). apply argmax on this will generate policy for policy search.
* Model-based approach: based on transition function and reward function, we can get the next state (s') and reward for the current state (s) and action (a) pair. These can be used to solve the Bellman equations and eventually solve value function and given policy.

![Q-learning](/assets/images/计算机科学/118382-c2ff454b627ea8d4.png)

With Q, we can find out U or PI without knowing transition or action. This is why Q learning works. 

![what Q-learning can do](/assets/images/计算机科学/118382-acf61ed25ef17627.png)

## Estimating Q From Transitions

![Paste_Image.png](/assets/images/计算机科学/118382-45a55f200b62db7b.png)

* Estimated Q,(Q hat) is the utility of next state plus the current learning rate discounted by the learning rate alpha.
* V and be estimated by changing alpha

![what V converges to?](/assets/images/计算机科学/118382-0041329c99cec99b.png)

V will converge to the estimated value of X when alpha satisfies: all alphas sum to infinity, but all alpha square sum to a certain number. (e.t alpha = 1/t).

![Q learning proof](/assets/images/计算机科学/118382-c03e2713086e4e43.png)

The first step is a bit ambiguous because Q-hat changes over time. But it works in practice.

![Q learning steps](/assets/images/计算机科学/118382-01d05ccb1223136a.png)

Q-learning only works if s,a visited infinitely often. and alpha<sub>t</sub> satisfy the conditions that it sums to infinity but the square of it sums to something less than infinity.

![Paste_Image.png](/assets/images/计算机科学/118382-eca071ce3195a29d.png)

* always choose a<sub>0</sub> 
* choose randomly
* use Q-hat
* "greedy" (local min) choose a<sub>0</sub> if a<sub>0</sub> is awesome
* annealing 

![Greedy exploration](/assets/images/计算机科学/118382-11b5e537e59913c4.png)
 
exploration & exploitation.

Wrap up
![wrap up](/assets/images/计算机科学/118382-daa863bd8825d112.png)

今天就要考试了，我根本就没复习好。祝我好运吧。
```
2016-04-30 初稿
```
