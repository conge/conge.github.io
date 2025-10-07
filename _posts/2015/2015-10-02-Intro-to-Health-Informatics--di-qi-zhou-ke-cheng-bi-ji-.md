---
layout: post
title: "Intro to Health Informatics 第七周课程笔记"
date: "2015-10-02 10:07:02"
categories: 计算机科学
excerpt: "Lesson 6: Clinical Data collection and visualization challenges Two key ..."
auth: conge
---
* content
{:toc}

## Lesson 6: Clinical Data collection and visualization challenges

## Two key challenges in HIT: 

* **Data collection**: efficiently and accurately collect high quality, comprehensive clinical data from busy and often computer-averse providers 
* **visualizing EHR data**: in a way that supports the provider’s mental model 

---

# Ⅰ. Data Collection

## Conflicts

![Physcians are in the data business](/assets/images/计算机科学/118382-4388c5da97d58c0d.png)

* physicians are in the Data Business. 
* medical records and record keeping receive minimal attention in medical training.

## How Physicians collecting and using data: 

![Collecting data by interviewing patient](/assets/images/计算机科学/118382-804deb8cb94ee880.png)

![Order tests, make dianosis and prescribe medication based on lab results](/assets/images/计算机科学/118382-25e5619718c0dddf.png)

![Follow up, medication changes and refereral](/assets/images/计算机科学/118382-3754af05c5eff19e.png)

* Subjective interviewing -> preliminary diagnosis 
* Objective laboratory, imaging, and other tests.
* Based on subjective and objective data, assign the patient with one or more diagnoses; 
* Develop a plan for managing them (e.g. prescribing medications, referral to specialists). 
* Follow up and make adjustments. 
* Coordination with other providers.

## Three common sources of error:

![Sources of errors](/assets/images/计算机科学/118382-176a421711db43b2.png)

1. An Incomplete Knowledge Base - the physician can’t know everything 
2. An Error in Perception or Judgment - physicians are subject to human error, and  
3. A Lapse in Attention - Busy physicians are may not focus sufficiently on each case.

Mishandling of data might cost life and money

## Electronic records themselves can be a new source of errors. 

### reason:

![EMR Template](/assets/images/计算机科学/118382-245b764a50fec9f6.png)

* Data standards are large and complex.
* An electronic version of the paper check off forms - long list which bounds to errors

### Sources of electronic records error

![List is too long. Acitive error is more likely to happen](/assets/images/计算机科学/118382-a9a145aa23ad3a3a.png)

![System default is another source of errors](/assets/images/计算机科学/118382-3eefdda361620d14.png)

![Inconsistent data across locations](/assets/images/计算机科学/118382-2321ff487bed8a38.png)

* “**active error**” — the entry of inaccurate information.
* incorrect system defaults. 
    * a) provider may overlook the **default value** while charting. 
    * b) EHR “remembers” the values from a patient’s prior visit.
* fitting as much as possible onto each data entry screen. 
*  inconsistent data across locations. (different terms for the same thing or non-standard abbreviations or acronyms).
* Physicians may not record all the needed data 
* hard to know which observations/events is definitive or even the most up-to-date.

## M\*Modal

![M\*Modal Demo](/assets/images/计算机科学/118382-b59b038bacb6f563.png)

* advanced medically specific __voice recognition__ technologies.
* translate voice to text 
* recognize clinical concepts in that text and codes them (using ICD9 and SNOMED-CT). 
* M*Modal is a tool, it isn’t an EMR. 
* The first EMR implemented M\*Modal was PrimeSuite from Greenway Medical Technologies.

![M*Modal demo](/assets/images/计算机科学/118382-9f4b2e64d554f14d.png)

![Quiz 1: look up SNOMEC-CT code](/assets/images/计算机科学/118382-7a8cb321b5a54957.png)

[The SNOMED-CT browser](http://vtsl.vetmed.vt.edu/).

## Interview with M\*Modal's chief scientist, Dr. Juergen Fritsch

![ Dr. Juergen Fritsch](/assets/images/计算机科学/118382-f6b24a28838b63a8.png)

Q1. Why M\*Modal was not directly built in an EMR and how do you train the system?

A: It is intentional. We started with finding the technology with dictation and transcription in the backend and provide a drafted report for physicians to review and confirm, and use the drafted and the corrected report to train the system. After years of training, the system becomes useful for immediate audio recognition.

Q2. How hard it is to automatically find clinical concepts in verbal transcriptions and coded them into SNOMED?

A: dealing with the complex SNOMED ontology and challenges in natural language processing. Also, ambiguity of words with different meanings in different contexts is another thing to deal with.

Q3. How accurate is the system now?

A: Depends on usecase. It can be very accurate for some subset of SNOMED (e.g. for particular type of diseases). The accuracy rate is low if you try to encode the whole SNOMED-CT due to the complexity of it.  

Q4. What technologies does M\*Modal is using?

A: 1). Speech recognition: well-know machine learning models ( neural network, regression models, etc……). But we combine speech recognition technologies with natural language processing technologies. 2) coding to SNOMED: a lot of classifiers

Q5. How is it going with implementing M\*Modal into the EMR system PrimeSuite from Greenway?

