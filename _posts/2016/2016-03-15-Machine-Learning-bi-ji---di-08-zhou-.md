---
layout: post
title: "Machine Learning笔记 第08周"
date: "2016-03-15 06:41:58"
categories: 计算机科学
excerpt: "注意，第七周是考试周，我其实把考试的的内容压缩进了第06周的笔记中去，所以第七周没有单独笔记。但是所有课堂内容没有缺失，特此声明。 Week 0..."
auth: conge
---
* content
{:toc}

注意，第七周是考试周，我其实把考试的的内容压缩进了第06周的笔记中去，所以第七周没有单独笔记。但是所有课堂内容没有缺失，特此声明。

Week 08 tasks:

- Lectures: unsupervised learning:  clustering and expectation maximization.
- Reading: Chapter 6 of Mitchell, and the supplementary notes on Expectation-Maximization and clustering.

----

![](/assets/images/计算机科学/118382-32a20ea70376fa4d.png)

![](/assets/images/计算机科学/118382-6f07846c46a41101.png)
* Supervised learning: use labeled training data to generate labels to new instances. Can be seen as function approximation.
* Unsupervised learning: make sense of unlabeled data. Data description, when new instance presents, describe it with the generated data description.

## Basic Clustering Problem

![Basic Clustering Problem](/assets/images/计算机科学/118382-5954c5d888ab6ae1.png)

* definition: given set of object X and inter object distance D(x,y) = d(y,x), we can partition the input and put x and y into the same cluster when P<sub>D</sub>(x) = P<sub>D</sub>(y)
* extreme cases: when P<sub>D</sub>(x) = 1, then will be only one cluster; when P<sub>D</sub>(x) = x, then each x is a cluster (each cluster has only one item).

![Quiz 1: Single Linkage Clustering](/assets/images/计算机科学/118382-7ee69e2751971baf.png)

* Single Linkage Clustering: first define each object as a cluster, and then find out the closest two points and merge them ( like kNN). The distance function could be customized. Repeat N-k times can get k clusters
* k is prior knowledge
* quiz, what two points should be linked together next?

![SLC](/assets/images/计算机科学/118382-d7fdf7f062d757df.png)

* the clustering process could be represented as a hierarchical tree structure
* the distance function could be mean, median...

![Quiz 2: Running time of SLC](/assets/images/计算机科学/118382-a88de5e9412e74c6.png)
* For SLC, we need to look at each pair can find the one has the smallest distance and this is a O(n<sup>2</sup>) process. And we need to do this about n times. So the answer is O(n<sup>3</sup>)

![Quiz 3: Problem of SLC](/assets/images/计算机科学/118382-f266128d3802f782.png)
* SLC could not clustering this problem correctly

## K-means

![K-means clustering](/assets/images/计算机科学/118382-3cdb8cdf9d5447ed.png)
* randomly initialize k centers
* each center claims points to cluster the data
* recompute the center by average the clustered points
* repeat above until converge.
* Question: does it always converge?

### K Means in Euclidean Space proof

![K Means in Euclidean Space 1](/assets/images/计算机科学/118382-dfd1196a4d8bf7b1.png)
* Terms: partition, cluster and center

![quiz 4: K Means as Optimization](/assets/images/计算机科学/118382-10422ff912964320.png)
Not sure how to understand the definitions here.

![K-means](/assets/images/计算机科学/118382-4cfd861a55a55f08.png)
* the error can never go up for partition part and re-centering part of the clustering process
* given the that the partition/clustering space is finite, K-means will converge in finite time.

![quiz 4: K-means properties](/assets/images/计算机科学/118382-2d113f34511683cb.png)
* it's possible for K-means to stuck at a local optima, but this can be solved by random restart ( like random hill climbing in the optimization)

## Soft Clustering

![Quiz 6:](/assets/images/计算机科学/118382-5d04b7b99513e03d.png)
* K-means and SLC could not give the point d a definitive cluster
* Solution: lean on possibility :)

![ Soft Clustering](/assets/images/计算机科学/118382-4c4d2730e5c8e392.png)
* here ML is maximum likelihood.

![maximum likelihood Gaussian](/assets/images/计算机科学/118382-50789937b1629e2b.png)
* Hidden variables are used to keep track which Gaussian distribution that x is generated from

![Expectation Maximization](/assets/images/计算机科学/118382-343798d1c3047a39.png)
* there are expectation and maximization for the soft clustering. The probability of X<sub>i</sub> in the <sub>i</sub> cluster is between 0 and 1.
* soft clustering can be converted to K-means if push the probability to be 0s and 1s.

![EM example](/assets/images/计算机科学/118382-4fb3636bdb1e7b54.png)
* given K, randomly generate k centers
* with each iteration, the centers were recalculated and the probability of the each point is in a cluster is also updated until converge.

![Properties of EM](/assets/images/计算机科学/118382-63c98fb6b8872d72.png)
* the reason that EM does not converge is because there are infinite number of configurations.
* Local maxima problem can be solved by random restart
* E, M might be different for different problems

## Clustering Properties

![Clustering Properties](/assets/images/计算机科学/118382-86aae74f2faf42ee.png)

![Quiz 7](/assets/images/计算机科学/118382-63f54274188aadff.png)

![Impossibility Theorm](/assets/images/计算机科学/118382-95f68b2324e24ae7.png)
* It's not possible to have all three properties.

![Recap](/assets/images/计算机科学/118382-478d2f4670efbf73.png)



```
2016-03-02 初稿, SLC
2016-03-14 K-Means
2016-03-15 EM
```
