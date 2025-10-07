---
layout: post
title: "Intro to Health Informatics 第六周笔记"
date: "2015-09-23 12:19:03"
categories: 计算机科学
excerpt: "Lesson 5B: Interoperability Standards In the last lesson, we learned abo..."
auth: conge
---
* content
{:toc}

## Lesson 5B: Interoperability Standards

![Lesson 5B](/assets/images/计算机科学/118382-567de84c1101b16c.png)

In [the last lesson](http://www.jianshu.com/p/c623ebf0643b), we learned about data standard and the evolution of standards. In clinical practice, data ( standard and nonstandard) need to be packaged into **clinical documents** and send via **messaging standards**. These are the focus of this lesson.

## HL7

**Health Level-7** or **HL7** refers to a set of international standards for transfer of clinical and administrative data between software applications used by various healthcare providers. These standards focus on the application layer, which is "layer 7" in the OSI model. ([Health Level 7 - Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/Health_Level_7))

![Reasons for HL7: to transfer information between departments within a hospital or providers](/assets/images/计算机科学/118382-17fbd6497ab19da2.png)

![Data format that HL7 uses](/assets/images/计算机科学/118382-60641a4ae4ca9db2.png)

![HL7 message in EDI](/assets/images/计算机科学/118382-f4dc7e047a711426.png)

![HL7 message in xml](/assets/images/计算机科学/118382-262a7b15ef511d30.png)

* HDF

![HL7 development framework](/assets/images/计算机科学/118382-301d491f7a6d324d.png)

## HL7 Reference Implementation Model (RIM)

* RIM can be used to create HL7 ver 3 based XML formatted messages and XML based CCDA documents

![RIM](/assets/images/计算机科学/118382-7833fb04dfe42546.png)

![RIM examples](/assets/images/计算机科学/118382-308b732f8bfbf463.png)

 * Here's the [complete RIM example](http://www.healthintersections.com.au/wp-content/uploads/2011/05/RIM.png). 

![RIM example](/assets/images/计算机科学/118382-23c0de3a345de993.png)

## CCDA 

* Consolidated Clinical Document Architecture (CCDA)

![CCDA example: patient demographics](/assets/images/计算机科学/118382-035d75e93ba1d00b.png)

![same data in RIM role](/assets/images/计算机科学/118382-2d9bb645db891b68.png)

![Same info in XML](/assets/images/计算机科学/118382-c6e12c4d75842a11.png)

![Quiz 1](/assets/images/计算机科学/118382-588a56195adcfa33.png)

![Quiz 2](/assets/images/计算机科学/118382-c7095b0e21d474aa.png)

## HL7 Document Standard

* CCDA templates have three subparts: Document template, Section Template and Data Entry Template.
* Templates are reusable XML components

![CCDA Templates](/assets/images/计算机科学/118382-51d79096f6a5dd1a.png)

![Quiz 3: Section level templates](/assets/images/计算机科学/118382-9ca162d454eb007e.png)
 
* Hint: the website in the slides does not work, a google search will lead you to the correct answer.

![Quiz 4: Section level templates](/assets/images/计算机科学/118382-7ede7383a7e34cd1.png)

![global unique identifier: not healthcare specific](/assets/images/计算机科学/118382-b3a0a4b108c87f52.png)

![Quiz 5: Entry level template](/assets/images/计算机科学/118382-c59197fa85b8a79c.png)

![Quize 6: Entry level template](/assets/images/计算机科学/118382-7203e83fad734ae8.png)

![Case Study: the medication consolidate tool using HL7 standards.](/assets/images/计算机科学/118382-371a5f99cec8cc68.png)

## Arden Syntax

![Arden Syntax's Goal](/assets/images/计算机科学/118382-a6448611c35aaff3.png)

![Arden example](/assets/images/计算机科学/118382-47d912bb2609dc6c.png)

* Each MLM supports one medical decision
* MLM can interact with intermediate States and provide CDS

![Example of Arden challenges](/assets/images/计算机科学/118382-5900c7ce6c9f33d8.png)

* Here, `{'dam'="PDQRES2"}` must be interpreted by another EMR to get the creatinine level which often could not be performed because of the interoperability issue of EMR softwares.

## CIMI

![CIMI](/assets/images/计算机科学/118382-d5c78ffba141e294.png)

* numerate clinical ideas to achieve consensus among clinicians
* can be used to constructed standard messages and structured documents as components of clinical rules 
* automate or facilitate constructing data entry and generating clinical reporting templates 

## CMS

* CMS wants to integrate applications at the point of use.

![CMS](/assets/images/计算机科学/118382-5ed10575bc3729fe.png)

![Example of different system dealing with one particular patient](/assets/images/计算机科学/118382-00686ae4ba4693ee.png)

![Smart on FHIR app platform](/assets/images/计算机科学/118382-0e98fe9ed7af2ff7.png)

![Example of Patient resource: in Json format](/assets/images/计算机科学/118382-21eb7b93988acf0f.png)

![Example of Conditoin resource: the code of condition is using existing SNOMED-CT code](/assets/images/计算机科学/118382-4e853a01d60a642d.png)

## FHIR

![FHIR Resources](/assets/images/计算机科学/118382-4f24d50e4d14a733.png)

![FHIR is a platform for apps and it uses Java APIs and RESTful APIs to get data.  ](/assets/images/计算机科学/118382-3e49ea3ca2f6fe7a.png)

* FHIR is still in development and testing and faces challenges: e.g. trade-off between functionality and complexity;
* FHIR is in its second version and is expected to have 100-150 specifications in the final product.

## Andrei Pop Interview about [humanAPI](http://humanapi.co/)

What does HumanAPI do?

It can get health data from multiple sources ( including EHRs, wearable devices), aggregates, normalizes and standardizes them (using HL7) and provided them to EHR, EMRs, etc with users authorization.

The data can be tracked, queried and visualized via API.

It essentially solves the interoperability issue of different vendors of health data generator/provider, etc..

## Josh Mandel interview (Lead Architect of SMART platform of Harvard Child hospital) 

**Q1**. Introduction to SMART platform.

**A**: SMART platform is a project to enable healthcare providers to use the apps they choose to access health data.

**Q2**. Why is the project important and what approach do you take to solve the problem.

**A**: Health data of a patient are usually sitting in databases of different health providers, bring the data together and allow apps to be build based on the data. Developers can create tools to better use the data and users can choose the tools they like.

The approach that SMART platform uses is that we build open sets of specifications based on open standards so any developer can use them to build their tools.

**Q3**. what's new in the latest version of SMART platform?

**A**: Many venders, government, independent labs builded apps based on SMART.

**Q4**: Smart on FHIR.

**A**: FHIR provides important building block for SMART: 1. FHIR resources(detailed clinical data models); 2. FHIR API base on http and restful.

Demo at <FHIR.smartplatform.org>

## Recap

* Health standards initially were created within the industry and only recently adopted XML and web technology.
* The industry is developing detailed standards and it might making the creation of HIT tools more complex.

```
2015-09-22 初稿
```
