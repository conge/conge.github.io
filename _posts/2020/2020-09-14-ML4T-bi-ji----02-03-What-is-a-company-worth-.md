---
layout: post
title: "ML4T笔记---02-03-What-is-a-company-worth-"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

# 01 - Overview
![Dollar printing company](/assets/images/计算机科学/118382-0ef702a79db80072.png)

A company can take raw materials, and process them, and turn them into dollars. and each year, this company can output a dollar bill reliably.

What is this company worth?

> Time: 00:00:44

# 02 - Quiz: What is a company worth

![What is the dollar printing company worth?](/assets/images/计算机科学/118382-d74e0a31d6e76594.png)

> Yes, the value of one dollar would typically reduce over time, and the sum of the individual $1's generated every year would converge to a finite value.

# 03 - Why company value matters
![ ](/assets/images/计算机科学/118382-18eda858f93e305b.png)

__why does it matter how much a company is worth?__

* Company has its true value, which is distinct and different from the value estimated by the market.
* The market value of the stock goes up and down, sometimes below the true value, sometimes above.
* We want to buy a stock when the price is too low and we want to sell it when it's too high.
* When market price >> true value of the company: __selling opportunity__; market price << true value of the company: __buying opportunity__.

__estimate the true value of a company__
* __intrinsic value__, estimated by future dividends. dividends accumulated over all of the future
* __book value__, based on the assets that the company owns.
* __market cap__, based on the value of the stock on the market and how many shares are outstanding.

> Time: 00:03:30

# 04 - Quiz: The Balch Bond

![ ](/assets/images/计算机科学/118382-a36759ed15ca2e1e.png)

Consider three assets: 1) a dollar bill (you can get it today); 2 the Balch bond that promise to give you a dollar in a year, and 3) US government bond that gives you a dollar in a year.

__assuming that they cost you the same today, How would you rank these three assets?__
* Rank: 1 = most preferred option, 3 = least preferred.

Solution: $1 right now is the best because it is guaranteed and you can use it or invested it now. US government has more credit in this example (not always, in my opinion)

> Time: 00:00:45

# 05 - The value of a future dollar
![ ](/assets/images/计算机科学/118382-9a2a074c55601a1a.png)

* the value of a dollar delivered in the future is worth less than a real dollar right now.
* risk and interest rate.
  * PV = FV / (1 + IR)<sup>i</sup>. PV = Present value; future value= future value; IR = interest rate; _i_ is how far into the future this payment is going to be delivered.
  * e.g.: the value of a $1 bill delivered in 1 year from now, at a 1% interest rate is 0.99 dollar.
  * private company offer bond with higher interest rate than government to attract investors.e.g. in order to attract clients to buy my promise for $1 in the future, I could only charge you $0.95 at a 5% interest rate.
* so a dollar in the future will exponentially decrease the value, private bond decrease value faster than government (more trustworthy) issued bond
* the higher interest rate assets, they decrease further into the future.

> Time: 00:05:07

# 06 - Intrinsic value
![ ](/assets/images/计算机科学/118382-3df8fc6e3c559441.png)

* Intrinsic value relates to the dividend which is money a company promise to pay you in the future (every quarter or every year) if you own its stock. This is very much like the Balch bond.
* We can use PV = FV / (1 + IR)<sup>i</sup> to estimate the future value of the dividend but IR is a question. 

__The problem is which IR to use.__
* interest rate relates to is how risky the company is.  you need to expect that the company is going to pay you more in the future 
* the discount rate (DR). higher if you think it's riskier, lower if it's more certain to pay you that dividend every year.

Intrinsic value is the value of the dividend one excpect to receive in the future. So we need to estimate the PV of dividend for year 1, 2, 3,..., infinity.
* PV = FV/(1+DR) <sup>1</sup> + FV/(1+DR) <sup>2</sup> +FV/(1+DR) <sup>3</sup> +...  = __FV/DR__.
* This equation above tells us the intrinsic value of the company.

> Time: 00:04:27

# 07 - Intrinsic value quiz
Let's check your knowledge now.

Consider a company that pays $2 per year in dividends and a discount rate of 4%.

What is the intrinsic value of this company?

__Solution__: 2 / 4% = $50.
> Time: 00:00:18

# 08 - Book value
![image.png](/assets/images/计算机科学/118382-2913da879f9578ac.png)

__a classic definition of book value__: total assets of the company.

* Total assets = all assets - intangible assets - liabilities.
  * Intangible assets are things that are difficult to put a price on. E.g. a brand, or a pent,...
  * Liabilities: loans etc.

__an example company__

* 4 factories x \$10 million = 40 million  
* 3 patents * \$5 million = 15 million  
* the liabilities = \$10 million.    
Note that patents are intangible
So, BV =  \$40 million -  \$10 = \$30

> Time: 00:02:06

# 09 - Market capitalization
![](/assets/images/计算机科学/118382-c14ab4beef4fbb38.png)

 Market Capitalization is the number of shares that are outstanding times the price.

> Time: 00:00:30

# 10 - Why information affects the stock price
![ ](/assets/images/计算机科学/118382-d7a1bfd0a69ddf33.png)

Primarily because news affects the expectation of future dividends (amount of the dividends and/or the probability of getting them).

* bad news reduces the expectation and the good news increases it.

Three types of news:
1. company-specific news: "CEO ill "only affect the stock price of the company
2. Sector-specific news: "Island soil bad" affects all the companies in this sector.
3. market-wide news: "See level rising" affects all the companies in the market.

> Time: 00:03:14

# 11 - quiz: Compute company value
![ ](/assets/images/计算机科学/118382-f0489cbe4eaf8ad6.png)

 would you buy that stock given the information?

 * an airline owns ten airlines worth 10 million each. Its brand name is worth 10 million, and it's got a liability of 20 million. (book value).

* it pays $1 million per year in dividends assuming a 5% discount rate. (intrinsic value)

* there's one million shares outstanding and $75 stock price (market capitalization).

__Solution__
* book value = 10 * \$10 - \$20 = \$80 million.
* Intrinsic value = \$1 million / 5%. = \$20 million.
* market capitalization = $1 million x 75  = $75 million.

>Time: 00:01:37

# 12 - quiz:  Would you buy this stock
So let's go back to that original question.

Assuming this company has a book value of $80 million, an intrinsic value of $20 million, and a market cap of $75 million.

__would you buy this stock?__

Yes.

You should absolutely buy the company because if you buy it for \$75 million and sell all of its individual assets for \$80 million, the net return is an immediate \$5 million.

> Time: 00:00:46

# 13 - Summary

![ ](/assets/images/计算机科学/118382-c15a931ba1983ef5.png)

* Intrinsic value, which is based on future dividends.
* Book value, which is the value of the company if we split it up into pieces and sold those individual pieces.
* Market capitalization which is simply the value that the market is placing on the company.

So, many stock trading strategies 
1. if the intrinsic value drops significantly and the stock price is high, it may be worthwhile to short that stock.
2. if dividends are going up, and the market capitalization is low, it might be an opportunity to buy the stock.
3. book value provides the lowest price. we can pretty much assume that the price is not going to go below book value or a predatory buyer would buy the whole company and break it up for parts.

> Time: 00:01:35

> Total Time: 00:28:42

```
2019-02-16 初稿
```
