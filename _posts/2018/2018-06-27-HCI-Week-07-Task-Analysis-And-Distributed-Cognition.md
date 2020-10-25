---
layout: post
title: "HCI笔记 | Week 07 Task Analysis And Distributed Cognition"
date: "2018-06-27 06:27:27"
categories: 计算机科学
auth: conge
tags: HCI OMSCS
---
* content
{:toc}

This week, you should watch lessons [2.7 Task Analysis](https://classroom.udacity.com/courses/ud400/lessons/9438503139/concepts/last-viewed) and [2.8 Distributed Cognition](https://classroom.udacity.com/courses/ud400/lessons/9486193755/concepts/last-viewed).

# 2.7 Task Analysis

![Intro](/assets/images/计算机科学/118382-33ecd4a634f61a4d.png)

* The task is at the heart of HCI: Look at the tasks now and restructure tasks to be more efficient using new interfaces. 

Two methods for task analysis.
> 1. Human information processor models (the GOMS Model): focuses on the input to the user and the output from the user and takes the processor model of the user.
> 2. Cognitive task analysis: Tries to get inside the users head takes the predictor model of the user




## GOMS model

![GOMS](/assets/images/计算机科学/118382-85f49d8c887a94be.png)

* The GOMS model is a human information processor model and builds off the processor model of the human's role in a system. 
* GOMS models capture our goals, our different methods for carrying out those goals, and the individual operators that we use to execute those methods.

> 1. Goal: in the system, every user has a goal or several goals
> 2. Operators: Operators the user can perform in the system to carry out a method. 
> 3. Methods: users have methods to achieve those goals. 
> 4. Selection rules: the user uses the rules to choose among different competing methods. 

## Visual representation of GOMS
The user:
> 1. starts with some initial situation, and has a goal in mind 
> 2. applies their selection of rule and chooses between different competing methods 
> 3. Executes the series of operators in the selected method
> 4. accomplishes the goal (see figure below)

![Visual representation of GOMS model](/assets/images/计算机科学/118382-96269f3578f02e04.png)

* Two examples: sending message and navigation.

## Quiz: Using GOMS to describe the two methods of entering an alarmed door.

![Quiz](/assets/images/计算机科学/118382-40ef6b6308d0dd5f.png)

## Answer:

![](/assets/images/计算机科学/118382-20b94d5d8e0ada8e.png)
* ?? I don't see selection rules here.

## Strengths and Weaknesses of GOMS

Weakness: 
> 1. it doesn't automatically address a lot of the complexity of problems. (Augmented GOMS like CMN-GOMS and NGOMSL, can deal with complexity.
> 2. it assumes the users are experts who have all the methods in mind. 

Strength:
> 1. it formalizes user interaction into steps that we can actually use to make predictions on the efficiency of using a certain interface. 

## Paper Spotlight: "The GOMS Family of User Interface Analysis Techniques: Comparison and Contrast"

![Authors](/assets/images/计算机科学/118382-4ab34bf7d5819795.png)

Varieties of GOMS models: KLM GOMS, CMN GOMS, and NGOMSL.

### KLM GOMS
![Six operators](/assets/images/计算机科学/118382-081de5758b1332ce.png)

* Keystroke-Level Model GOMS, the complexity of an interaction is defined by the operators used and the sum of the execution times for an action. (Six operators: K)

### CMN-GOMS
![CMN-GOMS](/assets/images/计算机科学/118382-7ca6514a93cc4285.png)

* features sub-methods and conditions in a strict GOAL hierarchy
* the model is often used to cut down the complexity of the interface

### Natural GOMS Language 
![Natural GOMS Language](/assets/images/计算机科学/118382-a7bfbe5f4e524405.png)

* a natural language form of GOMS: easy for human interpretation.
* help to spot the design which requires more working memory

## 5 tips: Developing GOMS Models

![Developing GOMS Models](/assets/images/计算机科学/118382-a959d822435e24fa.png)

1. focus on small goals. GOMS was really designed to work in the context of very small goals
2. nest goals instead of operators. It's possible to nest goals. Operators, however, are the smallest atoms of a GOMS model. 
3. differentiate descriptive and prescriptive. building a model of what people do or what you want them to do?
4. assign costs to operators. Usually, the cost is time.
5. use GOMS to trim waste. Use GOMS to identify places where the number of operators required can be simplified by the interface.

## GOMS to Cognitive Task Analysis

* GOMS models are human information processor models which assumes a human is an input-output machine. the internal reasoning of the human is ignored
* that human reasoning is actually too nuanced and complex to be so simplified. 
* Cognitive task analysis adopts more of the predictor view of the human and puts a much higher emphasis on things like memory, attention, and cognitive load. 

![](/assets/images/计算机科学/118382-ae3d302eba1c1c09.png)

behaviorism and cognitivism
* Behaviorism emphasized things that could be observed. 
* Cognitivism suggests getting into the mind of what people are actually thinking and how systems like memory and learning and perception actually work.
* The GOMS model emphasis on identifying goals and operators

## Cognitive Task Analysis

![](/assets/images/计算机科学/118382-0f45891fc6246f98.png)
* __Cognitive Task Analysis__ is a type of method of approaching the evaluation of how people complete tasks. 
* Cognitive task analyses are especially concerned with understanding the underlying thought process in performing a task. 

## common sequence of CTA
![common CTA sequence.](/assets/images/计算机科学/118382-a76e745c0683c0ea.png)
* First, we want to collect some preliminary knowledge. (needfinding?)
* Second step is to identify knowledge representations. The types or structures of the knowledge that they have. F
* the third stage, populated those knowledge representations. recognizing what the user actually knows.
* Four, we analyze and verify the data we acquired. 
* Five Format our results for the intended application. -interface design. 

## Example CTA

![CTA for navigation](/assets/images/计算机科学/118382-2a37a035a86f1d6b.png)

* The tasks in the middle are highly cognitive rather than observable (monitoring everything).
* think out loud might help to collect data

## Hierarchical Task Analysis



* One challenge of CTA is that very often, large tasks are actually composed of many multiple smaller tasks.
* these smaller tasks could then be used in different contexts.

Example: Here’s a somewhat simple model of the act of buying something online.
![example](/assets/images/计算机科学/118382-2d58ee9aa56c1e9c.png)

Anyhow, if we treat this cognitive task analysis more hierarchically we can start to see a well-defined subtask around this checkout process. 

* hierarchical task analysis helps us understand available tools or design certain things to transfer between different tasks and different contexts. 
* Hierarchical task analysis also lets the designers of the site abstract over this part of the process and focus more on what might make their particular site unique. 
* the strengths supplied by this hierarchy: 1) abstracting out unnecessary details for a certain level or abstraction, 2) modularizing designs or principles so they can be transferred between different tasks or different contexts, and 3) organizing cognitive task analysis in a way that makes it easier to understand and reason over. 

