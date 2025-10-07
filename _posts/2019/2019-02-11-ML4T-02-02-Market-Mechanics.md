---
layout: post
title: "ML4T笔记 | 02-02 Market Mechanics"
date: "2019-02-11 02:11:11"
categories: 计算机科学
auth: conge
tags: ML4T Machine_Learning Trading OMSCS
---
* content
{:toc}

# 01 - Overview
What happens when you click buy?

![ ](/assets/images/计算机科学/118382-8166f4866b060ab1.png)
 
> Time: 00:00:14

# 02 - What is in an order
![ ](/assets/images/计算机科学/118382-819aa60485693d89.png)

The components of an order that can go to a stock exchange:
* buy or sell shares?
* the symbol for the stocks or ETFs
* number shares to buy or sell.
* a limit order or a market order
   * market means accepting a good price but essentially whatever price the market is currently bearing.
  * limit price means you don't want to do any worse than a certain price. ( selling with a lowest acceptable price, buying with a highest acceptable price)
* price

> Time: 00:02:44





# 03 - The order book
![](/assets/images/计算机科学/118382-b1c21520f2376596.png)


Each exchange keeps an __order book__ for every stock that they buy or sell.

And here's how it works.

* If one wants to buy 100 shares of IBM with a LIMITED order at price $99.5 and put the order to an exchange, the exchange will publish the information in its order book `BID IBM 99.5`, and the information will be available to the public.

* Say, someone wants to sell 1000 shares of IBM at $1000, the exchange will add the order to its order book as `ASK IBM 1000`

* when someone put a market order, say one wants to buy 100 IBM shares at the market value, the exchange will find the best price in its order book and make the transaction so it can provide the best value to its client.

> Time: 00:02:54

# 04 - quiz: Up or down
![ ](/assets/images/计算机科学/118382-ab5e8ec4bfda4c21.png)

Look at how many shares we have for sale and how many shares people want to buy. is the price of this stock going to go up or down?

__Solution__: Down, because there's much more selling pressure.

* If market buy order coming in, the price will be the lowest among the bid orders in the order book.
* If a market sell order come in, the price will be the lowest among the sell orders in the order book.

> Time: 00:00:52

# 05 - How orders affect the order book

![ ](/assets/images/计算机科学/118382-a56c3bf6f4e94552.png)

* if a market order of buying went in, the exchange will execute the order at the lowest price.
* if there are not enough shares in the lowest price, then the exchange will execute to order shares form the second, third... lowest price to fulfill the order until there is not bid offering anymore.
* if the buying order is a limit order, the exchange will start order from the lowest price, then the second then the third and so on... and stop when the offers are higher than the limit order price. The unfulfilled orders will be in the order book.
* the selling order goes through the same logic.
* the executed prices of a market selling order will be decreasing if there is more selling pressure.
* in real life, the executed prices changes dynamically and rapidly as trades are executed.

![a live order book](/assets/images/计算机科学/118382-0700100ffe7b70d6.png)

> Time: 00:03:31

# 06 - How orders get to the exchange

How do the orders get to the exchange from you.

* You entered an order to buy some stock. The buy order goes over the internet to your broker.

![ ](/assets/images/计算机科学/118382-0de6ca8e1a68108e.png)

__scenario 1__:
* Your broker is connected to several exchanges and determines where to route your order based on information it knows about the exchanges.
  * the exchanges:  New York Stock Exchange, NASDAQ and BATS.
  * the broker queries the computer of the exchanges for the prices.
  * the broker routes your order to the exchange that has the best price.
* Your order enters the exchange, gets executed and the price comes back to your broker and forwarded back to you and you get a confirmation.

Note: each of these exchanges tends to be pretty similar, the prices don't differ much.

![ ](/assets/images/计算机科学/118382-d45d3b1ba34fd7ce.png)

__scenario 2__: order executed internally in a broker

* your broker received your buy order and Joe's sell order of the same stock at the same time. The transaction can be made internally and never reach to exchanges
* This way, the broker doesn't have to pay fees to the exchanges for the transaction.

However, by law, 1) both the seller and the buyer have to get prices that are at least as good as they would've gotten if they had gone to an exchange. 2) And this transaction has to be registered with one of the exchanges.

![ ](/assets/images/计算机科学/118382-8a2b10f59ee9f18b.png)

__scenario 3__:  order filled using a Dark Pool.

* you place a buy order using one broker, Lisa also wants to sell some stock, using a different broker
* Dark Pool: acts as an intermediary between brokerages and exchanges.
  * Dark Pool is looking at the order books of the various exchanges and often making predictions about which direction stocks are going to go.
