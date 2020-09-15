---
layout: post
title: "ML4T笔记---02-01-So-you-want-to-be-a-fund-manager"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

# 01 - Overview
![ ](/assets/images/计算机科学/118382-ebfe42f9cb868c5a.png)

__computational investing__: learning goals to be a portfolio manager.

_basic knowledge_ to know, and _motivation_ depends on type of fund and incentives.
* motivation is probably compensation: depends on the type of fund and how well your fund performs.

> Time: 00:00:27

![ ](/assets/images/计算机科学/118382-d32613933b344764.png)

# 02 - Types of funds
![ ](/assets/images/计算机科学/118382-9ea8c6565d49e7a6.png)

Types of portfolios and their differnces in trading method and visibility:
1. ETFs (exchange-traded funds), 
  * baskets of stocks, even bonds, and other instruments
  * Can buy and sell like stocks: observe their prices in trade day
  * transparent and very liquid: publish their holdings 
2. mutual funds, 
  * similar to ETF: bags of stocks and or bonds, etc
  * But can only buy or sell mutual funds at the end of the day.
  * less transparent: only publish holdings each quarter
3. hedge funds.
  * buy and sell by agreement: hard to exit
  * not transparent: don't ever have to disclose holdings
  * usually marketing by good performance, or describe to clients what their strategy is to attract clients.

> Time: 00:03:04

# 03 - Liquidity and capitalization

![ ](/assets/images/计算机科学/118382-fd115e053f08c716.png)

__liquid __: the ease with which one can buy or sell shares in a particular holding.
  * Stocks are extremely liquid.
  * ETFs are extremely liquid, like stocks. a) easy to trade; b) much dollar value trading in them each day (volume).  ETFs with higher volumes are even more liquid.

__Capitalization__: how much is the company worth. # shares x price.
* large-cap stocks, companies worth is large
* small-cap stocks have a lower value.

__Note__: the price of a stock really only relates to what one share is selling at. It doesn't relate to the overall value of the company.

> Time: 00:02:30

# 04 - quiz: What type of fund is it

![ ](/assets/images/计算机科学/118382-ecda8bd3543dbdd3.png)

What type of the funds are each of these five funds?

__Solution__: 
* VTINX is a mutual fund.
* DSUM is an ETF.
* FAGIX is a mutual fund.
* Bridgewater Pure Alpha is a hedge fund.
* SPLV is an ETF

Mutual funds have short several-letter abbreviations, thousands and maybe even millions of investors.

A hedge fund is just a one-on-one relationship. typically have no more than 100 investors, 

> Time: 00:01:29

# 05 - Incentives for fund managers
![ ](/assets/images/计算机科学/118382-46a79358e4099fd9.png)

How the managers of the funds are compensated is important because the incentivize method might lead the managers to trade or act in certain ways.

Concept:  __assets under management (AUM)__, how much money is being managed by the fund? The compensation is usually a percentage of the AUM.

ETF and Mutual fund managers are compensated to an expense ratio of AUM.
* ETFs: .01% ~ 1%.
* Mutual fund: 0.5% ~ 3%. 
  * ETFs managers only need to follow an index.
  * Mutual fund managers need to be skillful and they can charge a higher expense ratio. (cost of research and also for their skill).
* Hedge funds: __two and twenty __which 2% of AUM, plus 20% of the profits.

Note: the return of a fund in most cases is subject to what happens to the economy or what happens in the markets.

> Time: 00:03:49

# 06 - Two and twenty

![](/assets/images/计算机科学/118382-91f251fd75b0e6da.png)

The 2 and 20 situation example:

a hedge fund manager manages $100 million for a year. The return is 15%. Then the manager will receive

`100 x 0.02 + 15 * 0.2 = 5 million`

Is this 2% apply to 100 million or 115? __it depends on the hedge fund__

The Two and Twenty is very rare now. They're much lower. One and Ten.

> Time: 00:02:03

# 07 - Incentives quiz

What these incentives incentivize you to do?