## Cognitive Task Analysis Strengths and Weaknesses
![](/assets/images/计算机科学/118382-8ef9dc17728d6dc6.png)

Strengths:

> 1. CTA emphasize mental processes. Puts an emphasis on what goes on inside the users head.
> 2. formal enough to be used for interface design.

Weakness:

> 1. CTA are incredibly time-consuming to perform. Getting and analyzing the data need time.
> 2. CTA risk deemphasizing context. 
> 3. CTA is not well suited to novices. 

## Other Task Analysis Frameworks
![](/assets/images/计算机科学/118382-5517c3e97f968cc7.png)
__More in line with the human information processor models__ 

* KLM, TLM, and MHP, which capture even finer grain actions for estimating performance speed. 
* CPM-GOMS and NGOMSL. CPM-GOMS focuses on parallel tasks, while NGOMSL provides a natural language interface for interacting with GOMS models. 
__More on the lines of cognitive models__:
* CDM, TKS, CFM, Applied Cognitive Task Analyses, and Skill-Based Cognitive Task Analyses. 
  * CDM puts a focus on places where critical decisions occur. 
  * TKS focuses on the nature of humans' knowledge. 
  * CFM focuses on complexity. 
  * ACTA and Skill-Based CTA are two ways of gathering the information necessary to create a cognitive model. 