* Dark Pool: pay the brokers for the privilege to look at the orders before they go to the exchanges and take advantageous trade they see
* the sell might be routed through the Dark Pool from broker two to broker one. And again, the transaction never makes it to the exchanges.
* 80 to 90% of retail traders orders never make it to the exchanges.

The brokerages in the Dark Pools argue that both partners (seller and buyer) in this transaction are getting prices at least as good as they would get at the exchanges on the order books. And the brokers save money.

> Time: 00:04:06

# 07 - How hedge funds exploit market mechanics
 
__Order book exploit__
![](/assets/images/计算机科学/118382-9bb7b21b92ad771e.png)

* hedge funds have co-located computer connected to the exchanges via high-speed internet so they can watch the order books of the exchanges within a very short time. Based on the orders they see, they can predict the pricing trend of a stock.
* For traders that is far away from the exchange and/or have a slower network, it takes a lot more time relative to what the hedge funds need to see the exchange.
* When a trader place order of something that is going up in price, the hedge funds' can make the order before the regular trader, hold the stock for milliseconds (and the price is going up) and sell it to the trader at a higher price.

__Geographic arbitrage exploit__.
![ ](/assets/images/计算机科学/118382-512d015669714ad5.png)

* Exchanges located distance away and prices may drift a little bit up or down.
* a hedge fund can place their own servers at each of these Exchanges and connect them with an ultra high speed dedicated connection.
* When a difference emerges in two locations, the fund will immediately buy in one exchange and sell in another.
* Now these sorts of differences are rare

> Time: 00:04:09

# 08 - Additional order types
![ ](/assets/images/计算机科学/118382-cc0bf33e9acb39d1.png)

* the exchanges only execute buy and sell, market and limit orders.

They don't execute those other types.

Well, you might wonder, okay, how do those other types of orders come into being?

__Orders are implemented by brokers__

* How it works: trader enter this order, the broker holds that order and watches the market. When the conditions are met, the broker sends your order to the market accordingly.

1. _Stop loss_: when the stock drops to a certain price, then sell it.
2. _Stop gain_: when the stock reaches a certain higher price, then sell it.
3. _Trailing stop_: stop loss is triggering price is changing with the current price. e.g. stop loss when the stock price drop $0.1 from the current price. So as the price goes up, the value at which you would want to sell the stock goes up along with the price.
4. __selling short__:  sell a stock short if you believe its price is going to go down.

> Time: 00:01:51

# 09 - Mechanics of short selling: Entry
![ ](/assets/images/计算机科学/118382-ad3488c9ea99c2c7.png)

Example: You want to take a short position in IBM which is currently selling at $100.

1. Joe holds 100 shares of IBM. Joe can lend you his shares to you. Lisa wants to buy IBM.
2. You borrow Joe's share and sell it to Lisa.
3. Now, the 100 share is in Lisa's hands, $10000 is in your account, but you owe Joe 100 shares.
4. Joe may decide he wants his 100 shares back. then you'll have to buy the shares from someone and then give them back to Joe.

> Time: 00:02:04

# 10 - quiz Short selling
![.](/assets/images/计算机科学/118382-aa1e1aaa6219c5cd.png)

__if IBM goes down (as you predicted) to $90, and you decide to exit. Then you submit an order to your broker to buyout those 100 shares at $90. what's your net return?__

__Solution:__ $1000.

> Time: 00:00:20

# 11 - Mechanics of short selling: Exit

![ ](/assets/images/计算机科学/118382-f6c18ae06933e5dd.png)

1. Joe holds 100 shares of IBM. Joe can lend you his shares to you. Lisa wants to buy IBM.
2. You borrow Joe's share and sell it to Lisa.
3. Now, the 100 share is in Lisa's hands, $10000 is in your account, but you owe Joe 100 shares.
4. Joe may decide he wants his 100 shares back. then you'll have to buy the shares from someone and then give them back to Joe.
5. if you want to exit the short position, you buy 100 shares IBM at the market price and return the shares to Joe. your obligation to Joe, is now completed.
6. The broker is executing all the transactions.

> Time: 00:01:44

# 12 - What can go wrong

What can go wrong?

* If IBM went up to $150 per share, and now you want to exit your position, it costs $15,000. but you only got only $10,000 in your account. You will lose $5,000.
* if you bet wrong when you short a stock and the price goes up, you lose money.

> Time: 00:01:17

> Total Time: 00:26:48

```
2019-02-11 初稿
```
