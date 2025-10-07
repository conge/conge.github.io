---
layout: post
title: "Intro to Health Informatics 第十一周课程笔记"
date: "2015-10-30 13:34:48"
categories: 计算机科学
excerpt: "Lesson 10: Big data Meets Healthcare Big Data The world is awash in data..."
auth: conge
---
* content
{:toc}

## Lesson 10: Big data Meets Healthcare

## Big Data

![Big data](/assets/images/计算机科学/118382-42ee57b0ba6faa02.png)

The world is awash in data. It’s growing at exponential rates. 
* Cesar Hidalgo's definition of big data: data must be big in size, resolution, and scope. 
* for healthcare, data must represent many patients and providers, must do so in detail, and must give the context within which care is delivered and the external rules and policies within which that delivery system must operate. 
* The data must, in summary, be sufficient to represent the behavior of the complex adaptive system we’ve been discussing.

![Quiz 1: big data](/assets/images/计算机科学/118382-9349be4ebdbae90b.png)

![Controlled clinical trial](/assets/images/计算机科学/118382-7fb737f83009cc6a.png)

* Controlled clinical trial is gold standard for developing new medical knowledge. was the . 
* Controlled clinical trial faces difficulties.
  * Finding and recruiting the right patients is hard. 
  * Take a long time,
  * they are expensive. 
* No good alternative approach to replace it.

![Questions the clinial trial could not anwer efficiently](/assets/images/计算机科学/118382-2c2ec4477e039bc3.png)

![](/assets/images/计算机科学/118382-30bc7b3b304efbb0.png)

* Determining optimal treatment would require many alternative experiments. 
* Determining outcomes requires changing the clinical process in half of the clinic.
* These are too costly and complex to do. 
* But best answered through modeling and simulation using digital health data. 

![Quiz 2: Controlled clinical trial](/assets/images/计算机科学/118382-4321b2bc555cf516.png)

## Technique for modeling and simulation

![Decision Trees](/assets/images/计算机科学/118382-0f7ea472caab6611.png)

* __Decisions trees__ are directed graphs; 
* recursion (one-way); time is not represented. 
* In the figure above: generic clinical decision strategy example where different treatment choices yield different outcomes.

![Markov Decision](/assets/images/计算机科学/118382-bbacf36d47100db3.png)

__Markov Models__  
* are also trees
* introduce recursion where steps can be repeated
* time is now represented. 
* However, there is typically no memory so each step is based entirely on the current state of things. 
* there are many paths through the model 
* it is possible to go back to a prior point depending on actions and probabilities.

![Discrete Event Simulation (DES)](/assets/images/计算机科学/118382-48608cef3e8c65c0.png)

In a Discrete event simulation 
* entities and their attributes are represented along with queues where they wait for something typically because of finite resources. 

__Agent Based Simulations__

* richer in attributes than discrete event simulation 
* agents can interact with each other and their environment. 

![Quiz 3](/assets/images/计算机科学/118382-fc008e64cdea71d1.png)

![Quiz 4](/assets/images/计算机科学/118382-da025986298fc8be.png)

## how medical diagnosis and treatment can be improved through analytics

###  Center for Health Discovery and Well Being Case Study

![Center for Health Discovery and Well Being](/assets/images/计算机科学/118382-ba48ff644f1e2a2b.png)