## Conclusion to Task Analysis
![image.png](/assets/images/计算机科学/118382-330da3de39374691.png)
![image.png](/assets/images/计算机科学/118382-5452bed7377ca711.png)
![](/assets/images/计算机科学/118382-ed3cd7b6b71c3f71.png)



----

# 2.8 Distributed Cognition

## Introduction to Distributed Cognition

3 levels of HCI: 
* user interacting with the computer. 
* user interacting with the task through some computer.
* User interacting with the task through computers in some contexts 

In this lesson, we are looking at four different models or theories, of __the context__ surrounding HCI. 
1) distributed cognition, 
2) social cognition, 
3) situated action, and 
4) activity theory.

## Distributed Cognition
![image.png](/assets/images/计算机科学/118382-c15f294909fa9596.png)

* Distributed cognition suggests that models of the mind should be extended outside the mind. This theory proposes expanding the unit we use to analyze intelligence from a single mind to a mind equipped with other minds and artifacts and their relationships among them.
* E.G. By using pen and paper to write down numbers, the cognition was distributed amongst these artifacts

### Paper Spotlight: "How a Cockpit Remembers Its Speeds"
![](/assets/images/计算机科学/118382-6aaf05cfaf256400.png)

* Edwin Hutchins, 1995, “How a Cockpit Remembers its Speeds” 
  * The cockpit is a collection of controls, sensors, and interfaces, as well as the pilots themselves. 
  * The system as a whole (the cockpit) is remembering the speed

![](/assets/images/计算机科学/118382-6e7935936d1e6067.png)

The challenge it's addressing: Landing a plane
* When a plane is descending for landing, the pilot must remember a sequence of speeds at which multiple changes to the configuration to the wings must be made. 
* The task is high in cognitive load. Pilots must act quickly. And no mistake can be tolerated

![](/assets/images/计算机科学/118382-cb0286e380096f25.png)
We see a long-term memory in the book of cards, a short-term memory in the card they selected, a working memory in the speed bugs on the speedometer.
* the pilots have pages that contain the speeds for their descent, based on different parameters.  -  __long term memory__of different speeds for different parameters. 
* Then, prior to the descent, the pilots find the page from that booklet that corresponds to their current parameters.- __short term memory__
* Then as the pilots mark the different speeds right on the speedometer with speed bugs.to remind them to make a certain change. - __working memory__

Decisions on when to make configuration changes distributed across the pilots and these artifacts. The cognition involved in landing this plane is __distributed__ across the components of the system ( the pilots, the speed bugs, the cards).

### Distributed Cognition and Cognitive Load

* Distributed cognition suggests that artifacts add additional cognitive resources to offset cognitive load. 
* E.g.: A GPS is a way of off-loading one of the tasks, navigation, on to another system. Cruise control off loading the task of tracking speed to the car.

### Quiz: any part of the system that performs some of the cognition for Morgan.
![Answer](/assets/images/计算机科学/118382-8c53f0fcc7818362.png)

* Morgan is the processor 
* The checkbook can hold ink copies of the checks, a form a memory
* the pen: helps communicate the message from the bill to check
* two piles of bills: helps to keep track of which bills are done and which are not: short-term memory
* the bills: the long-term memory of billing info

### Distributed Cognition as a Lens

* distributed cognition isn't really another design principle. 
* Distributed cognition puts attention on how to extend the mind across artifacts. 

### Quiz: Reflections: Distributed Cognition

* reflect on what is the place where the system comprised of you and some number of interfaces is capable of doing more than you alone?

### Distributed Cognition to Social Cognition

![](/assets/images/计算机科学/118382-27c33f6fe7e6afb9.png)

* Distributed cognition is concerned with how the mind can be extended by relations with other artifacts and __other individuals__.
* mobile devices and artificial intelligence may have replaced humans in some such systems
* Example: JIRA tool allows a team of members to work on different part of a project.

## Social Cognition

The social portion of distributed cognition is concerned with:
* how social connections create systems that can, together, accomplish tasks.
* cognitive underpinnings of social interactions themselves. How perception, memory, and learning related to social phenomena. 

Designers need to know how social interactions actually work to design interfaces that integrate with social interactions

