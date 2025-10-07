---
layout: post
title: "HCI 笔记| Week 02 Methods, Ethic and Needfinding and Requirements Gathering"
date: "2018-05-28 05:28:28"
categories: 计算机科学
auth: conge
tags: HCI OMSCS
---
* content
{:toc}

OMS CS6750: Human-Computer Interaction – Summer 2018 笔记 Week 02

Links to Videos: [3.1](https://classroom.udacity.com/courses/ud400/lessons/9605372876/concepts/last-viewed), [3.2](https://classroom.udacity.com/courses/ud400/lessons/9646320134/concepts/last-viewed), [3.3](https://classroom.udacity.com/courses/ud400/lessons/9662642568/concepts/last-viewed)

# 3.1 intro to methods
![image.png](/assets/images/计算机科学/118382-73ccc3fbe3ed685f.png)  
* goal of designing an interface is to meet the needs of the users better than the existing design. 
* Important to consider the users' needs at every stage of the design process. 
* Design novelty must have a purpose and a strong understanding of the users' task is a must.
The unit will cover _Design Life Cycle_,  _User-centered design_, _four stages design life cycle_, and _Qualitative and Quantitative data_.





## User-Centered Design

![User-Centered Design](/assets/images/计算机科学/118382-7c1522ba304c7076.png)

User-centered design is the design that considers the needs of the user throughout the entire design process. 
* in reality, Design is often done to meet some functional specifications of what the tool must technically be able to accomplish, instead of considering the real needs of the user. Or
* people believe they understand the needs of the user without ever really checking.

User-centered design is about prioritizing the user's needs while also recognizing that we don't know the user's needs.
* need to involve the users at every stage of the design process.

## Six Principles of User-Centered Design

1. the design is based upon an explicit understanding of users, tasks, and environments.
2. users are involved throughout design and development.
3. the design is driven and refined by user-centered evaluation.
4. the process is iterative.
5. the design addresses the whole user experience.
6. the design team includes multidisciplinary skills and perspectives (psychologists, designers, computer scientists, domain experts, and more.)

## Stakeholders
![Stakeholders](/assets/images/计算机科学/1logically-a276cc9ae19d7c1d.png)

In designing this tool, we need to keep all three kinds of stakeholders in mind.
* Primary stakeholder is the user who uses our tool directly.
* Secondary stakeholders don't use our system directly but might interact with the output of it in some way.
* Tertiary stakeholders never interact with the tool or its output, but they are impacted by the existence of the tool.

## Reflection: HCI methods
3.1.5, Have you seen places where software engineers, data scientists, or even non-technical people were put in charge of designing user interfaces? How did it go?

As a data scientist, I often generate reports or visuals for stakeholders to consume. I do fine if the audience has some background in research and data analysis. But when we try to bring some outcomes into a product, the design task will be shifted to professionals who know the user better than me. Often, my design is more about getting the key information out but ignore the user's ability to consume and digest the information.

## The Design Life Cycle

![a four-phase design life cycle](/assets/images/计算机科学/118382-ff9cada76f1db7fe.png)

1. Needfinding:
* gather a comprehensive understanding of the task the users are trying to perform. __who__ the user is, __what__ the context of the task is, __why__ they're doing the task, 
2. we develop multiple design alternatives. 
3. prototyping. We take the ideas with the most potential and we build them into prototypes that we can then actually put in front of a user.
4. we perform user evaluation. 
* put ideas/prototypes in front of actual users. 
* Get user feedback
* and then the cycle begins anew. 

Each time we go through this cycle our understanding improves, our designs improve, and our prototypes improve. Eventually, our prototypes develop to the point of being designs ready for launch, and we keep iterating, now with live users doing the evaluation.

## Methods for the Design Life Cycle
![Methods for the Design Life Cycle](/assets/images/计算机科学/118382-21c3e2ae34ea7ec6.png)

Methods to actually obtain that information. 
## Design Life Cycles meets Feedback Cycles
 * In a feedback cycle, the user does something in the interface to accomplish some goal. And then judges based on the output from the interface, whether the goal was accomplished, then they repeat and continue. 
* In HCI, we're brainstorming and designing interfaces to accomplish goals. And then based on the output of our evaluations, we judge whether or not the goals of the interface were actually accomplished, then we repeat and continue.
* In many ways, we and the users are all trying to understand how to accomplish a task in an interface. 
* in the case of HCI, our interface is the tools to build and evaluate interfaces and our goal is to help the users accomplish their goal.

## Qualitative vs. Quantitative Data

![Qualitative vs. Quantitative Data](/assets/images/计算机科学/118382-6df0cb8c8775ba6a.png)

* Data can be used to describe users' interaction with a task;  or measures task efficiency or difficulty, recode users preference measure they performance on certain tasks.

Quantitative data describes anything numeric. With quantitative data, we can perform statistical tests and summaries, thus can draw formal conclusions, and make objective comparisons. But the view will be narrow.

Qualitative Data covers descriptions, accounts, observations, it's often in natural language. qualitative data provide broader and general picture of what we're examining. But it's harder to draw conclusions from it and more prone to biases.

* Sometimes, it's possible to convert qualitative data into quantitative data.

In general, quantitative data provides the "__what__", the qualitative data provides the "__how__" or the "__why__". 
* Need finding or prototype evaluations: qualitative descriptions
* after a few iterations quantitative analysis to find numeric improvements or changes.
* __Mixed method approach__: collecting both quantitative and qualitative data from the same participants.

## Quiz
![](/assets/images/计算机科学/118382-2b71896f1fabb92f.png)

## types of quantitative data
![](/assets/images/计算机科学/118382-d12561e954ceb316.png)

Different types and subtypes of data can inform us what statistical tests that we can perform. but generally, tests for interval and ratio data are the same, and tests for nominal and ordinal data are the same.

## Types of Qualitative Data
![](/assets/images/计算机科学/118382-60d1b1a3760681fa.png)

* Types of Qualitative Data are often determined by the way the data is gathered.
* Qualitative data is expensive to analyze and prone to biases.
* __Coding__ is a process to convert qualitative data into quantitative by categorizing the former (the output is usually nominal). The process needs to be documented.

# Exploring HCI: HCI Methods

* the design life cycle: The process of finding user needs, brainstorming design alternatives, prototyping interfaces and evaluating those prototypes with users. 
* Try to brainstorm a conceptual plan for how you might pursue the design life cycle in your area of interest. 
* examples: 
  * In educational technology, take into consideration lots of stakeholders, students, parents, teachers, administrators and more. 
  * In virtual reality or wearable devices, you need to think a lot more about the technical constraints
  * In computer supportive cooperative work, you might want to explore places where the phenomenon already exists like Wikipedia or geographically distributed companies. 

## Conclusion to Introduction to Methods

* four-step cycle: needfinding,  constructing design alternatives, prototyping, user evaluation, and then the cycle repeats.

* The goal of this cycle is to realize user-centered design: Design that takes into consideration the user's needs at every step.

------

# 3.2: Ethics and Human Research

* Ethical considerations 1) preserve the rights of our users, and 2) ensure the value of the data that we gather

