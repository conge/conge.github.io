---
layout: post
title: "HCI笔记 | Week-10-HCI-and-Agile-Development"
date: "2018-07-19 07:19:10"
categories: 计算机科学
excerpt: "Introduction to Agile Methods..."
auth: conge
---
* content
{:toc}

lessons [3.7 HCI and Agile Development](https://classroom.udacity.com/courses/ud400/lessons/9802732148/concepts/last-viewed) and [3.8](https://classroom.udacity.com/courses/ud400/lessons/9836200517/concepts/last-viewed)

> 3.8 is the conclusion of 3.1~3.7, so no notes for it.

# 3.7 HCI and Agile Development

## Introduction to Agile Methods

Agile workflow: 
* origins from software development, 
* emphasizes __earlier delivery__, __more continuous improvement,__ and __rapid feedback cycles__.
* In HCI, it leads to quicker design and feedback cycles

## The Demand for Rapid HCI

![](/assets/images/计算机科学/118382-58e20f37d71d04f6.png)

 Costs associated with elements of the design life cycle. Then and now:
__Then__:
* Developing software required a very specialized skill set. 
* Software distribution needed a supply chain. The cost of fixing it was enormous. 
* user feedback:  having users come in for testing. 

Quote from Shigeru Miyamoto,
> a delayed game is eventually good, but a rushed game is forever bad. 

__Now__
* Development isn't cheap now, but it is cheaper.
* Distribution and updating for software: now essentially free. 
* Feedback: we can gather usage data from live users automatically, and essentially for free as well. usage data, product reviews, error reports, the buzz on the internet.

The entire design life cycle is still important for big websites, complex apps, hardware, interfaces need a high profile first impression and anything high in stakes. 

This lesson answers the questions: How do you take the principles we've covered so far and applied them to a rapid, agile development process?

### Quiz: Exercise: When to Go Agile

![Quiz](/assets/images/计算机科学/118382-6a74ab2e5795eefe.png)

My answers: 1,3,5. But 1 is not correct.
* because it has an impact on important work, it's not easy to update the interface, changes in the interface will have high impact. More rigors design cycle show te applied.

## When to Go Agile

![](/assets/images/计算机科学/118382-d5d45463c9aaf1ab.png)

When should you consider using these more agile methodologies? Boehm and Turner suggest:
1. in an environment with low criticality because agile process lets the users do some of the testings. 
  * No for Healthcare or financial investing 
  * Yes for smartphone games and social media apps, 
2. in a place where requirements change often. 
3. small teams that are comfortable with change. 

### Paper Spotlight: "Towards a Framework..."

In 2006, Stephanie Chamberlain, Helen Sharp, and Neil Maiden:

Agile development to user-centered design had a significant overlap: they both 
1. **emphasized iterative development processes building on feedback from previous rounds.**
2. emphasized on **the user's role in the development process**
3. emphasized the importance of team coherence

the conflicts between the two are relatively light:
1. the importance of documentation 
2. the importance of doing research before the design work

### five principles for integrating user-centered design and agile development. 

![](/assets/images/计算机科学/118382-192b7b3c4d12bc48.png)

1. high user involvement 
2. close team collaboration. 
3. prototyping 
4. the design life cycle: run a sprint ahead of developers to perform the research necessary for user-centered design. 
5. strong project management is necessary.

## Application of Agile development in HCI

### Live Prototyping

1. when constructing the final interface is as easy as constructing prototypes? 
2. when we make small little tweaks or small revisions, 
3. When we have a lot of experience with designing interfaces in the first place,
4. When the cost of failure is relatively low, and if the possible benefit of success is particularly high.

### A/B Testing

AB testing is the name given to rapid software testing between typically two alternatives, A and B to get user feedback.
1. rapidly testing small changes with real users by rolling out the B version to only a small number of users to get feedback and to make sure a change is positive, or at least neutral
2. testing feedback is coming with the real users during normal usage of our tool. 
3. No added cost to recruiting participants and the feedback is received instantly. 

## Agile HCI in the Design Life Cycle
![](/assets/images/计算机科学/118382-fc96dee0763e5026.png)

taking an agile approach to the design lifecycle just changes the rate at which we go through it, and the types of prototypes, and the types of evaluation that we do.  **An initial needfinding phase is still necessary**

* needfinding by reading user feedback or checking out interaction logs. 
* We're still brainstorming design alternatives. But immediately move them on to prototyping. 
* Prototypes work. 
* Evaluating by rolling our changes out to only certain participants first to make sure the response is good. 
* And the results of that evaluation then feed the same process cycle

### 5 Tips: Mitigating Risk in HCI and Agile Development

![](/assets/images/计算机科学/118382-d5dd90deabae7ed7.png)

1. start more traditional, start with a more traditional needfinding, and prototyping process, and shift to more agile development once you have something up and running. 
2. focus on small changes. 
3. adopt a parallel track method. Agile development often uses short two week sprints in development. have the HCI research one sprint ahead of the implementation. The HCI team can do two-week sprints of need finding, prototyping, and low fidelity evaluation and then hand the results to the development team for their next sprint. 
4. be careful with consistency. Frequent usage, don't change.
5. nest your design cycles. Take all that new information from the agile design process and use it in the context of a broader, more traditional design cycle, aimed at long-term substantive improvements instead of small optimizations.

## Conclusion to Agile Methods

HCI can work in a more agile development environment because that  they both:
1. emphasize feedback cycles, 
2. emphasize getting user feedback, 
3. emphasize rapid changes. 

HCI traditionally behind the scenes but  Agile emphasizes doing these live.  And Agile is a more complex suite of workflows and stakeholders.

```
2018-07-19 初稿
```
