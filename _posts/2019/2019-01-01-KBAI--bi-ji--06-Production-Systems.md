---
layout: post
title: "KBAI 笔记 06 Production Systems"
date: "2019-01-01 08:35:46"
categories: 计算机科学
excerpt: "Preview Baseball Quiz the point is that the correct answer depends on kn..."
auth: conge
---
* content
{:toc}

# Preview

## Baseball Quiz
* the point is that the correct answer depends on knowledge about baseball

## Function of a Cognitive Architecture
Cognitive agent: a function to mapping history to actions. Precepts -> Action

## Levels of Cognitive Architectures
1. Hardware /Implementation level
2. Algorithm/Symbol Level
3. Task / knowledge Level

* levels are interconnected. the lower level provides architecture for higher level and higher level provides content to the lower level. The constrain each other and some time determine each other.
* Most of the AI work deals with Level 2 and level 3.

## Quiz three layers of Watson

a physical computer, algorithm contains at least searching function. Task is usually answering certain questions.

## Assumptions of Cognitive Architectures

![](/assets/images/计算机科学/118382-88156aac57469380.png)


![ ](/assets/images/计算机科学/118382-9b4c6442caeca19c.png)

Architecture + Content = Behavior


* Architecture + Content = Behavior
* now, assume we can fix the architecture, then behaviour change then indicates Content change.
* Now given that function of cognitive architecture, then we can say if action changes, then the knowledge change must be the cause. This is a simplification of the understanding of human cognitive.

## A Cognitive Architecture for Production Systems

![SOAR](/assets/images/计算机科学/118382-662c2ee898d59755.png)
* Episodic: event
* Semantic: generalizations, concept
* Procedural: how to do certain things

## Return to the Pitcher

How AI make decisions on the pitcher problem

* the pitcher has external knowledge: the status of the game of, other players' position...
* the pitcher also has internal knowledge: his goal 

## Action Selection

![Actions](/assets/images/计算机科学/118382-7c027d8b080f9589.png)

![Abstract state planning](/assets/images/计算机科学/118382-a9bd621b1c7babae.png)

## Putting Content in the Architecture

![Paste_Image.png](/assets/images/计算机科学/118382-7507e3b6ed286128.png)

## Bringing in Memory

![Paste_Image.png](/assets/images/计算机科学/118382-f7fc53bed7308afb.png)

![Production Rules as Procedure Memory](/assets/images/计算机科学/118382-85d5793965007bf9.png)
* the internal and external knowledge are in working memory
* procedural rules are long-term memory

## Exercise: Production System in Action I

![](/assets/images/计算机科学/118382-1b4eab9836912ae8.png)
* we mesh the knowledge in working memory (percept) and rules in the procedural type of long-term memory and  make the decision on what action to take. This is a P -> A mapping

## Exercise: Production System in Action II

![ ](/assets/images/计算机科学/118382-ba4994a18c2c87d0.png)
* r4 suggests that working memory and long-term memory interact with each other constantly, and new rules,new knowledge and actions can be generated in the process.

![](/assets/images/计算机科学/118382-09ba0d3531036dae.png)
* If a new left-handed batter, then two rules can be possible.
* the problem of no action is that there no rule for this particular state.

## Chunking

When 2 operators were selected, there is now rule to determine what to do. Then SOAR will have to learn a rule by activating the episodic memory.

![](/assets/images/计算机科学/118382-06a3bd8eb11eb5db.png)

Chunkin is a learning procedure. (for details, see Lehman, J. F., Laird, J. E., & Rosenbloom, P. S. (1996). A gentle introduction to Soar, an architecture for human cognition. Invitation to Cognitive Science, 4, 212-249.)

![chunking](/assets/images/计算机科学/118382-a4b67fac2a2e79f3.png)
Chunking in operation.

## Fundamentals of Learning
How do agent learn? when to learn, what to learn, why to learn.

## Assignment

![](/assets/images/计算机科学/118382-b209005206e8a684.png)

## Recap

![Paste_Image.png](/assets/images/计算机科学/118382-cb49394fd7171ed0.png)

## The Cognitive Connection

* working memory in both human and production systems have capacity limitations
* Soar and human have similarity when solving algebra problems
* 

```
20170202 first draft
```