![ ](/assets/images/计算机科学/118382-ba2f23c0117108c2.png)

* the expense ratio approach and the two and twenty rule both motivate managers to accumulate assets under management.
* the expense ratio approach was not incentivized to take risk to earn more profit, but the hedge fund model is highly incentivized to taking risks and earning more profit for the fund.
  * hedge fund managers are incentivized to take a risk because A) there's not too much of a penalty, and B) if they take a risk and make profits, then they'll be compensated more.

> Time: 00:01:51

# 08 - How funds attract investors
![ ](/assets/images/计算机科学/118382-0702352fdfc50f86.png)

hedge funds have up to 100 investors

__who might your investors be?__ three major types of investors in hedge funds
1. wealthy individuals.
2. Institutions: 
  * e.g.: very large retirement funds, like CalPERS out in California.
  * university foundations
3. funds of funds: they group together the funds of many individuals or institutions.


__the criteria to evaluate a hedge fund__

1. Track record.
2. simulate or back test your strategy, and investors will consider these simulations.
3. compelling story describing that strategy. a reason for why this method works and it needs to make sense.
4. investors consider how your strategy fits within their portfolio.

> Time: 00:03:36

# 09 - Hedge fund goals and metrics

![ ](/assets/images/计算机科学/118382-c8493c2cf2eeb200.png)

__Goals__:

1. beat a benchmark. Outperform a good index. outperform means when the benchmark goes up, your fund goes up more; when the benchmark go down, your fund goes down less.
2. Absolute return funds: means the goal is to provide __positive return__ no matter what.
* long/short: make positive bets in stocks they think are going to go up and make negative bets in stocks are going to go down.

__Metrics__:

* __Cumulative return__: given the funds I started with, how much more did I end up with after a certain amount of time.
* __Volatility__ (the standard deviation of daily returns): how rapidly and aggressively the portfolio goes up and down in value. Lower volatility is better.
* __the ratio of risk to reward __: Sharpe ratio (risk-adjusted reward).

__Recap__:

Hedge funds have goals, typically either to _meet a particular bench mark_ or to _gain absolute return_.

The metrics to judge the funds are 1) cumulative return. 2) Volatility, and 3 risk-adjusted reward or sharp ratio.

__Which benchmarks to choose should depend on the expertise you have.__

> Time: 00:05:49

# 10 - The computing inside a hedge fund

Hedge funds have computationally demanding environments. They have huge databases, significant network connectivity, low latency and high bandwidth connectivity, real-time processing, and so on.

![ ](/assets/images/计算机科学/118382-c32942d33903bdfb.png)

__how hedge funds work__

* we have a certain portfolio (which stocks we have and whether we're in positive or negative positions with regard to them).

* The trading algorithm is interacting with the market, observing the live portfolio. 
  * It tries to get this _live portfolio_ to match some _target portfolio_.
  * the algorithm decides the target portfolio, comparing target with live and then move the live portfolio towards the target, by issuing orders. Those orders get executed (or not), and that updates the live portfolio.
 * it is important not to execute everything at once because large order would affect the price for the stocks. (sometimes it takes days to enter a particular position.)

__how we arrive at this target portfolio__
![Portoflio optimizer](/assets/images/计算机科学/118382-4fe40faa479dd71c.png)

* Portfolio Optimizer takes in a forecast, historical data, and the current portfolio, evaluate the risk and reward and generate a target portfolio.
* Some other considerations that go into Portfolio Optimizer are historical data, open, high, low, close, and volume.

Note: we don't want to exit a stock immediately because we'd be penalized by rapidly selling it.

__How do we come up with this N-day forecast__

![Forcasting](/assets/images/计算机科学/118382-53c3e03836e37296.png)

__forecasting algorithm__, often in the form of a model, a machine learning based model.
* proprietary information
* historical data, and our forecaster crunches all that data to build a model and create a forecast.

> Time: 00:05:56

> Total Time: 00:31:44

```
2019-02-05 初稿 春节快乐
```