In response to unethical human subjects experiments, the National Research Act of 1974 was passed, and that led to the creation of IRB (institutional review boards)
1. Milgam's obedience experiment:
2. the Tuskegee syphilis study
3. Stanford prison experiment

The Belmont Report further summarizes basic ethical principles that research must follow __in order to receive government support__.
* the benefits to society must outweigh the risks to the subjects
* subjects must be selected fairly
* rigorous informed consent procedures.
* the positive results of research outweigh the negatives and 
* participant rights are always preserved

## The Value of Research Ethics

IRB's main task is to make sure the potential benefits of the study are worth the potential risks. 
* part of the role is to make sure __the potential benefits are significant__. 
* A lot of the steps of the process are going to ensure that __the data that we gather is useful__. 
* IRB helps ensure that research personnel all understand the basics of human subjects research. 
* IRB helps ensure that the research is sound and useful. 

__GaTech uses IRBWISE for IRB applications__.

-- The rest of the unit focused on the practical steps we go through to get approval for human subject's research. Note taking is unnecessary.

## Research Ethics and Industry
![image.png](/assets/images/计算机科学/118382-6b877ca5c8d6ab95.png)


* Facebook case: Facebook manipulate emotion of users via experiment.

![](/assets/images/计算机科学/118382-e95277feda3e5ceb.png)

