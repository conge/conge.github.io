---
layout: post
title: "Intro to Health Informatics 第三周笔记"
date: "2015-09-07 11:25:21"
categories: 计算机科学
excerpt: "Lesson 3: Health Information Exchange Reasons for establishing HIE Coord..."
auth: conge
---
* content
{:toc}

## Lesson 3: Health Information Exchange

## Reasons for establishing HIE

1. Coordinating care among multiple providers
2. Public health
3. Managing patients at population level.
4. Aggregating data for research

![HIE function](/assets/images/计算机科学/118382-f10bec8622aee58d.png)

## Challenges of HIE faces

1. EHR vendors are not design their systems with each other. **Some standards are needed for data formatting and data transmission**.
2. There is no universal ID for health purpose in the US. **MPI** is needed.
3. Finding patients' information from multiple providers is a challenging task. **Document Locator systems** are needed.

![Fact: lots of EHR venders,  but they were not interoperable, EHR certification has limited requirement on data sharing](/assets/images/计算机科学/118382-ad7d0f922b349f3e.png)

![Unlike France, US does not have national identification for health care. So it's hard to aggregate patients health information](/assets/images/计算机科学/118382-d4f9efa213e74c7e.png)

![Cross enterprise patient identification depends on MPI which uses patient's demographic info and other algoritms to indentify patients](/assets/images/计算机科学/118382-e82139602f807093.png)


![Document locator is need to find patient's health data](/assets/images/计算机科学/118382-63e85c9fffe90767.png)


## HIE Classifications

HIEs can be classified by their *Scope**, **Status**,**Architecture**, and **functionality**

![Scope:Geographic area a HIE covers; Status: where a HIE is at from an idea to full functionality; Architecture: How the system is organized; and Fuction: what HIEs can do](/assets/images/计算机科学/118382-6c562a7890b4e5d0.png)

### Scope of HIEs

![Scope](/assets/images/计算机科学/118382-c67e6e414948054c.png)

* Enterprise HIE(EHIE): Serve hospitals/professionals within on health system.
* Service-area HIE: geographic area or area which health provides/hospitals get their patients from.

The bigger an HIE is, the more challenge it faces. HIE don't naturally want to go bigger because: 1) patients usually only want to stay local, 2) sharing patients with others is not in provider's best interests and 3) **Sustainability and technology** challenges.

## Status of HIE

![EHI's purpose is to improve quality and efficiency of healthcare. It tracks Status of HIE accross the country](/assets/images/计算机科学/118382-2fb2dcee45376d02.png)

![Seven status of HIE: 1. Startup; 2. getting started....](/assets/images/计算机科学/118382-0be680b163f8fe60.png)

## Architecture of HIE

![Architecture](/assets/images/计算机科学/118382-1c1681cd7050310f.png)

## Function of HIE

![ONC classifies HIE by it function](/assets/images/计算机科学/118382-79e467600329a99b.png)

* **Direct exchange**: like the federated model, provide means to send and receive information between providers.
* **Query based exchange**: find and request information from providers.
* **Customer-mediated exchange**: put patients' data under their control.

## the Indiana Health information Exchange (IHIE)

![](/assets/images/计算机科学/118382-f8157eb2c617f703.png)
Major services include:
* **Docs4Docs®**: deliver lab results, reports to physicians. Supports Fax, Web portal or HL7 message delivery.
* **Indiana Network for Patient Care(INCP)™**: a patient-centric community health record. It functions as a virtual EHR and provides data from providers, payers, public health and pharmaceutical vendors. 
* **Quality Health First®**: Population health management system.
* ** ImageZone**SM: cloud-based medical image sharing service. not a permanent storage.
* **AOC Services**: tracking where care has been delivered,; managing transitions of care; following up to ensure care has been delivered as needed.

![](/assets/images/计算机科学/118382-d54f7683f1ece820.png)


![Screenshot of INCP, it looks like one EHR, but the data are from multiple sources](/assets/images/计算机科学/118382-32783b5dd6f2f1be.png)

### Interview with [John P. Kansky](http://www.ihie.org/john-kansky), the CEO of IHIE

** IHIE is an example of centralized HIE**

 Q1. What does IHIE do to solve the sustainability issue  facing the financial challenges most HIEs have:

> A: There are three types of HIEs in terms of funding sources
> 1. State run HIEs: funded by government (through HITECH) by tax money, government grant, etc.
> 2. Private funded HIEs
> 3. Regional interorganizational exchanges: IHIE is one of this type. It charges fees for service, run like a business.

Q2. General intro of IHIE, how IHIE works

> A: IHIE is a non-government, not-for-profit 501C organization. It has a board of healthcare expert, a governance body (which govern the data use). Three management stacks: 1) software development; 2) support, implementation, customer service and 3) IT, infrastructure and administrative.

Q3. How does IHIE coordinating data exchange?
> A: Through APIs, data mapping, systematic normalization of data from multiple source. IHIE then present the information from all sources in a centralized UI (INPC) to the uses. The aggregated data can be used for public health, manage patients at the population level