* [The paper](http://pubsonline.informs.org/doi/pdf/10.1287/serv.1120.0022) describing this research project.
* visualization of the agent-based simulation of the Center for Health Discovery and Well Being, 
* The simulation all the clinic personnel and the patients being served move along pathways governed by the time it takes to do each element of the clinic’s work, the available resources and other factors. 
* The simulation was constructed to help the clinic identify a set of processes and a revenue model that would make it both self-sustaining and of value to its parent organization.

## Rahul Basole Interview


## Optimal Treatment of Depression Case Study

![Optimal Treatment of Depression](/assets/images/计算机科学/118382-9917d794edf73857.png)

* [The paper](http://arxiv.org/ftp/arxiv/papers/1301/1301.2158.pdf) describing this research project.
* potential applications of analytics to the determination of optimal treatment. (Optimal means the __best results at the lowest cost__). 
* The example study: A partially observable Markov Decision Process was developed and compared to the actual treatment.
* the model delivered improvements that were better than or almost as good as real physicians but at a better cost per unit of improvement. 
* Read the textbook for more detail

## Early Diagnosis of Congestive Heart Failure Case Study

![Model generation](/assets/images/计算机科学/118382-ed260ff956992530.png)

![Result](/assets/images/计算机科学/118382-9202ff6bfbc3ddea.png)

* [The paper](http://www.research.ibm.com/healthcare/papers/AMIA2012CHF.pdf) describing this research project by Dr. Sun.
* Congestive heart failure earlier diagnosis by analyzing electronic patient records, including free-text patient-reported symptoms. 
* They developed extraction algorithms that used the structured and text components to develop a set of from 10 - 100,000 clinical features. 
* Features were classified using logistic regression (a statistical technique commonly used to predict whether a patient has a condition based on characteristics of the patient) and random forest (a method that uses multiple methods to classify objects) to determine which features were predictive. 
* Features Improve CHF Prediction: the resulting model substantially improves the diagnosis of CHF based solely on medical literature 
* as few as 50 features with high predictive power, based on the model, are added. 

## Interview with Jimeng Sun

![Interview with Dr. Sun](/assets/images/计算机科学/118382-5d6937a0ce15a52b.png)

##  Personalized Cancer Care Case Study

[站外图片上传中……(1)] i
[站外图片上传中……(2)]

* Cancer is a more complex family of diseases with high mutation rate. Selecting the right mechanistic drug for each patient is challenging because treatments (e.g. traditional chemotherapy and recent Mechanistic treatments) are not always working. Precious time and resources (money) are lost if they don’t work.
* Based on a comprehensive model of known cancer biochemical pathways, researchers can now predict the efficacy of treatment.
  * The blue boxes are components and the red circles are their reactions.
  * When genomic data on a patient and on the primary cell types in their cancer, including cancer stem cells 
  * It is now being commercialized by Alacris in Germany.

![Quiz 4](/assets/images/计算机科学/118382-06ee30b96697d264.png)

## How techniques can improve the care delivery system

### Clinical Processes Mining

![Bed choosing](/assets/images/计算机科学/118382-8496971be1367f19.png)

* Configuration of the beds in a hospital’s surgical suite. 
  * preoperative holding area (POHA), 
  * postanesthesia care unit (PACU), 
  * Level 2 recovery).
* Georgia Tech researchers developed a model using medBPM, and showed that using universal beds could serve the same number of cases with around a third fewer beds.

![Processe Mining](/assets/images/计算机科学/118382-cc9e067509ca58fa.png)

* Process Mining answers questions such as:
  * Could we infer the underlying care processes that patients receive as they traverse the complex service areas of the hospital? 
  * Could we identify differences in these processes and the impact these have on outcomes and costs? 
* Process Mining is feasible for the whole healthcare system but small scale research has been done.

### Process mining study of care of ischemic stroke patients in two hospitals. 

![Stroke Care Process in Two Hospitals](/assets/images/计算机科学/118382-719e08ead8341893.png)

* The results indicate significant differences with one hospital using the more state-of-the-art approach aimed at protecting brain cells to limit the damage from ischemia. 
* process mining is an important technology for re-engineering our healthcare delivery system to be safer, more cost effective and ultimately more valuable and responsible component of our society.

![Quiz 5](/assets/images/计算机科学/118382-2209ce8824bbba7c.png)

## Recap and wrap up of the course


* the nature and problems of our healthcare system and the key role that chronic disease plays in it. 
* made the case for digital records and data sharing 
* what the federal government is doing to encourage their adoption. 
* examined the key underlying technologies and looked at how they are being used in actual systems and tools for providers, patients, public health and clinical research. 
* Explored in more detail how data can be aggregated for analysis and concluded with a number of exciting examples of the results that can be achieved.

## Key Concepts/Vocabulary
● Controlled studies ● Decision trees ● Markov Models ● Discrete event simulation ● Agent-based models ● Process modeling

### Readings

* [The Inevitable Application of Big Data to Health Care](http://jama.jamanetwork.com/article.aspx?articleid=1674245)
* [Various Analytic techniques](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/From+Statistics+to+Simulation.pdf)
* [2008 paper by James E Stahl](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Modelling+Methods+for+HTA_Overview_Stahl+2008.pdf)
* [Multilevel Simulations of Health Delivery Systems](http://pubsonline.informs.org/doi/pdf/10.1287/serv.1120.0022)
* [Artificial Intelligence Framework for Simulating Clinical Decision-Making](http://arxiv.org/ftp/arxiv/papers/1301/1301.2158.pdf)
* [Combining Knowledge and Data Driven Insights for Identifying Risk Factors using Electronic Health Records](http://www.research.ibm.com/healthcare/papers/AMIA2012CHF.pdf)
* [Process Mining Techniques: an Application to Stroke Care](http://schonenberg.info/files/SHTI136-0573.pdf)
* [Big Data Revolution In Healthcare](http://www.mckinsey.com/~/media/mckinsey/dotcom/client_service/healthcare%20systems%20and%20services/pdfs/the_big_data_revolution_in_healthcare.ashx)

### Videos

* [Caesar Hidalgo discusses big data](https://www.youtube.com/watch?v=qQCYzc0Gjeg)
* [Dr. Hans Lehrach discusses Cellular Network Model](http://www.molgen.mpg.de/23934/Hans-Lehrach)

### Graphics

* [Cellular Network Model](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Figure+10.4a+Alacris+Cellular+Network+Model.jpg)
* [Cellular Network Model zoom](https://s3.amazonaws.com/content.udacity-data.com/courses/gt-ud514/Figure+10.4a+Alacris+Cellular+Network+Model+zoom.jpg)

### Websites
* [Alacris Theranostics Gmbh](http://www.alacris.de/patient/)

```
2015-10-28 初稿
2015-10-30 完成
```
