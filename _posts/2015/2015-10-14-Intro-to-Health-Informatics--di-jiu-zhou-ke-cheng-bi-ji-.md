---
layout: post
title: "Intro to Health Informatics 第九周课程笔记"
date: "2015-10-14 02:43:23"
categories: 计算机科学
excerpt: "Lesson 8: Population Health Management primary focus of healthcare: trad..."
auth: conge
---
* content
{:toc}

## Lesson 8: Population Health Management

* primary focus of healthcare: traditional “one patient at a time” care paradigm,
* managing public health problems across the population is also important.
* Informatics has a key and essential role in aggregating and reporting data at population level

## Case Study: PopHealth

![PopHealth: basic architecture](/assets/images/计算机科学/118382-19ec7e498a62ed3b.png)

__PopHealth__:
* open source Quality Measure Reference Implementation supported by ONC. 
* queries are run against data in each provider’s EHR (__data is in providers' control__).
* The results are statistics at one of three levels of detail, called QRDA.
* popHealth is designed to deal with the reality in most places with no HIE in place

![Quiz 1](/assets/images/计算机科学/118382-9c8058e26fc2827d.png)

> Answer to quiz 1: __adv__: 1) provider might be more likely to participate since they have control over the data. 2) security is simplified. __Disadv__:  1)have to deal with each EMR; 2) changes in EMR might cause problems.

![Quiz 2:](/assets/images/计算机科学/118382-74550e4149bc42ae.png)

> Answer to quiz 2: Centralized "data lockers". Providers will still have control to the data and queries to respond while keep the data formatting problems to a low level.

![QRDA categories](/assets/images/计算机科学/118382-ebf07f12f3670b87.png)

* QRDA is the standard vehicle for reporting the results of population or public health queries
* QRDA = Quality Reporting Document Architecture, which is in a CDA-compliant format
* Reported statistics can be classified into three levels of QRDA categories
* Three level:
  * individual patient level, 
  * lists of patients 
  * data aggregated over the entire practice or reporting entity. 

__Note__: PopHealth supports reporting in three different levels

![PopHealth: Practice level reporting](/assets/images/计算机科学/118382-f75382a22e44ff6b.png)

* example: 500 patients from a 10-provider practice (in which individual physicians could be using different EMRs). 
* smoking screening is good but weight screening is not so well.
* the need to identify the right group of patients for each metric. 
  * the numerator — typically the number of patients whose care met criteria
  * the denominator — the applicable target patient group for the metric

![Quiz 3](/assets/images/计算机科学/118382-381fa7eeac1d603c.png)

* applicable target patient group should include any individuals at risk

![PopHealth: provider level reporting](/assets/images/计算机科学/118382-b31d88b2606af805.png)

* provider level reporting provide details about all providers

![PopHealth: patient level reporting](/assets/images/计算机科学/118382-a60b366227775dec.png)

* patient level reporting can provide patient status at a glance
* Care outside of guidelines is flagged here in red.

## Case Study: Quality Health First Introduction

![Paste_Image.png](/assets/images/计算机科学/118382-eb8e98e7896b3376.png)

IHIE 

* Quality Health First supports more sophisticated searches using a simpler data model than IHIE on A wide variety of patient subsets

Recall that in Lesson 2 we learned __process__ and __outcomes__ measures. The process measure is whether it is done periodically according to guidelines and it’s actual value is a measure of the outcome of care.

* quality reporting to add transparency to healthcare through public reporting of quality metrics. 
* In Indiana, many providers voluntarily report this data at a practice level. 

### Quality Health First Public Measures

![Quality Health First Public Process Measure](/assets/images/计算机科学/118382-9fa21c4243e66aa7.png)


![Quality Health First Public Outcome Measure](/assets/images/计算机科学/118382-8cb886245854e50c.png)

Above are examples of provider level HbA1C process metric and QHF outcome metric. State average = red line;  regional average = green line.

Here’s a similar  report based on HbA1C that shows seven practices are below state average (red line) and five are below their regional average (green line)

![Quiz 4](/assets/images/计算机科学/118382-64d3d60f94b7e537.png)

> Answer to Quiz 4: Mix of patient based on their social, economic or demographic factors.

## Case Study: Wellcentive Introduction

* outcomes based contracting by insurance companies, Medicare and even major employers, commercial companies now provide the population health management tools. Wellcentive is one of them. (based in Atlanta)

![Paste_Image.png](/assets/images/计算机科学/118382-87fe5b15a53b5456.png)

* A report of overall performance for a list of practice-defined alerts
* illustrates the need to managed metrics specified in these contracts. 

![ an analysis by provider of the use of lipid-lowering drugs (LLDs) for patients at risk for coronary heart disease](/assets/images/计算机科学/118382-4f1caf699a4e1f7f.png)