* referring studies to an external reviewer

----

# 3.3: Needfinding and Requirements Gathering

Needfinding is:
* The first stage of the design life cycle.
* Finding out what the user really needs. understanding of the user or the task. 

Needfinding process:
defining some general questions throughout the data gathering process about __who__ the user is, __what__ they are doing and need.

## Data Inventory:
![Data](/assets/images/计算机科学/118382-30e1466c48b683c7.png)
the data we want to gather eventually answers the questions:
1. who are the users? - ages, gender, levels of expertise
2. where are the users? - What is there environment? 
3. what is the context of the task? - What else is competing for users' attention? 
4. what are their goals? - What are they trying to accomplish? 
5. what do they need? What are the physical objects, information or collaborators do they need? 
6. what are their tasks? What are they doing physically, cognitively, socially? 
7. what are the subtasks? How do they accomplish those subtasks? 

## The Problem Space

Where is the task occurring, what else is going on, what are the user's explicit and implicit needs?
Understand the broader problem space is a good start of the needfinding process.

## User Types
![user type](/assets/images/计算机科学/118382-e2f48f7edd0eb042.png)

understanding of who we're designing for. (Age, level of expertise, cultural background, etc ) 

__5 Tips: Avoiding Bias in Needfinding__
![image.png](/assets/images/计算机科学/118382-d82d79d478c5709d.png)

1. confirmation bias: we see what we want to see.  avoid this 1) by specifically looking for signs that you're wrong, 2) by testing your beliefs empirically, and 3) by involving multiple individuals in the need finding process. 
2. observer bias. The observer may subconsciously bias the users. Avoid this 1) by separating experimenters with motives from the participants. 2) By heavily scripting interactions with users, and 3) by having someone else review your interview scripts and your surveys for leading questions. 
3. social desirability bias. People tend to be nice, want to help and say nice things to make you happy. this gets in the way of getting good data. Avoid this 1) by hiding what the socially desirable response is, 2) by conducting more naturalistic observations and 3) by recording objective data. 
4. voluntary response bias. People with stronger opinions are more likely to respond and we risk over sampling the more extreme views. Avoid this 1) by limiting how much of the survey content is shown to users before they begin the survey and 2) by confirming any conclusions with other methods. 
3. Recall bias. People aren't always very good at recalling which can lead to misleading and incorrect data. Avoid this 1) by setting tasks in contexts, 2) by having users think out loud during activities or 3) conducting interviews during the activity itself. 

* multiple forms of need finding are helpful to avoid bias.

## Needfinding Methods

### I. Naturalistic Observation

Simply watch. observing people in their natural context. 
* start with very specific observations and then generalize out to more abstract tasks. T
* note that down as a question I want to ask people later.
* Naturalistic observation can gather an enormous amount of information but the researcher is limited ethically in what s/he can do. No interaction no identifying information and no access to users' thought process

5 tips to Naturalistic Observation
![](/assets/images/计算机科学/118382-a1c5fe5ae66753b5.png)
1.  take notes.  get a targeted information and observations.
2. start specific and then abstract. Observe first, interpret or summarize them later. 
3. spread out your sessions.  Note different information in different sessions, reflection on past exercises will inform future sessions. 
4. find a partner. Observe independently and compare notes.
5. look for questions.  What you need are questions to investigate further.

### II Participant Observation

experience a task for ourselves 
* "Remember you are not your user."
* use this experience as a participant observer to inform what you ask users going forward

### Hacks and Workarounds

hacks are ways users get around the interface to accomplish their tasks

* Look at the hacks that users presently employ. 
* not just look at their work around, but also ask them why they're using them. 
* Find out why they don't just use the interface that's currently in place. 

### IV Errors

