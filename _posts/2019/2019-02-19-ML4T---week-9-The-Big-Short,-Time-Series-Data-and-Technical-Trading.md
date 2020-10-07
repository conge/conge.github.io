---
layout: post
title: "ML4T | week9 The Big Short, Time Series Data and Technical Trading"
date: "2019-02-19 02:20:20"
categories: 计算机科学
excerpt: "This week, you should watch ... well, no lessons, but a few video..."
tags: [ML4T, Machine_Learning ]
auth: conge
---
* content
{:toc}

**This Week's Lessons.**

This week, you should watch ... well, no lessons, but a few videos: [The Big Short](https://www.youtube.com/watch?v=j13KSg4l9gM), [Time Series Data (First 30 Minutes)](https://www.youtube.com/watch?v=2e2Yr-Bpo-w), and [Technical Trading](https://www.youtube.com/watch?v=2e2Yr-Bpo-w).

* [Slides](http://quantsoftware.gatech.edu/File:CDB_vectorize_me.pptx) for Technical Trading

> the videos are hosted on Youtube.

__Project 5__ [Video](https://www.youtube.com/watch?v=1ysZptg2Ypk)

![Project 5 Video](/assets/images/计算机科学/118382-047806bc147f51db.png)

Here is the process to create a market simulator
1. construct a df_prices to record the prices (adjusted close price) for each trading day for each stock in the portfolio. Add a cash variable in the data frame and set the value for cash to $1.
2. construct df_trades to hold all the tradings. Make sure to get the value of the "cash" column correct.
3. df_holdings: the number of stocks and cash for each column.
4. df_value: = df_prices * df_holdings.
5. df_port_val: = sum of the df_value.

-----

# [Time Series Data (First 30 Minutes)](https://www.youtube.com/watch?v=2e2Yr-Bpo-w)

![](/assets/images/计算机科学/118382-936242d20b5279c3.png)

* When using technical indicators to predict stock prices, we usually use X in the indicators to predict the price of several days later.
* To construct a dataset for this, we can pair `Y` on  `t` and X on `t - n` to get an X-Y pair for the model building.
* usually, we split the data into a training set and a testing data. And the testing data should always be gathered later than the training data
  * building model with later data and testing on the former data will bias the result because the "now" is influenced by history. 

__Backtesting to Validate the Model__

![](/assets/images/计算机科学/118382-f3d3937c5fa3d058.png)

1. go back to the beginning of the data, select a chunk of them for training and building the model; Based on that model, make a Forecast towards the future (n days ahead), then make a trade decision.
2. Then skip the train and forecast period, select another chunk of data to repeat step 1.

This process is called _Roll forward cross validation_ or _Out of sample validation_

In this method, we can only use the slice of data in the future for testing. because _it is easier to predict past than predict the future_


## 10 Ways that backtest can go wrong.

### 1. In sample backtesting
![](/assets/images/计算机科学/118382-d6ec6bced89bf462.png)

* __description__: train and test the model using the same dataset.
* __problem__: the in sample error will be small.
* __how to avoid__: get different dataset for training and testing purpose. e.g. train on 2007 data and testing with 2008+ data.

### 2. survivor bias

![image.png](/assets/images/计算机科学/118382-c145865e46096ff7.png)
* __description__: As time goes, participant of an experiment might drop from the study. the final results can only be measured from the participants who are still in the experiment
* __problem__: as seen in the graph above, the green line, which is the S&P 500 performance with the current members (survivors), the purple line is the S&P 500 using the membership from the beginning of the data. The green line has overestimated the return ( or price of the index).
* __how to avoid__:  1) use the historical membership; 2) use SBF (survivor bias free) data 3) use the indices as the universe for testing. 

### 3. ignore the market impact
![](/assets/images/计算机科学/118382-3afee1aec718acac.png)

* __description__: The historical data has no information about your trading. but your trading might affect the price of the stock you trade. Ignoring this will lead to an inaccurate prediction 
* __problem__: When taking action based on a prediction, the stock price at the trading period might affect the performance of the stock because of your live trading.
* __how to avoid__:  include a "slippage" or "market impact" model when back testing.

----
## Case Study in Vectorization of Technical Strategy Python Code

![](/assets/images/计算机科学/118382-4f4e24d6f5d513a5.png)
* note: we have the code in project 5 to read in order files and calculate portfolio value.

![ ](/assets/images/计算机科学/118382-6cc5c71fad56b8f8.png)

- Relative strength index([wiki](https://en.wikipedia.org/wiki/Relative_strength_index#Calculation)) can be used to predict oversold and overbought

![](/assets/images/计算机科学/118382-5109b8c376083fdb.png)
In the graph above, there are
- SMA (the brown line)
- Bollinger Bands ( the red lines)
- Relative strength index ( the black curve below the bar graph)

![strategy](/assets/images/计算机科学/118382-ea1dc06702650085.png)
![](/assets/images/计算机科学/118382-09058e9f46139259.png)

## the easy but slow way of calculating the indicators
![](/assets/images/计算机科学/118382-3e897303f51d8d41.png)

![ ](/assets/images/计算机科学/118382-8febc0c3d9bbc84b.png)

The above method is a correct way of doing the calculation. However, it is very slow to calculate the needed statistics using the method.

> real    5m24.461s
> user    5m24.281s
> sys     0m0.185s

![ ](/assets/images/计算机科学/118382-dfd359c318cec086.png)

Solution: vectorize the calculation.[ Here](https://mega.nz/#!n6whwKJY!4TGN5IuBogUqWSPF1rMrMVRluUJ50kNjrB6RmBir85k) is the PPT used in the video

----

 
