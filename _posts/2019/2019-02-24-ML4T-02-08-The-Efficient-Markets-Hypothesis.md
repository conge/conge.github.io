---
layout: post
title: "ML4T笔记 | 02-08 The Efficient Markets Hypothesis"
date: "2019-02-24 02:24:24"
categories: 计算机科学
auth: conge
tags: ML4T Machine_Learning Trading OMSCS
---
* content
{:toc}

## 1 - Our hypothesis
![ ](/assets/images/计算机科学/118382-3cc8e51246332df3.png)

__Assumptions__.

* Technical analysis: assuming that there is information in historical price and volume data that we can discover and exploit in advance of the market.

* Fundamental analysis: assuming there is information in fundamental data, like earnings, that can be exploited and traded upon in advance of the market.

* The efficient markets hypothesis(EMH) says we're wrong about both.

> Time: 00:00:26





## 2 - EMH assumptions
![ ](/assets/images/计算机科学/118382-d62f88433a4a9dfd.png)

* Efficient Markets Hypothesis started from Jules Regnault in 1863.
* Eugene Fama (Nobel Prize) did research in the 1960's, and it became his PhD thesis.

__The assumptions that EMH makes__

1. There are large numbers of investors interacting in the market for profit by finding opportunities where the price of a stock is out of line with what its true value is. Information will move the stock prices
2. New information arrives randomly (random times, random rates for different stocks), but it's constantly arriving. 
3. therefore, the prices are adjusting quickly.
4. The current price reflects all available information.

* all this information that's trickling in is acted upon by the investors, the price adjusts quickly to that information, and the current price reflects all of the information about that stock.

> Time: 00:01:34

## 3 - Origin of information

![ ](/assets/images/计算机科学/118382-86b7fe9dcf417585.png)

But even this is certainly not an exhaustive list. There's many other places we can get information.

1. __Price and Volume__, public. It's rapid, it's quick, everybody can see it.
2. __Fundamental data__, pulbic and reported quarterly and everybody can see it. more to the root of the value of the company 
3. Exogenous data, that's the information about the world that affects the company.
  * e.g. price of oil might affect the price of the airline stock.
4. Information relates to company insiders, secretive but important. It may or may not be legal, but this reflects information that you have that people outside the company do not have.

__types of information and the efficient markets hypothesis__

There are three forms of the efficient markets hypothesis.

> Time: 00:02:21

## 4 - 3 forms of the EMH
![ ](/assets/images/计算机科学/118382-aef45c662e2cdb0b.png)

1. The weak form of the EMH: future prices cannot be predicted by analyzing previous prices. Because
* the current price reflects all information we might know and historical prices can't predict future events.
* It does leave room potentially for fundamental analysis.

2. The semi-strong version of the EMH: the prices adjust immediately to new public information (e.g. fundamental information in quarterly reports).
  * if it is correct, that would seem to prohibit even fundamental analysis.
  * can make money with insider information

3. The strong version of the EMH: can't even make money on insider information.
  * Prices reflect all information, public and private.
  * if it is true, it is essentially impossible to make money by holding a portfolio, other than the market portfolio.

| EMH  | Effect  |
|---------|----------|
|Weak|Technical Analysis won't work|
|Semi-strong |Fundamental Analysis won't work|
|Strong |insider information can't be leveraged to profit |

> Time: 00:02:30

## 5 - The EMH prohibits

__Consider the three forms of the efficient markets hypothesis.Weak, semi-strong, and strong. Which one of these types of analyses or strategies would these corresponding versions of the EMH would prohibit?__
![](/assets/images/计算机科学/118382-6f19a72c6b36b832.png)

> Time: 00:00:31

## 6 - Is the EMH correct
__there is evidence that certain versions of the hypothesis are not correct__.
* Hedge funds do make money off the market through technical analysis.
* The strong EMH is the least solid because it is possible to profit from insider information. The method can provide profit, but it might be illegal.

![](/assets/images/计算机科学/118382-18a9f17ff714cc01.png)

* P/E ratio: price over earnings. lower numbers for P/E ratio are better.
* The historical P/E data showed that price/earnings ratios are very predictive across many, many decades of future returns, and that tends to refute the semi-strong version of the EMH.
> Time: 00:03:27

> Total Time: 00:11:19


```
2019-02-24 初稿
```
