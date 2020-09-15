---
layout: post
title: "HCI笔记---Week-08-Evaluation"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}


# 3.6 Evaluation

## Introduction to Evaluation

* Evaluation is where we take what we've designed and put it in front of users to get their feedback. 

methods for evaluation depend on stages at design life cycle.
* qualitative feedback: Early on: what the users like, don't like, whether it's readable, whether it's understandable. Later on, is it usable? Does it actually minimize your workload? Is it intuitive? Is it easy to learn?
* empirical feedback:  more quantitative.
* Predictive feedback:

## Three Types of Evaluation

![Evaluation](/assets/images/计算机科学/118382-26d077ddd80720d8.png)

1. qualitative evaluation: get qualitative feedback from users. What do they like, what do they dislike, what's easy, what's hard. use the methods for need finding.
2. empirical evaluation: do some controlled experiments and evaluate the results quantitatively. - need more participants, and need to address the big qualitative feedback first.
3. predictive evaluation. evaluation without users. 

## Evaluation Terminology

![](/assets/images/计算机科学/118382-3592677e3bab3ab4.png)


1.  Reliability refers to whether or not some assessment of some phenomenon is consistent over time

2. validity. Validity refers to how accurately an assessment measures reality. 
  * An assessment could be completely reliable but completely inaccurate.
3. Generalizability is the extent to which we can apply lessons we learned in our evaluation to broader audiences of people. 
4. Precision: Precision is a measurement of how specific some assessment is.

![](/assets/images/计算机科学/118382-fd7a2e202fcbf8e4.png)

## 5 Tips: What to Evaluate
![tips](/assets/images/计算机科学/118382-6e346c70a5ba4991.png)

1. Efficiency. Time, number of actions to accomplish certain tasks. [expert users]
2. Accuracy. The number of errors users commit.  [expert users]
3. Learnability. learning curve. 
4. Memorability. The user's ability to remember how to use an interface over time. I
5. Satisfaction. Users' enjoyment of the system, or the cognitive load experience while using the system. [Need to avoid social desirability bias]

It's important to articulate at the beginning what you're evaluating, what data you're gathering, and what analysis you will use. 

## Evaluation Timeline
![time line](/assets/images/计算机科学/118382-9c0d6302efdc2a5b.png)
Over time, the evaluation method we'll use will change.

### purpose
* Throughout most of our design process: formative evaluations to help with a redesign and improvement 
* At the end: summative evaluation to conclude the design process, especially if we want to demonstrate that the new interface is better. 

### Approach
* early evaluations: more qualitative (more interpretative and informal) * Later evaluations: more empirical, controlled, and formal to demonstrate or assess change. 
* qualitative evaluations and empirical evaluations are ways to actually fulfill formative and summative evaluation, respectively
* Predictive evaluation: similar to qualitative evaluations. inform how we revise and improve our interfaces over time. 

### Data

* using qualitative data more early, and quantitative data later. 
* quantitative data really can only arise when we have pretty rigorous evaluations.

### settings

Settings are where the evaluation takes place. 
* early low fidelity interfaces in a lab setting 
* Later on, we might want to do real field testing w
* But also think about the context early on. 

## Evaluation Design

![Evaluation Design](/assets/images/计算机科学/118382-b18390794aa30356.png)

Steps to ensure that the evaluation is actually useful. 
1. First, clearly define the task. 
    * can be very large or very small. 
    * could involve context and constraints
2. Second, define our performance measures to avoid confirmation bias.
    * Qualitatively: based on spoken or written feedback 
    * Quantitatively, measure efficiency or count mistakes. 
3. Third, develop the experiment. 
    * Think out loud or survey? 
    * what to measure, what to control, and what's vary? 
    * reliable and valid assessment. generalizable. 
4. Fourth, recruit the participants. 
    * Consent
5. Fifth, do the experiment.
6. Sixth, analyze the data. 
    * follow the analytical plan. 
    * do a follow-up experiment to test if needed. 
7. Seventh, summarize the data in a way that informs our on-going design process. 
    * What did our data say was working? 
    * What could be improved? 
    * How can we take the results of this experiment and use it to then revise our interface?

![Design life cycle](/assets/images/计算机科学/118382-1c0badc03662bdd5.png)

## Qualitative Evaluation
![](/assets/images/计算机科学/118382-c27609edf7de6b49.png)

The methods we use for qualitative evaluation are very similar to the methods we used for need finding. Interviews, think-aloud protocols, focus groups, surveys, post-event protocols. 

* What did you like? What did you dislike?
* What were you thinking while using this interface?
* What was your goal when you took that particular action?

### Capturing Qualitative Evaluation

![](/assets/images/计算机科学/118382-f0491875f0a6631b.png)
![](/assets/images/计算机科学/118382-0ed153484f1e393e.png)
![](/assets/images/计算机科学/118382-7e5c7bc3572cf57d.png)

How to capture qualitative evaluation sessions:
1. record the session. 
    * Pros: automated, comprehensive (everything is recorded), passive (research can focus on the evaluation). 
    * Cons: intrusive, difficult to analyze (time-consuming), screenless (can be resolved by recording screen). 
