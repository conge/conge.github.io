---
layout: post
title: "ML4T笔记---02-09-The-Fundamental-Law-of-active-portfolio-management"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

## 01 - Overview

![ ](/assets/images/计算机科学/118382-13e50d81c1ebb027.png)

Quotes from Warren Buffett: __Wide diversification is only necessary when investors do not know what they are doing__.

Mr. Buffett is talking about two things, 1) __Investor skill__ and 2) __bre,adth__ (the number of investments).

> Time: 00:00:38

## 02 - Grinolds Fundamental Law
![ ](/assets/images/计算机科学/118382-e5299c849ab6947a.png)

* 1980s, Richard Grinold 

__the Fundamental Law of Active Portfolio Management__.

* performance = skill x $\sqrt{breadth}$ or $IR = IC \times \sqrt{BR}$.
* Thus Two ways to improve performance 1) improve skill, 2) more opportunities for applying that skill.
* measure of skill and some measure of breadth.
  * breadth might relate to how many stocks you invest in, it is the number of trading opportunities.
  * skill relates to your skill in choosing them, is summarized in __Information coefficient__
  * performance is summarized in something called information ratio, 

* __information ratio__ refers to the Sharpe ratio of excess returns: the manner in which the portfolio manager is exceeding the market's performance.

> Time: 00:01:57

## 03 - The Coin Flipping Casino
![ ](/assets/images/计算机科学/118382-8a0da46aba688705.png)

A Coin Flipping is analogous to a single trade in stock: you flip a coin, you get head or tail, you buy a stock and hold it, you make or lose money.

__Here, the coin is biased__: we have information about this coin
* Head probability is about 0.51 
* (the edge is like our alpha when investing in stocks).
* the uncertainty of the outcome is like beta in stock investing.

__even money bet__: bet n coins, If you win you get 2 x n coins; if you lose, your money is taken.
* There are 1,000 betting tables each with their own biased coin, and you have 1,000 tokens.
* Once you've distributed all your tokens, the coins are all flipped at once.
__Is it better to bet all your tokens on just one coin flip, or is it better to bet on multiple coin-flips at once?__

## 04 - quiz: Which bet is better
![ ](/assets/images/计算机科学/118382-ea62752ec75d8cc4.png)

1. you put all of your 1000 tokens on a single table
2. put 1 token on each of the 1000 tables, 

Which one of these is better?

__Solution__: 2 multiple coin-flips

In 1. there's a 49% chance you'll lose all your money 
In 2, there's very little chance you'll lose all your money. Option 2 has a lower risk.

> Time: 00:00:41

## 05 - quiz: Coin flip casino - Reward

![](/assets/images/计算机科学/118382-eb20bf447ff13d54.png)

Reward: expected return.
* in the context of the coin flip casino, bet 1000 chips at once. The expected return is  `winning_chance x bet times` Winning change is 0.51 and losing chance is 0.49 or 49%. multiply this all out and add it up, then our expected return is `0.51 x 1000 - 0.49 * 1000 = $20`.
* What's our expected return in that case of betting 1000 individual chips on 1000 different tables?

__Solution__: still $20.

* $expectedReturn = \sum_{i =1}^{1000}expectedReturn_{table_i}=0.02*1000 = 20$ 
* each of the 1000 bets has 0.51 chance of winning \$1, and 0.49 chance of losing $1.
* the expected return of each bet is 0.02, and we multiply it by a thousand and we get $20.

So the reword of the single betting and multiple betting is the same, so why the multi-bet approach is better?

_RISK_

> Time: 00:00:59

## 06 - Coin-Flip Casino: Risk 1
![ ](/assets/images/计算机科学/118382-6951c7f3acb24606.png)

__Risk as the probability of lose it all: what's the chance you might lose it all?__

*  single bet: there is a 49% chance to lose all in one bet.  this is very high

* multi-bet case: the chance of losing it all $p_{loseAll} = \prod_{i=1}^{1000}p_{i} =0.49^{1000}$
  * It's so small it's not even a number.

> Time: 00:01:59

## 07 - Coin-Flip Casino Risk 2
![](/assets/images/计算机科学/118382-4d47f61104f085c0.png)

__Risk as the standard deviation of all those individual bets__

for the multi-bet: Because for each table, the result is either -1 or 1, so that the standard deviation is easily calculated as 1.0.

* for the single bet of a 1000 tokens: we have 1) 1000 bet on one table and 0 bets on the other tables, turns out a little bit differently. the standard deviation on this event is the same 31.62.

> Time: 00:02:20

## 08 - quiz: Coin flip casino: Reward-risk

![ ](/assets/images/计算机科学/118382-ef6ea87a5edfdd52.png)
 
__Risk adjusted reward__
* it is like the Sharp ratio that we've looked at in other contexts.
* single bet case:  expected return was $20 and our risk was $31.62, `adjusted reward/ ratio = 0.63`.
* for multi-bet case: adjusted reward/ ratio =?

