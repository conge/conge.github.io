---
layout: post
title: "Intro to Health Informatics 第八周课程笔记"
date: "2015-10-07 11:22:26"
categories: 计算机科学
excerpt: "Lesson 7: Empowering the Patient Technology that help patient monitoring..."
auth: conge
---
* content
{:toc}

## Lesson 7: Empowering the Patient

Technology that help patient monitoring and managing their health is the topic of this lesson.

## Key PHR attributes

![PHR](/assets/images/计算机科学/118382-1de1fb6ccc3003c0.png)

* MicroSoft's PHR Health Vault
* include key health information
* It has a smartlist as typing in information
* it supports DIRECT technology
* It supports many physiology monitoring apps and devices to automatically collect health data
* It can update record by CCD 

![Health Vault: main UI](/assets/images/计算机科学/118382-0f1b5067121817b0.png)

![HealthVault: Smart list](/assets/images/计算机科学/118382-76cb9494f5c5d179.png)

![HealthVault: Supports Direct](/assets/images/计算机科学/118382-2c8b0578a7b2c2e4.png)

![HealthVault: Apps and Devices](/assets/images/计算机科学/118382-aab2fe8424722b71.png)

![HealthVault: get data by CCD](/assets/images/计算机科学/118382-4ea3f85c06e899fa.png)

![Activity 1](/assets/images/计算机科学/118382-86383f3d9144a005.png)

 > **To do this activity you MUST follow these steps to send Marla's CCD via Direct to your HealthVault account**: (有8个步骤，此处从略)

## Interview with Vice Present of PatientLikeMe Sally Okun.

Q1. How Patient like me come to be

A: Finding ways to bring patients and their families together so they can learn from each other, find solutions to deal with disease can connect to opportunities to contribute to research. Collective wisdom.

Q2. The lithium on ALS story.

A: PatientLikeMe collected data about the experience of ALS patients taking lithium as a treatment and ultimately disapproved the claim of small study which claim lithium can slow the progression of ALS. This demonstrate the power of the patient community contributing to scientific research.

Q3. You started building the community around ALS and then expanded to other conditions. can you tell a bit more about them?

A: 270,000 patients and  2000 conditions.

Q4. What does it take to make the site work

A: **Engineering side**: software engineers, UI + **Clinical Side**: physicians, research & data scientist. Coded conditions using ICD10, SNOMED-CT, RxNorm for medication. Also match clinical concept and patient vocabulary. 

Q5. How do you help users find clinical trials.

A: 1) data from clinicaltrial.gov and patient can see clinical trials available with 45 miles of where they live. 2) New service **trial access**, help patient contributing in drug development and establish patient centered clinical trial, and also get feedback

Q6. What's the future of PatientsLikeMe, how do you see PatientsLikeMe's role in VDT?

A: Sensors and wearables to do active data collection. Thinking of ways to standardize data and bring them into health records. And trying to figure out of ways to pull data from physicians' EHR system so patient don't have to enter the data manually to PHR systems.


![quiz 1](/assets/images/计算机科学/118382-61a4d9df70d52f08.png)

## Patient Portal

![RelayHealth](/assets/images/计算机科学/118382-174b3c94a291ed94.png)

* test results, request appointments, and pay physicians
* patient can download their data.

![Quiz 2: VDT](/assets/images/计算机科学/118382-83c30bca49221c0c.png)

## Blue Button +

![Blue Button +](/assets/images/计算机科学/118382-cd173157230f5e53.png)

![Blue Button +](/assets/images/计算机科学/118382-5152852e0b9cda8c.png)

![CCDA structure](/assets/images/计算机科学/118382-fbea12cb89c5e88e.png)

* Blue Button was started at VA in 2010, adopted by ONC in 2012
* Blue Button + integrated with DIRECT technology
* It can bring data from multiple sources to patients PHR 
* Data are constructed into CCDA format

## TeleHomeCare