A: Physicians like storytelling style of data entry, so M\*Modal is a great to extract information from verbal notes into structured information. More and more EMR vendors starts to invest in ways to preserve narrative type of data.

Q6. what 's the potential role of voice recognition technology in healthcare?

A: Physicians tends to create storylines and narratives around their patients.  voice recognition technology is a way to help physicians enter this type of data into EMR systems.

Voice recognition technology can help to improve evidence based healthcare by identifying trends, facts in documents created by physicians. The information can be used to derive better treatment and accurate diagnosis for other patients.
 
> The original M\*Modal was founded by three Carnegie Mellon PhD's. It was acquired in 2011 by MedQuist, a much larger company, and the merged entity was renamed M*Modal. It filed for bankruptcy in 2014 but, so far as I can tell, its business was actually profitable but insufficient to pay the huge debt incurred as part of the merger so the purpose of the filing was to restructure the debt.

## Machine learning in EMR technology

![Praxis](/assets/images/计算机科学/118382-2fa9034161b782d2.png)

* Praxis by Infor\*Med Corporation. 
* Praxis learns how physician usually treats each problem and presents a note based on the most similar past patient(s). 
* Each phrase is what Praxis calls a “clinical concept” : **text descriptions** as defined by each physician. 
* Physician must confirm and/or edit each clinical concept to avoid the "default error".

![Quiz 2: think of ways to use machine learning to help with clinical data collection](/assets/images/计算机科学/118382-d20dcbd1752d9973.png)

## Physicians' attitude towards innovative EMRs

![Physicians' attitude towards innovative EMRs](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson++6+Exercise+19+AAFP+Survey.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* physicians, especially physicians who have a say on what system they can choose, do prefer EMRs with innovative approaches to data collection. 
* Practices with more physicians tend to be more conservative.

---

# Ⅱ· Data Visualization

How to present data to physicians  to support “their mental model”?

![Jigsaw text analysis tool helps to understand **relationships** among stage, medication and treatment of cancer](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Lesson++6+Exercise+21+Jigsaw.png)

EMRs don’t really distinguish fairly obvious differences

![EMR design question for differnt patient](/assets/images/计算机科学/118382-b95486561beb8131.png)
 
![EMR design question for different physicians](/assets/images/计算机科学/118382-8029490b22109f3c.png)

## the IOM’s seven information-intensive aspects 

* Stores comprehensive patient data
* provides cognitive support
* intergration of patient-specific data
* integration of evidence-based guidelines
* practice-wide care management
* population-level care management
* recognizing the home as a new care setting

![information-intensive aspects ](/assets/images/计算机科学/118382-f0069f0a53765cf5.png)

![IMO's perspective](/assets/images/计算机科学/118382-3f9568f4062f4a30.png)

![Home based healthcare](/assets/images/计算机科学/118382-7d6b278a3ce2744d.png)

----

##Key Concepts/Vocabulary

## Readings
* [Computational Technology for Effective Health Care](http://www.nap.edu/catalog.php?record_id=12572)
* [Medical Records, Patient Care and Medical Education](http://link.springer.com/article/10.1007%2FBF02945791#page-1)
* [2009 interview of Dr. Weed](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2911807/)
* [Book by Dr. Weed](http://www.amazon.com/Medical-records-medical-education-patient/dp/081519188X)
* [Electronic Health Records (EHR): Benefits and Challenges for Data Quality](http://mitiq.mit.edu/IQIS/Documents/CDOIQS_201177/Papers/02_08_2B_Panel_Disc.pdf)
* [Notes on Hospitals](https://archive.org/details/notesonhospital01nighgoog)
[To Err is Human: Building a Safer Health System.](http://www.iom.edu/Reports/1999/To-Err-is-Human-Building-A-Safer-Health-System.aspx)
* [Debating the value of EHR templates](http://pilchermd.com/2008/03/30/template-charts-and-the-emr-the-good-the-bad-and-the-ugly/)
* [Detailed discussion and explanation of Praxis](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Praxis.pdf)
[AAFP survey results](http://www.aafp.org/fpm/2012/1100/p23.html)
* [Surveys of physician satisfaction with EHRs](http://medicaleconomics.modernmedicine.com/medical-economics/news/physician-outcry-ehr-functionality-cost-will-shake-health-information-technol)
* [Physician (dis)Satisfaction with EHRs?](http://frissepolicy.blogspot.com/2014/02/physician-dissatisfaction-with-ehrs.html)
* [Optimal CCD Visualization](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Optimal_CCD_Visualization.pdf)
* [Inspired EHRs: Designing for Clinicians](http://inspiredehrs.org/)
* [Medication Reconciliation](http://inspiredehrs.org/designing-for-clinicians/medication-reconciliation.php)

## Videos
* [TwinList demo](https://www.youtube.com/watch?v=YoSxlKl0pCo)
* [TwinList details](https://www.youtube.com/watch?v=dABfksDvOiw)
* [Medication Reconciliation — SHARPC UTHealth](https://www.youtube.com/watch?v=4VyIsPS9r4U)

```
2015-09-30 初稿， 完成一半视频
2015-10-01 完成所有视频
```
