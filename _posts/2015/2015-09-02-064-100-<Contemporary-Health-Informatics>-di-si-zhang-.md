---
layout: post
title: "064-100 《Contemporary-Health-Informatics》第四章"
date: "2015-09-02 09:02:02"
categories: 阅读
excerpt: "个人健康信息，也必须受到保护。这些信息首先是个人隐私。其次，这些信息可以拿来牟利，骗取保险公司和政府的保险金，造成纳税人的损失。本章讲述HIE系统需要的两个重要功能：获取病人授权和如何对信息加密解密。需要注意的是，保证信息的隐私、安全和信任，技术只占20%， 80%的是工作是制定各种policy..."
auth: conge
tags: 读书笔记 
---
* content
{:toc}

> ![Contemporary Health Informatics](/assets/images/阅读/118382-aa432bd3d772d66a.jpg)

> 图书信息：[豆瓣](http://book.douban.com/subject/26601196/a0)

就在上一周，著名的偷情网站用户信息被黑客公开，不知道有多少人上去搜索自己配偶的电子邮件，这又加速了多少家庭的破裂。近些年来，经常听到信息被盗的新闻，银行账户被盗，个人身份信息被盗，各种事件层出不穷。IT行业面临最大的问题，恐怕就是信息安全了。

个人健康信息，也必须受到保护。这些信息首先是个人隐私。其次，这些信息可以拿来牟利，骗取保险公司和政府的保险金，造成纳税人的损失。

本章讲述HIE系统需要的两个重要功能：获取病人授权和如何对信息加密解密。需要注意的是，保证信息的隐私、安全和信任，技术只占20%， 80%的是工作是制定各种policy。

以下为书主要内容。

----

> Part II: Key technologies
> Chapter 4: Privacy, Security and Trust 

## Overview

PHR has a low use rate (1 out of 14) and one of the concerns that  users have is the security of their health information (another major concern is the reliability of the system). Internet criminals are interested in health data because they can use them to file false claims to get money. Public health officials, health professionals and others were sometimes reported to breach the HIPPA law to get access to protected health information.

PHR, EMR and HIE must address the privacy, security and trust concerns.

**Privacy**: only people authorized by patient can see health data. 
**Security**: data is protected from unauthorized access.
**Trust**: senders and recipients of health information knows that the people they are interacting with are who they say they are.

To ensure privacy, prior authorization of the data owner is required before doing anything. To address security, a public key infrastructure (PKI) is commonly used. To ensure trust, a third-party trusted organization is usually provide the identification service to certify users of the system.

Challenges：

* how patient can specify data to share, can the patient be confident that only the specified data will be share?
* How can patient remain control of the shared data.
* how can the providers trust the validity of the data shared by patient
* how can the provider be sure the person who send the data is the patient

## Privacy and Data Segmentation

Privacy models
*  **"no consent"**: data use was automatic, patient has no control
* **Opt-out model**: patients are sharing their data unless they ask not to.
* **Opt-in model**: No patients' data are allowed to share unless they consented to. It's an all-in or nothing model.
* ** Opt-in with restrictions**: Patient's consent must be obtained before data sharing, and patients have control over sharing what data with whom. This needs the support of data segmentation.

**Data Segmentation**: is the process of sequestering certain data elements that are perceived as undesirable to share.

Three models of Segmentation:

* **Patient-controlled**:
* **Physician-assisted**:
* **other models**: Organization-controlled, hybrid, innovative tools.

## Security and Trust (in the context of Direct)

** 3 Concepts of Public Key Infrastructure (PKI)**
* Paire of public and private keys, 
* difference between message and electronic signature
* functions of registration authority(RA) and certificate authority(CA).

### Public and Private Keys

Public and Private key pair are related sequence of numbers. Private key can not be public otherwise it can not assure security.

Both public key and private key can be used to encrypt message. Using receiver's public key to encrypt message will make sure only the one with the receiver's private key can see the message. Using sender's private key to encrypt message can ensure the message is indeed sent by the sender. The private key now functions as part of a digital signature because it can only be decrypted by the sender's public key.  it will not reveal the private key.

### Trust and Digital Signatures

Digital signature is usually based on the outgoing data so it is virtually unique. The signature must be encrypted with sender's private key before sending out. The receiver can then decrypt the signature with sender's public key to reveal the signature. These steps can ensure the message is indeed from the sender and the message is valid.

RA is important because it is responsible to generate private key and public key for a provider after verifying their identity.

### Policy Issues

Since patients are accessing HIE or HISP via PHRs, it's hard work to verify every patient by RA. Policies is more important in the scenario.

### PKI on the Web

It is very similar to what the public/private keys usage. I will simplify the knowledge with two questions below:

**Q**: For example, I want to sent a secure email via gmail. How do I (my browser) do that?

* **A**: Establish HTTPS connection, receive Google public key, encrypt the message using the key and send it back to Google.

**Q**: How do I know the key are from Google?
* **A**: On the internet, there are agencies like RA do the work to verify websites and public keys of the sites. After verification, they encrypt the keys with the agencies private key. Google will send you this version of keys to browse. And browsers keep a copy of the agencies' public keys, so it can decrypt those keys and verify they are from a trusted source. 

### Other PKI questions

* PKI works partly because the generating of keys is time consuming.
* Validation for the certificate needs to be more comprehensive
* Simplified version of public/private keys are available (e.g. the Pretty Good Privacy, PGP), but might not be enough for use in healthcare.
* If computing power becomes very powerful, e.g. quantum computing, PKI needs modification.

PKI is not foolproof, private keys can be stolen, attacked, one can swap another people's public key with his to get access to messages which were intended to send to that person. Data security is a sophisticated field.

## Conclusion

Internet is not designed for security. Digitizing data and sharing them via internet securely needs a lot of policy work and technology support.

## 扩展阅读

[Intro to Health Informatics 第四周笔记](http://www.jianshu.com/p/86912223d821)
```
2015-09-02 初稿
2015-09-08 添加扩展阅读链接
```