Errors are slips or mistakes that users frequently make while performing the task within the interface.
* Slip happens because when the mental model is correct but the design is weak to support the execution.
* Mistakes are places where the mental model is weak.
* use errors to understand a bit more about the user’s mental model. 
* watch people performing their tasks, and ask them about why certain things happen the way that they do.
* Discovering hacks and errors involves a little bit more user interaction than naturalistic observation. Recruitment might be needed.

### V Apprenticeship and Ethnography

 For particularly complex tasks, we might need to become experts ourselves in order to design those programs. 
* ethnography: recommends researching a community or a job or anything like that, by becoming a participant in it.

### VI Interviews with Focus Groups

A most targeted way to gather information from users though is just to talk to them through interview or focus group. 
* Interviews are useful ways to get at with the user is thinking when they're engaging in a task. 
* Focus groups can elicit some information we don't get from this kind of an interview, 
* the risk is overly convergent thinking. 

__ 5 Tips on Interviews__
![interview tips](/assets/images/计算机科学/118382-c2069241e2ffb510.png)

1. Focus on the six W's when you're writing your questions. Who. What. Where. When. Why and how. Try to avoid questions yes/no questions. ask open-ended, semi-structured questions. 
2. Be aware of bias. not to predispose the participant to certain views. don't show agree or disagree with facial expression.
3. Listen. 
4. Organize the interview. introduction phase. lighter questions to build trust and a summary at the end. Control the interview process so it's on track.
5. Practice. Practice and Rehearse the entire interview.

### VII Think-Aloud and post-event protocol

with think-aloud, we're asking the users to talk about their perceptions of the task in the context of the task. 

* it can help us get at users thoughts that they forget when they are no longer engaged in the task. 
* But it can change the way they actually act. 

With a post-event protocol, we wait to get the user's thoughts until immediately after the activity. 
*the activity is still fresh in their minds, but the act of thinking about it shouldn't affect their performance quite as much.

### VIII Surveys

Surveys let us get a much larger number of responses very quickly and the questions can be phrased objectively, allowing for quicker interpretation. it's low cost with digital online survey tools. 
* it's a powerful way of getting a larger amount of data. 
* it can be especially useful to decide what to ask participants during interviews or during focus groups.

__5 Tips on Surveys__

![tips on surveys](/assets/images/计算机科学/118382-28e363abd3f24228.png)
1. less is more. Ask the minimum number of questions necessary to get the data that you need and only ask questions that you know that you'll use. 
2. Be aware of bias. 
3. Number three. Tie them to the inventory. 
4. Test it out. Before sending it to real participants, have your co-workers or colleagues test out your survey.
5., iterate. Test out your survey, Ask participants for feedback on the survey itself, see what works and what doesn't and revise it accordingly. 

__quiz__
![Surveys](/assets/images/计算机科学/118382-ce60b1a301a3cb45.png)

###  Other Data Gathering Methods

1. UI evaluation for existing interface. 
2. Product review: look at user reviews and see what people already like and dislike about existing products.
3. Data logs: examine data logs about user interaction for insights.

## Quiz: Exercise: Needfinding Pros and Cons
![Quiz: Exercise: Needfinding Pros and Cons](/assets/images/计算机科学/118382-756be28093334186.png)

### Quiz: Design Challenge: Needfinding for Book Reading

## Iterative Needfinding

![](/assets/images/计算机科学/118382-f8d02c80ec7e166c.png)
* all of the different kinds of need finding that we do can inform our next round of other kinds of need finding.

## Representing the Need
![need representation methods](/assets/images/计算机科学/118382-cbbe0a616e06697c.png)

* step-by-step task outline
* hierarchical network
* diagram of the structural relationships amongst the components in the system and how they interact.
* flow-chart equipped with decision-making points or points of interruptions.

## Defining the Requirements

Requirements should be specific and evaluatable, they can include some components that are outside of users tasks, as well, as defined by the project requirements.

user tasks components, 
* functionality, what the interface can actually do.
* Usability, how certain user interactions must work.
* Learnability, how fast the user can start to use the interface.
* Accessibility, who can use the interface.
* Compatibility, what devices the interface can run on.
* Cost, how much the final tool can actually cost, and so on. 

```
2018-05-28
``` 