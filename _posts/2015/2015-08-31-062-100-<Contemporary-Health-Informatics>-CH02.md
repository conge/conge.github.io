---
layout: post
title: "062-100 《Contemporary Health Informatics》第二章"
date: "2015-08-31 08:30:30"
categories: 阅读
auth: conge
tags: 读书笔记
---
* content
{:toc}

> ![Contemporary Health Informatics](/assets/images/阅读/118382-aa432bd3d772d66a.jpg)

> 图书信息：[豆瓣](http://book.douban.com/subject/26601196/a0)

传统的以纸张作为纪录媒介的医疗信息系统有很多弊端。这里只举一个例子说明一下，医生的手写处方往往龙飞凤舞，在药房的工作人员需要练就一双火眼金睛才能搞清楚医生到底开的什么药。要是药房人员看错了，给病人拿错了药，造成医疗事故，可就事儿大了。因为这个死人的也有。





医疗信息数字化可以降低人为错误，方便信息传递，病人可以更加方便的获取自己的病历，也可以降低医疗成本，行政管理成本，沟通成本。然而医生医院或者医生本人却不见得有动力完成医疗信息数字化。

即便是救死扶伤的医院，也有追求利益的一面，采用新的系统虽然长远来看可以降低成本，但是在先期的时候，是需要一部分资金投入。除了资金投入，还需要进行新旧系统的兼容调整，不同的医院诊所可能采取不同的策略。最后，还要进行员工培训。购买系统容易，但是学习信东西，对于已经习惯于原有系统的人来说，比较难。

既然医院和医生也有逐利的一面，那么达成让所有医院医生都适用健康信息科技，就得利诱。这一章就是讲美国政府的健康信息科技的三步走计划。这个计划有三个方面，分三步完成。

第一个方面是电子健康记录系统（EHR）的认证。政府不出面研发EHR系统，交由私人公司去搞。但是政府提出一套标准，必须满足标准才能通过认证，各个医院诊所必须使用通过认证的系统，才能从政府拿到补偿。

第二个方面是实现有意义的使用（meaningful use）。光买了系统，放在那里不用，是从政府拿不到钱的。正是这个Meaningful use这里，分了三步。

第三个方面是补偿计划。政府根据医院诊所何时参与到这个计划当中的，又是何时达成的第一、二、三步的，逐步进行补偿。有钱拿，动力就有了。

有意义的使用的第一二三步要达成的目标分别是1）数据采集与分享，2）推进医疗进程和3）改善医疗结果。

每个步骤都有考核标准，第三步的考核标准正在制定中。已经有大部分的医院诊所采用了EHR系统。反响呢，有好有坏，总体是好的。我自己也有些切身的体会，以后有机会再写。

饿的不行了。吃饭去。

----

## Summary of the book

Part I: Problems and Policies

Chapter 2 Current US Federal Policies and Initiatives

Incentives in healthcare, the models of care and the adoption of health information technology (HIT) are connected.

Roughly, 20% percent of Medicare patients have five or more chronic diseases and they account for half of all Medicare costs. In an average year, such a patient sees about 14 providers and s/he faces a logistics problem from the point of view of IT professional.

It's more challenging for PCPs. One typical PCP often sees about about 6 such patients, send them to about 86 providers, and keep connection with about 229 providers for all patients. The logistics needs are more complex for physicians.

The more physician one patient sees, the more errors might emerge because the lack of coordination among physicians. unavailable tests, duplicate test orders or prescriptions, information sharing failures...

### Case Study: informatics for improved use of medications.

Superscripts, allows physicians prescribe medication and send the prescription to the pharmacy of patients' choice electronically. All physicians who use the system can get the patient's medication list when they see them. So they will not make duplicate orders or prescribe anything that will interact with the meds that the patients are currently taking. 

It's convenient to patients because then don't need to drop off their prescription by themselves any more.

## Why coordinated Care?

It's the need of effective and efficient management of chronic diseases. The key is to coordinating care among many physicians involved in patient care.

Clinical information systems are not new insight. The development of EMR systems started in 1970s, but the adoption rate of the these types of systems were very low. One of reason is that **there is no financial incentives for doing so**. 

## New Care Models Require Health Informatics to succeed.

**Patient Centered Medical Home (PCMH)**: Team-oriented approach to care, primarily for chronic diseases; continuous involvement with the patient between physical visits and widespread use of HIT.

HIT is crucial for PCMH, however, different systems are not designed to be "interoperable" so they can not share data seamlessly.

## Accountable Care

Studies showed that "Pay-for-Performance" approach of incentive might improve the quality of care. these led to the Physician Group Practice (PGP) project by Medicare. PGPs receive incentives (from Medicare) by achieving benchmark quality performance. They receive additional bonus if they can provide better care AND lower the cost. Marshfield Clinic get more bonus because (one of the reason) they established a fully functional electronic health record (EHR) system.PGP led to **Accountable Care organizations (ACOs)**.

**Basic requirements of ACOs** is enrolling 5000 Medicare beneficiaries.

**Characteristics of ACOs**: Still paid-for-service, but receive bonus based on improvement of quality and savings of costs. Formation of the ACOs are self administered. They use more community resources (pharmacies, home care) and adopt HIT.

Pioneer ACOs give preferences to organizations with advanced HIT capabilities.

## Policy Overview

In 2004, George W. Bush set a 10-year goal for universal computerization of health records and created **Office of the National Coordinator for Health IT (ONC)**. ONC has funded some research and projects to develop and promote **HIT** and **health information Exchange(HIE)**. HIE has a focus on data sharing between different HIT systems.

In 2009,**Health Information Technology for Economic and Clinical Health(HITECH)** Act was passed. It provides funding to providers who adopt EMR. 

In 2010, **Patient Protection and Affordable Care Act** was passed. It started to change the financial incentives in healthcare.

The goal of these two act: universal adoption of HIT by 2014 and changing healthcare to outcome-based incentives.

HIT adoption is implemented in three parts:
* **EHR certification**: minimal acceptable requirements of EHR, if met the requirements of Meaningful Use, would qualify for incentive payments
* **Meaningful use**: what to do with EHR to qualify incentive payments;
* **Incentive payments**: how to apply for incentives if met the requirement of EHR certification and Meaningful use.

## EHR certification

EHR must be verified by the National Institute of Standards and Technology(NIST).

EHR systems should do three things:
1. record key data (demographic and clinical health information)
2. Provide tools to measure and improve care quality
3. Protect confidentiality, integrity and availability of data.

Details about the three criteria:

![1.  record key data](/assets/images/阅读/118382-d633bae36bb694a9.png)
![2. Provide tools to measure and improve care quality](/assets/images/阅读/118382-135417d1f04b9832.png)
![3. Protect confidentiality, integrity and availability of data.](/assets/images/阅读/118382-35c3092fb5ad72fb.png)

EHR systems must be able to change status of problems based on input (ICD codes or SNOMED CT codes) and provide quality reporting.

## Quality Measurement in Healthcare

A working definition of healthcare quality: Healthcare quality measure should indicate the degree to which health services for individuals and populations increase the likelihood of desired health outcomes and are consistent with current professional knowledge.

**Process measure**: e.g. whether a test for a problem done?

**Outcome measure**: e.g. whether the problem controlled?

## Electronic Health Records:

The use of electronic records can reduce some human error: E.g. pharmacist misreading physician's handwriting and giving patient wrong meds.

Key elements of Contemporary HIT:

**EMR** is the foundation. **Personal Health records (PHR)** and **HIE** allowing the secure and private sharing of protected health data. **EHR** is build on EMR PHR and HIE to manage patient data for providers. **Care Coordination Systems** are needed to enable communication and data sharing among different providers and their EHR systems. The ultimate goal is to build **Databases for Second Use** to collect and store health data for research.

## Meaningful Use

Three objectives:

1. Certified EHR are used.
2. Health information is being exchanged.
3. clinical quality measures are being collected and submitted.

Meaningful use is undergoing 3 stages. Stage 1 & 2 are defined and Stage 3 is proposed.

### Stage 1:

| measurement category| # of measures|
|----|----|
|core measures| 15 (all mandatory)|
|menu set measures| 5 of 10|
|clinical quality measures| 6 of 41 (3 mandatory)|

**Core measures are divided into 4 groups**:
* Improve quality, Safety, and efficiency, and reduce health disparities
* Engage patients and families
* Improve care coordination
* Privacy and security

Menu set measures can also be divided in the similar groups.

Under *quality, Safety, and efficiency*, a report listing patients of a specific condition must be provided as surveillance data.

### Stage 2 

Stage 2 raised the bar of quality measures similar to those in Stage 1. And it focus on patient access to their data. Viewing, Downloading or Transmitting (**VDT**) directly or via API count as measurements.

![Stage 2 encourages User engagement: VDT](/assets/images/阅读/118382-84e86d89354cd4e8.png)

### Stage 3

Stage 3 is proposed but not approved yet. For more information about stage 3, please see [Intro to Health Informatics 第二周笔记](http://www.jianshu.com/p/ebfe5bec6897).

## Incentive payments

Providers who adopted certified EHR and achieved meaningful use are qualified for incentive payments from Medicare or Medicaid.

The incentive payments are based on when a provider enrolls and achieves the three stages of Meaningful Use.

As of March 2015, 86% eligible hospitals and 73 eligible professionals received incentive payments.

70% adopters of EHRs reported 1) administrative, financial and clinical benefits and 2) improved clinical communications. But not everyone are happy about their EHR systems.

## See also

[Intro to Health Informatics 第二周笔记](http://www.jianshu.com/p/ebfe5bec6897).

```
2015-08-31 初稿
```