2. Note Taking
    * benefits: cheap, not intrusive, and analyzable. 
    * drawbacks: hard to keep up with the dynamic interactions. Manual and active (might need two people); limited in what it captures. 
3. Logging the behavior inside the software. 
    * Benefits: automatic and passive, it's analyzable. 
    * drawbacks: limited to things that are actually expressed inside the software. Only captures a narrow slice of the interaction.  tech sensitive: have to have a working prototype

### 5 Tips: Qualitative Evaluation
![](/assets/images/计算机科学/118382-6b23d0b7a772ab8b.png)

1.  run pilot studies. try your experiment with friends or family or coworkers before trying it out with real users. 
2. focus on feedback. Try not to teach this one user. Hear the critics.
3. use questions when users get stuck. 
4. tell users what to do, but not how to do it. 
5. Capture satisfaction. the user should be able to use the interface and like it.

## Empirical Evaluation

* evaluate something formal (numeric). 
* The goal is to come to something verifiable and conclusive.
* Most empirical evaluations are comparisons: how can we show there is a difference between designs?

### Designing Empirical Evaluations

Apply treatments to participants and investigate the comparison between the treatments to find out about how they’re different. 
* Design treatments: what's the condition of each treatment
* Design experiment: what participants do.
 * between-subjects design. We're comparing the data from one group to the other group. (Randomize participants assignment to treatments)
  *within-subjects experiment, each participant participates in both treatments. (remove order effect by randomly assign participants in to different order)

### Hypothesis Testing
![](/assets/images/计算机科学/118382-bed2fb0c56b8a2bd.png)

### Types of Hypothesis Testing
![](/assets/images/计算机科学/118382-53a1eb72f206cb2b.png)
![](/assets/images/计算机科学/118382-dfb174052ff4aad7.png)
![](/assets/images/计算机科学/118382-15261c8aba782ab2.png)
![](/assets/images/计算机科学/118382-700abc7bde504f15.png)
![](/assets/images/计算机科学/118382-6109fe71e5951204.png)
![](/assets/images/计算机科学/118382-5596046d8e9f036b.png)

### 5 Tips Empirical Evaluation
![](/assets/images/计算机科学/118382-1f9e245270aaf8f6.png)

1. control what you can, document what you can't. 
2. limit your variables. Focus on varying only one or two things and monitor only a handful of things in response. 
3. work backward in designing your experiment. Decide the research question first and then the analysis and data to gather. 
4. script your analyses in advance. Analyze data with all the method and selectively report the ones showed significant results might be misleading.
5. pay attention to power. The size of a difference that a test can detect. a small effect needs a lot of participants. a big effect needs fewer.

## Predictive Evaluation

Predictive evaluation: evaluation without actual users. 
* efficient and accessible than actual user evaluation. 
* OK to use as part of a rapid feedback process. 
* shouldn't be used when a qualitative or empirical evaluation is available.

### Types of Predictive Evaluation

__heuristic evaluation__: hand the interface and the design guidelines to a few experts to evaluate. 
   * they give us small snapshots into the way people might think about our interfaces. 

__model-based evaluation__
* take models of our users' tasks developed in need finding and trace through it to evaluate it for efficiency.

__simulation-based evaluation__: construct an artificially intelligent agent that interacts with our interface
  * Can we really evaluate them automatically?

__Cognitive Walkthroughs__: 
  * The most common type. 
  * step through the process of interacting with an interface, mentally simulating what the user is seeing, thinking, and doing. 
  * constructing specific tasks that can be completed within our prototype. 
   * investigate: gulfs of execution and evaluation. 
  * The weakness of cognitive walkthroughs: We are not our users
  * So, if you can put yourself in a novice’s shoes enough, you can find some really good feedback without involving real users.

## Evaluating Prototypes
!](/assets/images/计算机科学/118382-55de9c91ccd9d26a.png)

1. qualitative evaluation. ask questions about the interface
2. quantitative analysis. 
3. predictive evaluation:
* evaluation is a foundation of user-centered design 
* understand how the user relates to the design at every stage of the design life cycle.

## Quiz: Exercise: Evaluation Pros and Cons 

![Quiz](/assets/images/计算机科学/118382-91c3c07cf38b0051.png)

![](/assets/images/计算机科学/118382-9a8effcb154d6e2e.png)
*  predictive evaluation is the only evaluation we can do without involving users in the evaluation process. 
* For identifying provable advantages, only empirical evaluation can reliably generate generalizable conclusions, generalizable advantages, because it's the only one who does it numerically. 
* informing ongoing design decisions: Qualitative and predictive evaluation. empirical evaluation is usually at the end of the design lifecycle
* Investing in the participant's thought process: Qualitative evaluation definitely asks users to think out loud and describe their thought process. Predictive evaluation tries to investigate the participant's thought process in a lower overhead or lower cost kind of way. On the other hand, empirical evaluation only accesses participants performance numerically.  
* empirical evaluation can provide generalizable conclusions, again because it uses numbers. 
* qualitative and empirical evaluations both draw conclusions from actual participants. 

```
2018-07-07 初稿
```
