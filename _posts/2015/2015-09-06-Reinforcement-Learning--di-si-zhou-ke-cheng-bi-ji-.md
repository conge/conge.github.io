---
layout: post
title: "Reinforcement Learning 第四周课程笔记"
date: "2015-09-06 12:04:19"
categories: 计算机科学
excerpt: "本周三件事：看课程视频，阅读 Sutton (1988)，作业3（HW3）。 以下为视频截图和笔记： Temporal Difference  ..."
auth: conge
---
* content
{:toc}

本周三件事：看课程视频，[阅读 Sutton (1988)](http://www.jianshu.com/p/d2796b5f87a4)，作业3（HW3）。

以下为视频截图和笔记：

## Temporal Difference  Learning

![Read Sutton 1988 first](/assets/images/计算机科学/118382-504d712e4b0ca50f.png)

* Read Sutton, Read Sutton, Read Sutton. Because the final project was based on it!

![Three families of RL algorithms](/assets/images/计算机科学/118382-311884cbd051001b.png)

1. Model based
2. Model free
3. Policy search

* Form 1 --> 3: more direct learning
* From 3 --> 1 more supervised

----

## TD-lambda

![TD-lambda](/assets/images/计算机科学/118382-f152593e62818c2f.png)

![Quiz 1: TD-lambda Example](/assets/images/计算机科学/118382-d38378591d3a8af2.png)

* in this case the model is known, the calculation is easy.

![Quiz 2: Estimating from Data](/assets/images/计算机科学/118382-05faa4b08ca9c881.png)

* Remember from the previous lecture, we need to get value from each episode and average over them.

![Computing Estimates Incrementally](/assets/images/计算机科学/118382-c22280d7d09675e9.png)

* The rewrite makes the formula looks a lot like neuro-net learning. and alpha is introduced.

![Quiz 2: alpha will mke learning converge (tips:if 指数i大于1, 1/(T)<sup>i</sup> will be bounded](/assets/images/计算机科学/118382-48e9f2fda101215d.png)

![TD (1) rule](/assets/images/计算机科学/118382-7b73fc9a7148b71f.png)

![TD(1) with and without repeated states](/assets/images/计算机科学/118382-6af4a8d2994cc513.png)

* When no repeated states, the TD(1) is the same as outcome-based updates ( which is see all the rewards in each state and update weights).
* when there is repeated states, extra learning happens.

![Why TD(1) is "Wrong"](/assets/images/计算机科学/118382-d7dcc73a78d77d2c.png)

* in case of TD(1) rule, V(s2) can be estimated by average episodes. we only see V(s2) once and the value is 12. Then V(s2) = 12
* in case of Maximum likelihood estimates, we have to kind of learn the transition from data. e.g. for the first 5 episodes, we saw s<sub>3</sub>->s<sub>4</sub> 3 times and s<sub>3</sub> -> s<sub>5</sub> 2 times. So the transition probability can be extracted from data as 0.6 and 0.4 respectively.

![TD(0) Rule](/assets/images/计算机科学/118382-9598276643dcdf3e.png)

* First of all, if we have infinite data, TD(1) will also do the right thing.
* When we have finite data, we can repeatedly infinitely sample the data to figure out all the ML. This is what TD(0) do.

![Connecting TD(0) and TD(1)](/assets/images/计算机科学/118382-67c08454de051f6b.png)

## K-Step Estimators 

![K-Step Estimators](/assets/images/计算机科学/118382-43686f7925cab82d.png)

* E1 is one-step estimator (one-step look up) TD(0)
* E2 is two-step estimator, and Ek is k-step lookup.
* When K goes to infinity, we got TD(1)

![K-step Estimators and TD-lambda](/assets/images/计算机科学/118382-90ca5c847c79ce90.png)

TD-lambda can be seen as weighted combination of K-step estimators. the weight factor are λ<sup>k</sup>(1-λ).

![Why use TD-lambda?](/assets/images/计算机科学/118382-bbd74b441ed9432f.png)

The best performed lambda is typically not TD(0), but some λ in between 0 and 1.

![Summary](/assets/images/计算机科学/118382-a078afff664eb78f.png)

```
2015-09-5 初稿
2015-12-03 reviewed and revised until the "Connecting TD(0) and TD(1)" slides
```
