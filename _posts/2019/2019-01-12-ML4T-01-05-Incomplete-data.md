---
layout: post
title: "ML4T笔记 | 01-05 Incomplete data"
date: "2019-01-12 01:12:12"
categories: 计算机科学
auth: conge
tags: Machine_Learning Trading OMSCS
---
* content
{:toc}

# 1 - Introduction  
![](/assets/images/计算机科学/118382-346072f286d7aa74.png)

* Historical financial data is monitored and recorded by computer and saved for us to pore over later but there are many ways the data can be faulty.

* In this lesson: how missing data can occur and what we can do about it.

> Time: 00:00:27





# 2 - Pristine data
![image.png](/assets/images/计算机科学/118382-f2b67c772c78f8ca.png)

what people think financial data is like.
* perfectly recorded minute by minute.
* price and volume are exactly right.
* no gaps in the data, that we have every single minute recorded.
* data for stocks started since the beginning of time, and they continue to the very last minute.

The reality is that our data is an amalgamation created from many, many sources.
* any particular stock may be traded on different market/exchange over any particular minute at different prices. And it's hard to say who is right.
* there's no single price for any stock at any particular time.
* And different data providers will provide different numbers.
* not all stocks trade every day.
* stocks could come into or go out of existence, stop trading for some time and then come back again at any time, resulting in missing data for the time they don't exist.

> Time: 00:01:56

# 3 - Why data goes missing
![ ](/assets/images/计算机科学/118382-a0130ecf98cecd12.png)

__SPY__ 
* _SPY_represents the S&P 500. It's one of the most liquid and actively traded ETFs and typically used as a time and date reference for other stocks.
* It's been active since 1993. (There are some stocks that go all the way to 1901).

__JAVA__
* Sun Microsystems (trading under the ticker JAVA), was acquired by Oracle in 2010. And on that date, that ticker went away. so it ends at sometime in 2010.
* before JAVA was Sun Microsystems, it was Mr. Coffee. So there are two different time series for JAVA: One for when it traded as Mr. Coffee and another when it traded as Sun Microsystems.
* In the data, when arriving at this abrupt end for JAVA, you'll see __NAN__, meaning not a number, meaning there's no data there.


__what to do about NAN__

## another two example.

__FAKE1__: it didn't exist before a certain time so the FAKE1 data is going to have NAN values before a certain date.

__FAKE2__: it didn't exist before this date, data was absent in between these two dates, and so on. data like this exists for thinly traded stocks.

> Time: 00:04:04

# 4 - Why this is bad - what can we do
![ ](/assets/images/计算机科学/118382-eccea5ba7a6b8a94.png)

### what do we do in situations where we don't have data between two separate dates?
* DO NOT interpolate. because there was no trading. interpolation will wipe out our entire calculation for rolling statistics.
* OK to __fill forward__, fill forward with the last, previous known value. Note there might be a big gap between the filled data and the value of the next real data, but that realistically reflects what was going on with the data.
* interpolation will give ourselves (wrong) information about the future. And that is not allowed.
* filling forward then we're not peeking into the future.

### How to treat missing data at the beginning?

* fill backward.
* When filling data to resolve problems with gaps, fill forward first and fill backward second to avoid, to the max extent possible, peeking into the future.

> Time: 00:03:12

# 5 - Pandas fillna quiz

Pandas `fillna()` function to fill the missing data.

Find the documentation of this function, on [pandas Documentation site](http://pandas.pydata.org/pandas-docs/stable/).

find the `DataFrame.fillna()` function, read and try to understand different options and how to call this `fillna()` function, and  answer

__How would you call `fillna()` to fill forward missing values?__

![](/assets/images/计算机科学/118382-6071ce43a0ab1d75.png)

answer: `fillna(method='ffill')`

> Documentation: [pandas](http://pandas.pydata.org/pandas-docs/stable/)
> 
> Documentation: [pandas.DataFrame.fillna()](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.fillna.html)
> 
> You could also use the `'pad'` method, same as `'ffill'`: fillna(method='pad')



# 6 - Using fillna()
So, let's do some coding.

after reading the csv into the data frame and some plotting.

So now let's go and plot this data and see what turns up.

So, here is the graph.
![](/assets/images/计算机科学/118382-3e8606990dbb9e38.png)

a single statement to fill those gaps: `df_data.fillna(method='ffill', inplace = TRUE)`
* `method='ffill'` corresponds to forward filling  
* `inplace = TRUE` will save all the changes in the same data frame.

![ffill](/assets/images/计算机科学/118382-0921b319af452c16.png)

> Time: 00:01:20

# 7 - Fill missing values quiz

![fillna quiz](/assets/images/计算机科学/118382-b2465dae4a4a0f04.png)

fill these gaps using the fillna() method and yes, it can work for multiple stocks or in that case, multiple columns of the data frame simultaneously.

> Documentation: [pandas.DataFrame.fillna()](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.fillna.html)
> 
> Instructions:
> 
> *   Use **Test Run** to execute the script and view the resulting plot.
> *   Implement **`fill_missing_values()`** to fill any gaps in the data.
>     *   Replace the TODO block (`pass` is just a placeholder).
>     *   Please do not modify anything else in the script.
> *   Use **Submit** to have your solution evaluated. Use Test Run 

> Time: 00:00:34

### solution:

![](/assets/images/计算机科学/118382-89b5713e069514ae.png)
* fill forward first and them fill backward.

> Time: 00:00:30

> Total Time: 00:13:18

```
2019-01-12 初稿 
```
