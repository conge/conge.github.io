---
layout: post
title: "Intro to Health Informatics 第五周笔记"
date: "2015-09-23 05:16:53"
categories: 计算机科学
excerpt: "Lesson 5A: Data Standards Data standards can be different from each othe..."
auth: conge
---
* content
{:toc}

## Lesson 5A: Data Standards

![Lesson 5A](/assets/images/计算机科学/118382-567de84c1101b16c.png)

![Why do we need data standards](/assets/images/计算机科学/118382-c876e0b18c1da460.png)

Data standards can be different from each other syntactically or semantically.

* Syntax : Structure difference, need translation.
* Semantic : Meaning difference, E.g. A doesn't have the capacity to represent all the information in C.

![quiz 1](/assets/images/计算机科学/118382-73b693de897fbd1c.png)

Clinical data are often represented with different data standards (as shown above). It's often very complicated to aggregate data from different sources.

## Standards Evolution

![Standards evolution can be divided into three domains](/assets/images/计算机科学/118382-91f0da8738f80921.png)

![Structure of data standards: Classification is list of diseases; Ontology can also represent relationships](/assets/images/计算机科学/118382-7ffdf806ef7d6ed0.png)

![Purposes of standards: ](/assets/images/计算机科学/118382-df4bc1c2ce299070.png)

![Purposes of standards: Document Standards](/assets/images/计算机科学/118382-aba4e3348ca4f0c4.png)

* Physicians use ICD for diagnostic notes
* Labs and pharmacies have their own unique classifications. To coordinate care with each other, healthcare facilities need **messaging standards** between each other.
* When data exchange is needed (e.g. from physician to hospitals or vise versa), **document standards** play important role ( however, *Document standards are hard to implement*).

![Technology of standards: Transport standards](/assets/images/计算机科学/118382-4ad2f2b315c71bd0.png)


![Technology of standards: EDI/X12, created in early days, cryptic and compact.](/assets/images/计算机科学/118382-eb5289a35dc5da65.png)


![Technology of standards: XML, more descriptive and verbose ](/assets/images/计算机科学/118382-31eef27024183c91.png)

The above EDI/X12 and XML examples are showing the same test result. As we can see, that former is more compact, cryptic and hard to understand without training; while the letter is more human readable, descriptive and verbose.

## Key Data Standards

![5 Key Data Standards](/assets/images/计算机科学/118382-8291e594e72ea91b.png)

* CPT (Current *Procedure* Terminology) and NDC (National *Drug* code) are U.S. Specific classifications
* ICD (The International Classification of Diseases) and CPT are most widely used because they are mostly required for medical billing.
* ICD, LOINC (Logical Observation Identifiers Names and Codes) and SNOMED (The Systematized Nomenclature of Medicine) are international ontologies.

![Quiz 2](/assets/images/计算机科学/118382-85fe03125fa275a4.png)

![Quiz 3](/assets/images/计算机科学/118382-9ab5a96998f78ae2.png)

## ICD

![ICD](/assets/images/计算机科学/118382-9da1d25a21ec2fb3.png)

![ICD-9 v.s. ICD-10](/assets/images/计算机科学/118382-b551889e34fa8405.png)

* the U.S. is still using ICD-9 while the world is using ICD-10.
* The U.S. is set to adopt ICD-10 in 2015 when ICD-11 is about out. Some are proposing the idea of skipping ICD-10.
* ICD-10 provides more codes for more information (e.g. laterality of breast cancer)
* ICD is classification prior ICD-10. ICD-10 and the following versions are moving to ontology.

![ICD-10 Example](/assets/images/计算机科学/118382-f2a638b5ba626884.png)

## CPT (Current *Procedure* Terminology)

* CPT is updated annually by the American Medical Association. It classifies all the medical procedures and is required for all medical billings.
* There are three code category for **widely performed procedures**, **quality and performance** metrics  and **new or experimental procedures**.
* For each code, there are **Full**, **Medium** and **Short** descriptions (see below).
* CPT code can be very detailed and specific (e.g. Psychiatry visits by length or size of removal tissue for a procedure)
* Billing personal must be trained to be able to select the correct codes.

![CPT categories](/assets/images/计算机科学/118382-4753ce743c3842a4.png)

![CPT descriptions](/assets/images/计算机科学/118382-8b05aaf349423fef.png)

![CPT code example: Psychiatry vistits by length](/assets/images/计算机科学/118382-d3ac99a616356371.png)

![CPT code example: Skin revoval by Area](/assets/images/计算机科学/118382-e46239d9cbb69f51.png)

![Quiz 4: CPT code](/assets/images/计算机科学/118382-d3e86a0e301ff039.png)

![Quiz 5: CPT code](/assets/images/计算机科学/118382-1c87512cfc3c5e4c.png)

## Logical Observation Identifiers Names and Codes (**LOINC**)  

* it was created and is maintained by the Regenstrief Institute
* LOINC provides codes for lab results and clinical observations
* LOINC provides detailed information about an observation with it's names which can be divided into 7 subparts (See slide below).

![LOINC name example](/assets/images/计算机科学/118382-d07c97eb13fc890a.png)

![Quiz 6: LOINC name](/assets/images/计算机科学/118382-d45c93103914be9e.png)

## National Drug Code

* maintained by FDA.
* 10-digit,3-segment structure indicates the vendor, the drug and the packaging.

![NDC example](/assets/images/计算机科学/118382-3ce8fe7c2ceb7401.png)

## SNOMED-CT

* Created by NIH for pathology, CT is specifically for clinical medicine. It is now distributed by the [International Health Terminology Standards Development Organisation](http://www.ihtsdo.org/) (IHTSDO)
* It's always an ontology
* It's complex
* 9-digital ID and human readable concept names.
* It has hierarchy (shown below) 
* Relationship links expressed by "|is a|".

![SNOMED-CT Hierachy](/assets/images/计算机科学/118382-5f7ccf43f4624880.png)

![SNOMED-CT example](/assets/images/计算机科学/118382-208bb3498d4d1eb3.png)

![SNOMED-CT Concept example](/assets/images/计算机科学/118382-230796e98f89458c.png)

## Activity

* Click on the link below to get a copy of the sample CCD: [Sample HealthVault Continuity of Care Document (CCD)](https://developer.healthvault.com/DataTypes/Example?TypeId=9c48a2b8-952c-4f5a-935d-f3292326bf54). Review the sample CCD carefully and answer the three questions below.

![Activity instruction](/assets/images/计算机科学/118382-78fc20314c5266db.png)

![Activity question 1:](/assets/images/计算机科学/118382-0491ef8ee376f55e.png)

![Activity question 2 ](/assets/images/计算机科学/118382-a6474b5a06154087.png)

![Activity question 3](/assets/images/计算机科学/118382-ff20ec9944b0e7f8.png)

```
2015-09-21 初稿 至ICD slides
2015-09-22 补充完全
```