Q4. What role or view is IHIE taking when facing new technologies such Direct, Federated HIE, RESTful API and FHIR?
> A: IHIE considers itself a centrally managed federated organization since the providers still have control over the data they provided to IHIE. IHIE already uses Direct and pays close attention to the newer technologies emerge from the marketplace.

Q5. Future directions of IHIE 
> 1. more emphasize on providing structured health data for emergency department support.
> 2. Making medication data more available  by removing obstacles of medication data aggregation and sharing.
> 3. Providing more analytic support of data besides sharing them.

> ![ IHIE is supported by Rgenstrief Foundation](/assets/images/计算机科学/118382-cfa9c37e2bde91c5.png)

## CONNECT

![CONNECT is a government provided open source solution for centralized HIE. CONNECT components are modularized (color coded in the figure). It is also the gateway to the proposed national HIE - NHIN](/assets/images/计算机科学/118382-82b99b60adbc819f.png)

* white: CONNECT Components
* Red: customizable Components
* Purple: Replaceable Components

Most of adopters are government supported healthcare providers. Some are private: e.g. Marshfield Clinic from the PGP demo.

## Federated HIE: Direct

Data stays at the source. A classic use case is two physicians share patient's' records via secured email (Fax machine replacement).

![Replacing fax machine. Trust are handled by HISPs. Privacy is handled by getting patient's consent. Security is assured by secure email. If the record is in XML format, the message can be parsed and entered into Dr. Jones' EMR automatically.](/assets/images/计算机科学/118382-070e678306237099.png)


![Sender establishes secure connection to its HISP and send the email with health info. The sender HISP then encrypt the message with recipient's pub key and send the encrypted message to recipient's HISP. Recipient's HISP then decrypts the message with recipient's private key. Then the message is available for retrieval by the recipient. ](/assets/images/计算机科学/118382-1effeeca9c376120.png)

![Quiz 1](/assets/images/计算机科学/118382-d73d59fe57b03729.png)

## Limitation of Direct:
* lack of robust delivery confirmation.
* Trust between HISPs are expensive as the number of HISPs grow: the practical is Direct Trust, a community of Trusts.
* Pull: automatic retrieval of data.
* Automation of physician's workflow

![Trust models](/assets/images/计算机科学/118382-d6d76620924d6eb5.png)


![Quiz 2](/assets/images/计算机科学/118382-9725d511a2f9a3f2.png)

![Proposed solution of direct Pull](/assets/images/计算机科学/118382-8f61d34e83ee4521.png)

1. Patient and Doctor exchange Direct email address.
2. Patient add doctors email to his authorization list (consent)
3. doctor send request to patient's address
4. patient PHR authorize the doctor and perform query in the repository of patient data
5. repository send requested data back via Direct email.


![Automation of physician's workflow: automate the process of selecting data, prepairing and sending email for sender and receiving data, parsing information and data entry to recipient's EMR.](/assets/images/计算机科学/118382-168b2412239cc2f2.png)

## Interview with CurrentCare people

CurrentCare is developed in Rhode Island Quality Institute

### Laura Adams, CEO

Q1. Brief history of CurrentCare

> CurrentCare is a Non-government not for profit. Goal is: quality, safety and value of healthcare. Participated in *[Surescripts](http://surescripts.com/)* (end-to-end electronic prescribing) at its pilot stage. In 2004, it received state grant for health information technology research. In 2009, it received fundings from all three major HITECH grants. 

Q2. Why does CurrentCare use Direct technology?
> There are too many EHRs in the state, implementing APIs for all of them into a centralized model is complicated and very costly in terms of money and time. Point-to-point Direct solution is simple. CurrentCare easily implemented Direct into an automatic workflow.

### Elaine Fontaine, Director of Data Quality and Analytics

Q1. What does CurrentCare do to support providers to achieve quality improvement and quality reporting?
> A: The institute is doing quality measurement for another project outside CurrentCare. It involves collecting and aggregating data about 15 quality measures related to Meaningful Use, providing utilization reporting and patient experience to help clients to see their performance over time and access their success in quality improvement and cost reduction. Same services can be applied to different data source (EHR, HIE, ets).

Q2. Does HIE support data quality and cost analytics?
> A: quality and cost analytics is a challenging task. HIE has data from many sources which might differ from each other. Of course the goal of quality and analytics want to provide reporting on the population level, but we must first understand the data to do so. (in another word, HIE data is too complicated to support population level analytics).

Q3. Is the long goal of CurrentCare to be a "Unified Statewide population and public health electronic reporting system"
> A: basically Yes.

Q4. Will you post Public quality metrics and what will providers think if you do that?
> A: Not so public. The reports were presented to participated providers.

### Charles Hewitt, Director of HIE

Q1. What Privacy model does CurrentCare use?
> A: HIE can not see patient's data without consent. Once patient opted-in, all the data are in the HIE. Patient can choose to give access to 1) all the physicians treating her/him, 2) only emergency doctor, or 3) providers on a white list.

Q2. What percentage of patients fall into echa bucket?
>. A: 1) 95%; 2) 2-3%; 3) 1-1.5%.