### Quiz: Design Challenge: Social Cognition

How to design gaming platform so my coworker won't know how much I play games.

## Situated Action

* Situated action focuses on humans as improvisers. It’s interested in the kinds of novel, situational problems that arise all the time. 
* The users are defining the task as theygo along.

![Situated Actions](/assets/images/计算机科学/118382-72f49813b5bb0cef.png)

There are three takeaways here.

1. we must examine the interfaces we design within the context in which they’re used.
2. we must understand that the task that users perform grows out of their interaction with our interfaces -- we don’t define it.
3. we can try to structure it as much as we can, but until users get started, the task itself doesn’t exist -- and once they get started, they play a significant role in defining the task.

### Situated Action and Memory

* recognition is easier than recall in part because memory is so context dependent. 
* Recognition provides the necessary context to identify the right option. Relying on recall means there's little context to cue the right answer to the users' memory. 

### Paper Spotlight: "Plans and Situated Actions"

* Lucy Suchman's 1985 book, _Plans and Situated Actions_
* two views of human action
  1. views the organization and significance of action as derived from plans.  
  2. people simply act in the world, and plans are what we derive from those actions.
* the key take away for us is to focus on the resources available to the user at any given time.

## Activity Theory
![](/assets/images/计算机科学/118382-d83f8341b5964629.png)

* Activity theory predates HCI.
* three main contributions of activity theory to HCI:
  1. Activity theory generalizes our unit of analysis from the task to the activity: why is the user completing the task in the first place? 
  2. activity theory emphasis that we can create low level operations from higher level actions. 
  3 activity theory points out that actions by the user can actually move up and down this hierarchy.  e.g.: an action can move from being a conscious action to a subconscious operator.

### Paper Spotlight: "Activity Theory and Human-Computer Interaction"

In 1996, Nardi outlines the general application of activity theory to HCI in two papers

![](/assets/images/计算机科学/118382-1bf42228131ac108.png)
![](/assets/images/计算机科学/118382-441844decec9adbc.png)

* activity theory offers a set of perspectives on human activity and a set of concepts for describing that activity. And this is exactly what HCI research needs as we struggle to understand and describe "context", "situation" and "practice". 

### Paper Spotlight: "Studying Context: A Comparison of Activity Theory, Situated Action Models, and Distributed Cognition"

![](/assets/images/计算机科学/118382-9f0e4dc1c1cacacb.png)

* Nardi wrote a comparison between the three philosophy
![](/assets/images/计算机科学/118382-10be6a624b8ad596.png)
![](/assets/images/计算机科学/118382-e985e2ce97c4e768.png)
![](/assets/images/计算机科学/118382-6c75eafc2d0511e3.png)
![](/assets/images/计算机科学/118382-6a4ecae5ea3e5db0.png)
![image.png](/assets/images/计算机科学/118382-9b8e3a31c1d2d6d6.png)

1. she notes the activity theory and distributive cognition are driven by goals. Whereas situated action de-emphasizes goals for a focus on improvisation.
2. situated actions says goals are constructed retroactively to interpret our past actions
3. permanent, persistent structures are important for activity theory and distributed cognition. But present attention for situated action. 
4. the main difference between activity theory and distributed cognition is their evaluation of the symmetry between people and artifacts:
  * Distributed cognition believes that artifacts can serve cognitive roles. And so those should be considered conceptually equivalent to humans. 

## Exploring HCI: Distributed Cognition

think about distributed Cognition in terms of your chosen areas of HCI. What are the cognitive components of the areas with that you're dealing? How do augmented reality and wearable devices off-load some of the user's cognition onto the interface? And as occasional technology, or in HCI for health care, what are the tasks being accomplished by the system's comprised of users and interfaces?

## Conclusion to Distributed Cognition

The common ground for all these theories is that our interfaces are not simply between the users and their task, but they also exist in some kind of greater context.

* Distributed cognition is interested in how cognition can be distributed among multiple individuals and artifacts, all working together. 
* Situated action focus on the importance of ad hoc improvisation
* activity theory focus on the need to emphasize users' motives beyond just their goals. 


```
2018-06-27
```
