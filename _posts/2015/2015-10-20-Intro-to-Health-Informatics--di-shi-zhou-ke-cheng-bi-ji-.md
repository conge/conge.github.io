---
layout: post
title: "Intro to Health Informatics 第十周课程笔记"
date: "2015-10-20 06:05:08"
categories: 计算机科学
excerpt: "Lesson 9: Data Query in a Federated Environment Distributed query: secur..."
auth: conge
---
* content
{:toc}

## Lesson 9: Data Query in a Federated Environment

* Distributed query: securely obtaining useful data from diverse EHR systems and other sources. 
* ONC supported Query Health initiative. 
* Query Health initiative related video ([The first 18 minutes](http://vimeo.com/28676116) is a good general introduction to distributed query that you should watch. The rest describes individual query reporting systems.)

## Slides from the video
![Article about Distributed data network](/assets/images/计算机科学/118382-31335fb27def83d1.png)

![Desired attributes of Distributed data network](/assets/images/计算机科学/118382-f209e4ec539fa985.png)

* Govern is more important

![Secondary Use](/assets/images/计算机科学/118382-7766929d0eaf1c20.png)

![Data from Multiple Institutions](/assets/images/计算机科学/118382-e7e2b0fa40083412.png)

## why do we need distributed systems

![](/assets/images/计算机科学/118382-78ce304fbdc9eea3.png)

![Rationale 1](/assets/images/计算机科学/118382-c0bb0a49b0b89ec2.png)

![rationale 2](/assets/images/计算机科学/118382-bad643af75d1783b.png)

![rationale 3](/assets/images/计算机科学/118382-e09af2a1fc6a3dbb.png)

![chanllenges 1](/assets/images/计算机科学/118382-90d39c79c3aef779.png)

![Challenges 2](/assets/images/计算机科学/118382-a3def171f86a4316.png)

## hQuery

* hQuery's goal: __simplicity__.  limited but  well standardized data set (in quality measurement and other common clinical activities). 
* point-and-click interface (called the hQuery composer) to non-technical healthcare providers. 
* the possible queries are somewhat limited. 
* hQuery uses a simple patient information model to facilitate query building by nontechnical users. 
* hQuery Gateway 
  * located at source system 
  * receives queries in a standard format 
  * forwards queries to an adapter 
  * the adapter translates the query, receives response and converts it into the standard data model for transmission back. 
* [Video about hQuery](http://news.avancehealth.com/2011/08/hquery.html). 
* HQuery presents results in an attractive way (frequency, time and geographic distributions). 

![hQuery query composer](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson+9+Exercise+2+hQuery+Query.png)

![Patient information model](/assets/images/计算机科学/118382-ddc9db4dfcf4ba1a.png)

![hQuery reports](/assets/images/计算机科学/118382-0dd8bec287744d1d.png)

![Quiz 1](/assets/images/计算机科学/118382-7c503d7fa9c039fd.png)

* the curly braces problem is a technical sub-issue of interoperability problem

##  Informatics for Integrating Biology and the Bedside (i2b2)

![I2b2](/assets/images/计算机科学/118382-92df3f003a85b0ab.png)

* is NIH-funded effort based at Partners HealthCare System in Boston, Mass. * mission: enable clinical investigators to conduct research using genomics and biomedical informatics. 
* is sophisticated to support complex research environments 
* provides an easily understood database schema

![i2b2 Hive and cells](/assets/images/计算机科学/118382-fc68e2aa2541c82a.png)

* i2b2 “cells” communicate via web services and are together called a “hive”.
* Custom cells can be added to the hive. 
* i2b2 users group (share information and applications; create the potential for translational research)

![Quiz 2](/assets/images/计算机科学/118382-35b89e5695435e9a.png)

* extracting clinical concepts or features from free text format clinical notes 

## PopMedNet

![PopMedNet Schema](/assets/images/计算机科学/118382-33f71b98ce9a4a1f.png)

*  each source to maintain control of its data (sometimes referred to as “data lockers”) 
* be capable of accepting and responding to queries. 
* PopMedNet is intended to support medical product safety analysis 

![quiz 3](/assets/images/计算机科学/118382-019e9f8a2946ba39.png)

![Quiz 4](/assets/images/计算机科学/118382-176858240f9c2b35.png)

![quiz 5](/assets/images/计算机科学/118382-5ed47de8a1107b90.png)

## Query Health

![proposed Query Health architecture](/assets/images/计算机科学/118382-9dd75dc773fa7f88.png)

### distributed query standards.

Four kinds of standards:

1. Envelope standards: define the package for sending/receiving queries
2. Format standards: provide a Declarative specification of the query 
3. Results standards (such as QRDA): specify the format and packaging of the query results 
4. Data Model standards (such as CEDD common data element definitions): specify the data model that will link data from the contributing systems.

![Standards](/assets/images/计算机科学/118382-2d167401ca3f67fb.png)

![](/assets/images/计算机科学/118382-7c791e250795c864.png)

* Declarative specification: expresses the desired result.
* Procedural specification: provides a recipe for achieving the goal
* E.g. 1 Curly braces problem with the Arden syntax. Arden provides a declarative standard but the procedure will be different depending on the system that is the source of the data. 
* e.g. 2 The hQuery Gateway receives a standard query on one side but knows how to get it done on the other.

![Quiz 6](/assets/images/计算机科学/118382-f0b8868430cd59d6.png)

### Query envelope standard

![Query envelope standard](/assets/images/计算机科学/118382-279c667b9bddd5a6.png)

The Query Envelope standard serves to provide
* identification that is unique within the network; 
* the information requestor ID including name, email and organization;
* the purpose, priority and type of the query 
  * 7 purpose codes (e.g. TREAT for treatment), 
  * its Priority from 1-5 (1 highest), 
  * its type Type, 1-20 characters
* PHI level (Aggregated, Limited, De-identified, PHI) 
* its Timing, Submission date/time and optional execution date/time.

### Query Format

![Query Format: 3 levels of detail](/assets/images/计算机科学/118382-6a749fb5d1414a94.png)

![Query Format: example](/assets/images/计算机科学/118382-206a5fd804f7b491.png)

* the Health Quality Measure Format (HQMF): an HL7 standard format for documenting the content and structure of a quality measure in an XML document format based on the HL7 RIM.
* It can consist of three levels of detail: 
  * metadata: who wrote it, the dates over which it is valid, who validated it, and other details about how the measure works or is used; 
  * human narrative: measure description, data criteria, measure population and measure observations; 
  * computer instructions: how to count and compute the results of the measure. 
* The example XML provides instructions to the computer to only include patients who have had a weight measured, presumably in the numerator of a weight screening quality metric that, as you should recall from Lesson 2, is a requirement of Meaningful Use.

### the standard for query results

![Query results](/assets/images/计算机科学/118382-719e9017f1a5f37b.png)

* QRDA in [Lesson 8](http://www.jianshu.com/p/047576d2e079).  Results can be reported at three levels of detail: patient-level, patient-list level or aggregate level.
* Example: the two result templates refer to NQF defined quality measures for inpatient asthma care.

###  Query Data Dictionary

![the title here should have been **CEDD** Allergy Example](/assets/images/计算机科学/118382-24cde81ebefcf658.png)

* The Clinical Element Data Dictionary (CEDD): use in setting up source data in support of distributed queries within a larger Query Health solution. 
* it is not intended as a new standards development effort and began with the elements already specified in the CCD and which most EMRs already support
* Here’s a simple example for the patient allergy data element showing how it ties to already accepted standards used in the CCD.

![quiz 7](/assets/images/计算机科学/118382-445b07dd1a853a91.png)

## Recap

In this lesson we 
* examined how data from multiple EHR systems can be queried and aggregated for diverse purposes.
  * e.g. quality reporting and advanced clinical research. 
* All of these technologies provide a framework over the many non-interoperable EHR systems. 
* Different technological solutions each of which is optimized for a specific problem in a specific cross-institutional context.

## Supplementary resources

### Key Concepts/Vocabulary

●Distributed query ● Distributed query standards ● Data warehouse ● Data lockers ● hQuery ● i2b2 ● PopMedNet ● Query Health ● Health Quality Measure Format (HQMF) ● Quality Reporting Document Architecture (QRDA)

### Readings

* [QDM Version 4.1 Specification](http://www.healthit.gov/sites/default/files/qdm_4_0_final.pdf)
* [QRDA Implementation Guide for category I and III reporting](http://www.cms.gov/Regulations-and-Guidance/Legislation/EHRIncentivePrograms/Downloads/QRDA_EP_HQR_Guide_2015.pdf)

### Videos

* [Query Health Initiative](http://vimeo.com/28676116)
* [i2b2 demo](https://www.youtube.com/watch?v=iOtE7cKHKxQ)
* [i2b2 and PopMedNet integration](https://www.youtube.com/watch?v=sqDAo6E-b1o)

### Graphics
* [hQuery query screen](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson+9+Exercise+2+hQuery+Query.png)
* [Query Health pilot proposal](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson+9+Exercise+10+Query+Health+Pilot.png)

```
2015-10-19 初稿
```
