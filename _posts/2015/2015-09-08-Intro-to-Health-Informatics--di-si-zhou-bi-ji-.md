---
layout: post
title: "Intro to Health Informatics 第四周笔记"
date: "2015-09-08 22:30:29"
categories: 计算机科学
excerpt: "Lesson 4: Private, Security and Trust People's Protected Health informat..."
auth: conge
---
* content
{:toc}

## Lesson 4: Private, Security and Trust

People's Protected Health information ( PHI, healthcare data that is linked to information that identifies the patient) is protected by HIPPA. PHI can only be accessed by authorized person for legitimate purpose.

![Patients' Access to data improve their care](/assets/images/计算机科学/118382-1824f702c25305f3.png)


![Only 1 in 14 people used PHR, so the doption rate is low.](/assets/images/计算机科学/118382-790e1c50246a83b5.png)


![The main concern is the privacy of their data](/assets/images/计算机科学/118382-e7a2d76562b39a4d.png)

And most of people do not even want their data to be digitized.

## Sub-area of data protection in healthcare

* **Privacy**: only people authorized by patient can see health data.
* **Security**: data is protected from unauthorized access.
* **Trust**: senders and recipients of health information knows that the people they are interacting with are who they say they are.

![Three Sub-area of data protection in healthcare](/assets/images/计算机科学/118382-367a8876b81edbcc.png)

![Quiz 1](/assets/images/计算机科学/118382-30d15ab80e0bac92.png)

![Quiz 2](/assets/images/计算机科学/118382-e3dbc53b04ab2671.png)

![Quiz 3](/assets/images/计算机科学/118382-267efdf4cd54e6a0.png)

![S & I Process](/assets/images/计算机科学/118382-1645cb339bd79c11.png)

![Lab testing ordering workflow](/assets/images/计算机科学/118382-b80851f5c1af0986.png)

## Privacy Consent Models 
![Privacy Consent Models ](/assets/images/计算机科学/118382-befb58e929e9571b.png)

CurrentCare uses Opt-in model.

## Data segmentation

![Data segmentation](/assets/images/计算机科学/118382-7da1d70cc3ffe1ec.png)

## Models for data segmentation

![Models for data segmentation](/assets/images/计算机科学/118382-3bbb603934fb53fd.png)

![A: Too complicated for patient to understand](/assets/images/计算机科学/118382-6bd069ab1687712b.png)

## Public Key infrastructure (PKI), a solution for Trust

![](/assets/images/计算机科学/118382-4db7d0dcf9505115.png)


![Given the public, it is very complicated to calculate the private key.](/assets/images/计算机科学/118382-25aaf0fb8d66b8bc.png)


![The use case of public key and private key for data encreption (top) and digital signature (bottom) ](/assets/images/计算机科学/118382-3a9d4fd479b1a158.png)


![Quiz 4](/assets/images/计算机科学/118382-c7fea1e581a200ee.png)

![Quiz 5](/assets/images/计算机科学/118382-e1bf0fa278c464aa.png)


![Registration authority verifies identity of providers and certificate authority issue certificates ](/assets/images/计算机科学/118382-62c74e8cbb5a9e5c.png)

![So brower can verify that the public keys are indeed from the CA by decrept the keys with CA's public key](/assets/images/计算机科学/118382-5837db54427e9c1b.png)

![How to view public key of Google](/assets/images/计算机科学/118382-90cff4212a45224e.png)

![Other use cases of PKU](/assets/images/计算机科学/118382-a35ebd38374ddd7b.png)

![Concerns about PKI](/assets/images/计算机科学/118382-4e364fabe713ad2c.png)

## Interview with Dr. Don Detmer

Q1. Where we are in transforming our healthcare systems with HIT, and what’s the future?
> A: digital records were believed to be essential in healthcare in 1991, but it is in 2009 when HITECH legislation started, things becomes more exciting. Current HIT is in developing, there are things that are exciting and things we don't like. The use of HIT in terms of computer technology and communication technology are very exciting right now.

Q2. getting digital health data is import but time consuming, the concern is the patients' privacy issues. Does the emphasis of privacy harming the use of data, how to balance privacy and data sharing?
> A: HIPPA is developed pre web area with the paper system in mind. Misuse of the data at that time can bring real harm to people and to the society. But researchers and students want to use the data for research and educational purpose which usually have very low risk. Patients like the idea of using big data for research but culturally they might now want to share their data. We really need very big dataset to address the new health problems. Because of the privacy issue, a lot of study could not even get started. Data liquidity (relative free flowing of data) is an important issue the field needs to solve.

Q3. What's your thought on Patient generated and controlled data repository (VIA PHR), will it contribute to the share of clinical data for research and other purpose.
> A: It sounds great but researchers might ended up getting disportionately represented data because certain group of the population decide to opt out.

## Supplementary material

[064/100 《Contemporary Health Informatics》Chapter 4 Summary](http://www.jianshu.com/p/6cc61829f808)

### Key Concepts/Vocabulary
● HIPAA ● Protected Health Information (PHI) ● De-identified health information ● Privacy ● Security ● Trust ● Personal Health Records (PHRs) ● Privacy Consent Models ● Data Segmentation ● Data Segmentation Models ● Public Key Infrastructure (PKI) ● Public and Private Keys ● Registration Authority ● Certificate Authority

### Readings
* [California Health Foundation patient survey](http://www.chcf.org/media/press-releases/2010/new-national-survey-finds-personal-health-records-motivate-consumers-to-improve-their-health)
* [Xerox comments on the results of their online survey](http://news.xerox.com/news/Xerox-Surveys-Americans-Electronic-Health-Records)
* [Decision Support for Data Segmentation (DS2)](https://sharps-ds2.atlassian.net/wiki/download/attachments/524334/DS2_Policy.pdf?version=1&modificationDate=1401792341355&api=v2)
* [RSA Code Made Easy](https://www.youtube.com/watch?v=t5lACDDoQTk)
* [A Robust Health Data Infrastructure](http://healthit.gov/sites/default/files/ptp13-700hhs_white.pdf)
* [The De-identification Standard](http://www.hhs.gov/ocr/privacy/hipaa/understanding/coveredentities/De-identification/guidance.html#standard)
* [The Computer-Based Patient Record: An Essential Technology for Healthcare](http://www.nap.edu/openbook.php?isbn=0309055326)

### Graphics
* [HealthVault](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/healthvault-ppe+home+page.png)
* [NORC Screenshot](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/NORC+De-identification+Console.png)

### Websites
* [ONC's Standards and Interoperability Framework's home page](http://www.siframework.org/)
* [S&I Framework Wiki](http://wiki.siframework.org/)
* [DS2 Project Home Page](https://sharps-ds2.atlassian.net/wiki/display/DS2/SHARPS+DS2)
* [The NORC X-ID System](http://xid.norc.org/)

```
2015-09-07 初稿
2015-09-08 添加 Interview with Dr. Don Detmer 部分
```