__Solution: `adjusted reward/ ratio = reword/risk = $20/1 =20`
so, A thousand bets is better than a single bet.

> Time: 00:00:28

## 09  - Coin-Flip Casino Observations
![](/assets/images/计算机科学/118382-15e5268298cb2a68.png)

* So bet all 1,000 chips on a single coin flip: the sharp ratio for the single  $SR_{single} = 0.63$
* 1000 times in other words 1 chip on each of 1000 tables, the sharpe ratio is $SR_{multi} = 20$.
*  $SR_{multi} = 20 > 40 \times  SR_{single} $
* In general,  $SR_{n} = \sqrt{n} SR_{single} $ wehre n = number of bets
* this relation above is exactly like the fundamental law of active portfolio management.

Performance is related to skill (how good are you at predicting the future return of the stock) and breadth (by the square root of your breadth).

> Time: 00:02:34

## 10 - Coin-Flip Casino Lessons
![ ](/assets/images/计算机科学/118382-4e24887c5f9e02f6.png)

* The Coin-Flip Casino experiment enabled us to allocate our 1,000 tokens to 1,000 tables.

* We looked at two extreme cases:  1) a small bet on all 1,000 tables, 2) all our money on one table.

* The expected return was the same in both cases, about $20, but the risk was substantially higher for the single bet case. True for both risk to lose everything and risk as standard deviation.

__Three lessons__.

1) higher alpha generates a higher Sharpe ratio. (reword)
2)  more execution opportunities provides a higher Sharpe ratio. (breadth)
3) Sharpe ratio grows as the square root of breadth.

> Time: 00:00:53

## 11 - Back to the real world
![ (/assets/images/计算机科学/118382-3da2aedbe70f4841.png)

let's consider two real-world funds.

1) RenTec or Renaissance Technologies, founded by Jim Simons, a math and computer since professor, and he's had tremendous performance over the last several decades: trades may be 100,000 times per day
2) Warren Buffet, who runs Berkshire Hathaway: holds maybe 120 stocks, doesn't trade much, just holds them.
* Both the funds over the years have produced similar returns.

*  there is a theory that can relate them, it's the fundamental law of active portfolio management.

> Time: 00:01:10

## 12 - IR, IC, and breadth
![ ](/assets/images/计算机科学/118382-8e081edc87ddff70.png)

1. information ratio.
* recall, $r_p =\beta \times r_m + \alpha$. portfolio return is the market component of the return $\beta$  times the market return, plus the residual return $\alpha$.
* alpha is about skill. the Sharpe ratio of this skill component is the information ratio.

* $IC = mean({\alpha}) / std( \alpha) $ Note the risk and reword are calculated by looking back historically at the daily values of alpha.
  * information ration applies in many different cases, not just in this fundamental law case.

The __information ratio is essentially a Sharpe ratio of excess return, this part that's due to skill.__

> Time: 00:02:09

## 13 - IR, IC and breadth cont
![ ](/assets/images/计算机科学/118382-486723a0c210c8af.png)

2. information coefficient (IC), is the _correlation_ of the manager's forecast to actual returns.
3. breadth (BR) represents the number of trading opportunities per year.
* If hold 120 stocks all year, that's 120 trading opportunities.
* if trade 100,000 times per day, multiply that by the trading days in a year, 
* Key is if buy and hold, the number of positions in that portfolio is the number of trading opportunities.

Time: 00:01:10

## 14 - The Fundamental Law 
![ ](/assets/images/计算机科学/118382-3cc7b56f8e993fb8.png)

__the fundamental law as expressed by Richard Grinold__.

* `IR = IC * sqrt(BR)` or $IR = IC \times \sqrt{BR} = mean(\alpha) / std(\alpha) * \sqrt{BR}$

__Proof of the Fundamental Law__

* Since performance is related to skill and breadth of a manager, one can improve the performance by improving a skill or increasing breadth (by applying the skill to more investment opportunities).
* it is a lot easier to increase breadth by finding additional stocks, but please keep in mind, as you increase the breadth, the overall performance only increases as $\sqrt{BR}$.

> Time: 00:01:39

## 15 - quiz: Simons vs Buffet
![ ](/assets/images/计算机科学/118382-f7a8f0c50ee6467f.png)

Assuming that both Simons and Buffet have the same information ratio and that Simons' algorithms are only one 1000th as smart as Buffet and that Buffet trades 120 times per year.

Given that, how many trades must Simons execute in order to maintain the information ratio at the same level as Buffet?

__Solution__: 120,000,000

* $IR_{Buffet} = IR_{Simons} = IC_{Buffet} * \sqrt{120} = IC_{Simon} * \sqrt{TradingTime_{Simons}}$
* So, $TradingTime_{Simons} = (IC_{Buffet}/IC_{Simons} \times \sqrt{120})^2 = (1000 * \sqrt{120})^2 = 120,000,000$
> Time: 00:01:10

> Total Time: 00:25:45

```
2019-03-05 初稿
``` 