![further provider analysis and an analysis of the relationship between blood pressure and the use of LLDs](/assets/images/计算机科学/118382-0688c97dad019ffb.png)

![Quiz 5](/assets/images/计算机科学/118382-c5c1079f113754d9.png)

> 1) security and trust issues; 2) standardize the clinical data.

### Interview with Kirk Elder

![Interview with Kirk Elder](/assets/images/计算机科学/118382-70d26823d7f0c1bf.png)

Q1: Founding story of Wellcentive, Inc.

A: Two brother in law, one is generating quality measurements using excel sheets, the other is a software engineer who knows how to help with this process both sees a market. They found the company to provide software which helps providers generate quality reports.

Q2. How many data are you collecting and processing?  

A: we have about 1000 practices, 8000 physicians are using the service, 25,000 interfaces to collect data from. Process 200 million clinical data points per month. have sent 175 million transactions to payers and resulted in payment based on clinical quality.

Q3. How do you do it?

A: be aggressive on data collection from customer. Create interface to parse, process and interpret  the data and put them into structured format so it can be used by the application.

Q4. How do you normalize and standardize data from multiple sources.

A: We do this in a "purpose driven" way: ask customers what should be in the quality report for them to get paid by the payers and only pick out the related data points from the data we get. We then create custom dictionaries of the quality measures and mappings between custom dictionaries to national standards.

Q5. How do you address security issues.

A: HIPPA risk assessment (pass all the checklist) on the application and HIPPA education to employees is required.

Q6. How do the system handle patients who have to see multiple providers?

A: Practice entities are trying to solve the problem internally via DIRECT and HIEs.  

Q7. What do you think the role of direct in the complex practice, doctors and patient relationship?

A: We are MU certified so we support standards and protocols such as Direct and CCDA. But we deal with EHR most of the time. We see DIRECT as a technology to get clinical information from outside the practice.

Q8. What we are going in terms of population health can quality measurement.

A: Patient can seek service from multiple places and there data will come from different providers and systems. To access the total quality, one has to gather and aggregate all the data. Base on these, we have to figure out who is responsible for the quality actions and should be paid for the action taken.

FTC ask provider organization only to contract with payers when they are clinically integrated, which is difficult. workflow and health systems need to change their internal structures over time. 

Once physician engagement is achieved, then we can see patient engagement.

## Public Health Overview



 

![Public Health Overview](/assets/images/计算机科学/118382-4ff66d61f0a82d38.png)

* From an informatics perspective, many aspects of public health are similar to population health:
  * data is aggregated and reported.  
  * However, public health takes a broad view 
  * uses disparate data sources for the factors determining health and disease.

![Biosense 2.0 by CDC, Case Study: Tarrant County ](/assets/images/计算机科学/118382-c32ad1c5612a2010.png)

* Syndromic surveillance, monitoring for disease outbreaks. 

## Overview

* Data can be aggregated across EHRs to manage entire patient populations against defined quality objectives. 
* it can be used to support and enhance critical public health services such as disease surveillance.

## Supplementary materials

### Key Concepts/Vocabulary

● HQMF ● QRDA

### Links

* [Patient-Centered Primary Care Collaborative publication](http://www.pcpcc.org/resource/managing-populations-maximizing-technology)
* [The Query Health Initiative](http://wiki.siframework.org/Query+Health+-+Project+Charter)
* [Guide to QRDA](http://www.cms.gov/Regulations-and-Guidance/Legislation/EHRIncentivePrograms/Downloads/Guide_QRDA_2014eCQM.pdf)
* [Quality Health First's public reporting site](http://www.ihie.org/public-reporting)
* [Improving Population Health blog](http://www.improvingpopulationhealth.org/blog/population-health-basics/)

### Videos

* [Biosense 2.0 approach](http://vimeo.com/32199430)
* [A more detailed look at the role that syndromic surveillance, the goal of Biosense 2.0, can play](https://www.youtube.com/watch?v=tKyYr7eNEVo&feature=youtu.be)
* [Dr. Taha Kass Hout describes the Biosense 2.0](https://www.youtube.com/watch?v=31npXXC6R6Q)

### Graphics

* [popHealth Architecture](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson+8+Exercise+2+popHealth+Architecture.png)
* [popHealth practice-level report](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson+8+Exercise+6+popHealth+Practice+Level+Reporting.png)
* [popHealth provider-level report](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson+8+Exercise+8+popHealth+Provider+Level+Reporting.png)
* [popHealth patient-level report](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson+8+Exercise+8+popHealth+Patient+Level+Reporting.png)

```
2015-10-12 初稿 至quiz 5
2015-10-13 完成

```