Q3. Why CurrentCare do not give options for patient to select what data they want to share?
> A: Physicians want to see all the information before they provide care. Data segmentation is not what physicians want.

Q4. What does CurrentCare do with Direct?
> A:  1) on the inbound side, **automatically** collecting data from providers (e.g. CCD). Participating physician send patient data via Direct to CurrentCare gateway to check if the patient is consented. if yes, the data goes into Currentcare. 2) at outbound side, it sends out alerts via Direct. E.g: Hospital alert: send notification to primary care doctor when patient admitted to hospital. 

### Elaine Fontaine, Director of Data Quality and Analytics

Q1. Future of HIE, take home message about HIE
> Historically, HIE provides information to healthcare providers(physicians, hospitals, care homes……) but focus of care is moving to communities, homes. The future is shifting care to patients. So the future of CurrentCare is to engage patients. Patients might generate lots of data but doctors might not what to see them all. HIE can function as a data filter and monitor and only send out alerts to doctors if something abnormal or wrong with their patients. Or send alerts to relatives when a patient is admitted to hospital or ER.

## Interview with Dr. David Kibbe

### Dr. David Kibbe is the head of [Direct Trust](http://www.directtrust.org/)

Q1. Adoption of Direct Trust
> A: Direct Trust now has 135 memberships , 33 HISPs serving EHRs, HIEs etc... It's now serve 6000~7000 health organizations, more than 250,000 Direct addresses created and the number is doubling every 3 months. (200 EHRs and one million address Projected in early 2015)

Q2. Use case of transition care from hospital to long term care facility
> A: First of all, the main drive of adoption of Direct is meeting the Meaningful Use requirement (e.g. to promote patient engagement). The most used use case is sending referrals to other providers (related to Meaningful Use) and nursing homes (not related). Claim attachment is another use case which is not related to meaningful Use. Also, replacing Fax machine.

Q3. Use case of health department (of Tanasee and Taxus governments) to collect data about STD patients
> A: It's a grass root use case. Clinics in the military are interested in doing things like this.

Q4. Direct role in VDT? 
> A: Provider to Patient health data communication has potential. PHR companies are implementing Direct services. But, it depends on the establishment of provider-to-provider network. We are on the building phase on the provider side.

Q5. Are companies manufacturing health monitoring devices interested in Direct?
> A: Yes. Direct could the be the "last mile" for device to device, device to data center, and data center to provider in box data transmission. 

Q6. What are the challenges that Direct faces for the next  a few years?
> A: Payment and business rationale. Incentive for using Direct Exchange is not strong. Providers and health organizations are hesitating in moving their data or providing data to patients. Direct is essentially a standard, a tool, but it can not motivate people to use it.

## Recap

### Reasons for establishing HIE

1. Coordinating care among multiple providers
2. Public health
3. Managing patients at population level.
4. Aggregating data for research

### Challenges HIEs face
1. Sustainability or business model
2. function and cost trade-off. Centralized HIE can provide sophisticated services with very high cost, federated HIE does not cost as much but will never reach the richness level of services a centralized HIE can achieve.


## Please also read 

* [《Contemporary Health Informatics》chapter 3 summary](http://www.jianshu.com/p/d0190d5fd539).

### Key Concepts/Vocabulary
●Health Information Exchange (HIE) ●Protected Health Information (PHI) ●Centralized architecture ●Federated architecture ●Hybrid architecture ●eHealth Initiative (eHI) ●CONNECT ●Health Information Systems Programme (HISP) ●Public Key Infrastructure (PKI) ●MIME, S/MIME ●LDAP ●DNA ●IMAP ●X509 Certificates

### Readings
* [ONC dashboard](http://dashboard.healthit.gov/quickstats/pages/FIG-Vendors-of-EHRs-to-Participating-Professionals-2014.html)
* [WSJ - Should Every Patient Have a Unique ID Number for All Medical Records?](http://online.wsj.com/news/articles/SB10001424052970204124204577154661814932978)
* [2013 eHI HIE survey results](http://www.ehidc.org/2013-hie-survey-results)
* [HealthIT - What is HIE?](http://www.healthit.gov/providers-professionals/health-information-exchange/what-hie)
* [IHIE Services](http://www.ihie.org/solutions)
* [CONNECT Wiki](https://connectopensource.atlassian.net/wiki/display/CONNECTWIKI/Wiki)
* [CONNECT Adoptors](http://www.connectopensource.org/adopters)
* [5 blog posts about Direct](http://www.cerner.com/blog.aspx?Author=Greg%20Meyer,%20director,%20principal%20architect,%20Cerner)
* [eHealth Exchange Product Testing Program](http://healthewayinc.org/index.php/exchange/product-testing)

### Websites
* [The Direct Project](http://directproject.org/)
* [HealthVault](http://www.healthvault-ppe.com/)
* [Direct Trust](http://www.directtrust.org/)
* [Heal the Way](http://healthewayinc.org/)

```
2015-09-06 初稿
2015-09-07 补充 Interview with Dr. David Kibbe
```
