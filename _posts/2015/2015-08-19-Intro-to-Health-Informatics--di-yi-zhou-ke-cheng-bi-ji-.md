---
layout: post
title: "Intro to Health Informatics 第一周课程笔记"
date: "2015-08-19 03:55:53"
categories: 计算机科学
excerpt: "美国医疗系统简介 美国的医疗保险系统大概有两种，一种是PPO一种是HMO。HMO要求参保人必须有一个全科医生，看专科医生必须由全科医生推荐转诊。..."
auth: conge
---
* content
{:toc}

![Introduction to Health Informatics](/assets/images/计算机科学/118382-4252639142bcfca3.png)


 ## 美国医疗系统简介

美国的医疗保险系统大概有两种，一种是PPO一种是HMO。HMO要求参保人必须有一个全科医生，看专科医生必须由全科医生推荐转诊。而PPO则无此要求。

PPO的部分与中国的类似，就是身体哪里有病就看那一科的医生。肝有病，看肝病专科，哮喘看呼吸道专科。只要挂得上号（当然美国这边是预约制），随便你看什么医生，在保险条款允许下，随便你做什么检查。

HMO的部分和中国不同，要求每个人有一个全科医师（Primary Care Physician，PCP）。PCP相当于过去的家庭医生，人有什么病先去看全科医生，全科医生能解决大部分的问题，小到头疼脑热，大到癌症的日常养护。全科医生解决不了的，会将病人转到专科医生那里去。如果病人有多种疾病，比如高血压，肥胖，心脏病，不同的专科医生将负责治疗他／她所胜任的那一方面的疾病。而全科医生负责掌握病人健康状况的全局，并协调治疗。与PPO相比，HMO能更有效的控制医疗花费。

HMO遇到的问题是全科医生的短缺。全科医生收入比不上专科医生。医科学生付出一样的时间和金钱成本的情况下，更愿意成为专科而不是全科医生。当然，计算机科学对此帮不上忙。

HMO与PPO遇到的共同问题是，医生之间对病人情况的交流很不顺畅。HMO还好，有一个全科医生作为中转。PPO网络的每个医生之间互相联系非常少，对病人缺乏全面的了解。对病人健康信息的掌控，依赖于病人本身，而没有一个专业的人或者系统帮助病人管理和分析其自身状况。计算机科学家所研究的健康信息学会对此有很大的帮助。这也是这门课的主要内容。

## 健康信息系统面临的挑战和机遇

无论是哪一种情况，慢性病病人在治疗过程中，平均要见十四个医生，而每个医生对病人的了解，都得通过其病历进行。传统的病例都是纸的，每个门诊自行管理。病例记录（以及这种化验，诊断记录等等）在病人在不同医生那里流动时，往往不容易交流。随着科技的发展，越来越多的医院、门诊开始将纸的文件数字化，信息化。但是不同门诊医院之间的信息交流，基本还停留在纸上（传真、信件目前还是主流的病历传递手段）。

从病人角度来讲，自己的健康文档的管理，也都完全的交给了医院和医生。想了解自己医疗历史和当下状况，病人必须咨询医生。目前的健康信息系统是对病人完全不友好的。原因之一是所有的健康信息系统的用户都是医生、诊所和医院，不同的机构采用的信息系统各不相同，互相也不兼容。针对个人的信息管理系统，基本没有。Google多年前曾经有一个Health服务，但是由于种种原因，最终停止运行了。

医疗行业有钱赚。美国目前GDP的20%都花在了对医疗的各种补助上。最近几十年来，政府用于医疗上的花费有成指数上升的趋势。我所在的小城，医院是当地最大的雇主。随着人口老龄化和美国人不健康的生活方式，美国越来越多的人开始患上慢性疾病。为了给病人提供更好的医疗服务，给医生提供便捷的健康信息收集分享系统，同时降低花销，政府开始重视建立起高效医疗信息系统。健康信息系统面临机遇。

## Supplementary Materials

[061/100 《Contemporary Health Informatics》第一章](http://www.jianshu.com/p/430cde8303a5)

### Key Concepts/Vocabulary

● Rescue Care ● Acute disease ● Chronic disease ● Organisation for Economic Co-operation and Development (OECD) ● Health Maintenance Organizations (HMOs)

### Readings

* [The growing burden of chronic disease in America.](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1497638/) <- Recommended at least 3 times in Lesson 1
* [Better to BEST (PDF)](http://www.pcpcc.org/sites/default/files/media/better_best_guide_full_2011.pdf)
* [Shortage of Doctors an Obstacle to Obama Goals](http://www.nytimes.com/2009/04/27/health/policy/27care.html)
* [The Cost Conundrum](http://www.newyorker.com/magazine/2009/06/01/the-cost-conundrum)
* [Commonwealth Fund - How ACA Will Strengthen Primary Care Reform (PDF)](http://www.commonwealthfund.org/~/media/Files/Publications/Issue%20Brief/2011/Jan/1466_Abrams_how_ACA_will_strengthen_primary_care_reform_brief_v3.pdf)
* [Commonwealth Fund - 2011 International Survey of Patients with Complex Care Needs](http://www.commonwealthfund.org/publications/in-the-literature/2011/nov/2011-international-survey-of-patients)
* [Commonwealth Fund - 2011 International Health Policy Survey of Sicker Adults](http://www.commonwealthfund.org/about-us/events/2012/international-health-policy-survey)
* [RAND Research Report - Factors Affecting Physician Professional Satisfaction and Their Implications for Patient Care, Health Systems, and Health Policy](http://www.rand.org/content/dam/rand/pubs/research_reports/RR400/RR439/RAND_RR439.pdf) (Chapter 7)
* [CS 6440 Team Project Instructions (PDF)](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/CS+6440+Team+Project+Instructions.pdf)
```
2015-08-17 初稿
2015-09-07 添加 Supplementary Materials
```