![TelehomeCare comes from Steve Kaufman's original HANC idea](/assets/images/计算机科学/118382-f15ff9e9cabd5ef4.png)

* HANC robots can provide medication to patient and take physiological measurement.

![Quiz 3](/assets/images/计算机科学/118382-cfc6ac0c98451a6e.png)

![Dimensions of TeleHomeCare](/assets/images/计算机科学/118382-b2c89020d349c2b2.png)

* SOAP: Subjective, Objective, Assessment and Plan.

![medication compliance is hard to measure](/assets/images/计算机科学/118382-81fb4f2a478f31a6.png)

* medication compliance: technologies are available to remind patient to take their meds and even dispense medication at proper time, but it still hard to get accurate measure.

![Mobile device can be used to provide objective data](/assets/images/计算机科学/118382-1e836675b0fcb2c5.png)

* Fitbit and smartphones. 
* AliveCore
* FDA is trying to determine how to regulate mobile devices for healthcare usage (For Safety, accuracy, manufactured properly and keeps records)

![Quiz 4](/assets/images/计算机科学/118382-96729b767bafd5a9.png)

## provide help to patient

**Heart360**

![Paste_Image.png](/assets/images/计算机科学/118382-1d5099850e8c4194.png)

* **Heart360**
* PHR apps

## Virtual Home Visit

![Virtual Home Visit](/assets/images/计算机科学/118382-ff1f9429a169bafc.png)

* With internet, physicians can see patient via internet chatting
* Simple and easy to achive
* **Controversy**: Some state medical boards does not allow physicians treating patients over the Internet if they have not previously actually seen that patient in person.

![Quiz 5](/assets/images/计算机科学/118382-dc32bbf2d166d385.png)

## The challenges

* usability is important but difficult to achieve. 
    * Patients must be able to use these technologies. 
    * vast amounts of data V.S. limited time to look at it 
* analytic and visualization tools that minimize false positives and appropriately alert providers are of critical importance. 
  * machine learning 
  * artificial intelligence 

## The Future

technology to empower and **remotely monitor**, **educate** and even **treat** patients is, without a doubt, one of the most dynamic, innovative and rapidly growing domains within health informatics. 

the web, inexpensive measurement devices and mobile computing devices 

----

### Readings

* [Barriers to the Adoption and Use of Personal Health Record Systems](http://staging.star-uci.org/wp-content/uploads/2011/01/iConf_PHR_CAMERAREADY.pdf)
* [Pros and Cons of Patient Portals](http://www.cfha.net/blogpost/689173/138161/The-Pros-and-Cons-of-Patient-Portals-Can-Integrated-Electronic-Health-Records-Help-Empower-Patients)
* [Blue Button is one of the ONC S&I Framework initiatives](http://wiki.siframework.org/BlueButton+Plus+Initiative)
* [The Blue Button REST API](http://bluebuttontoolkit.healthit.gov/blue-button-plus-pull/)
* [Home Telehealth Buying Guide](http://atatelemedicinedirectory.com/Listing/Index/Medical_Services__Providers/Home_Telehealth/2844/96)
* [Validation of an iPhone ECG Application](http://circ.ahajournals.org/cgi/content/meeting_abstract/126/21_MeetingAbstracts/A16810)
* [Geisinger experience with OpenNotes](http://www.myopennotes.org/tag/geisinger/)

### Videos

* [One of the more advanced home medication dispensing technologies (this is a commercial so be advised)](http://www.tabsafe.com/?page_id=498/?)
* [Virtual Nurse Makes Home Visit](https://www.youtube.com/watch?v=NYrFHuHxCqU)

### Websites

* [The Blue Button+ Implementation Guide](http://bluebuttonplus.org/)
* [OpenNotes](http://www.myopennotes.org/OpenNotes)
* [Geisinger Health System](http://www.geisinger.org/)

```
2015-10-06 初稿
```
