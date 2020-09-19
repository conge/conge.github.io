---
layout: post
title: "Machine Learning笔记 第01周 "
date: "2016-01-23 12:15:05"
categories: 计算机科学
excerpt: "本学期学习Machine Learning。本课程在Udacity上有免费版本，并提供详细的笔记。本文的笔记是超级脱水版，目的是自用。 Week..."
auth: conge
---
* content
{:toc}

本学期学习Machine Learning。本课程在Udacity上有[免费版本](https://www.udacity.com/course/machine-learning--ud262)，并提供详细的笔记。本文的笔记是超级脱水版，目的是自用。

Week 01 tasks
* Lectures: Decision Trees, Regression and Classification, and Neural Networks.
* Reading:  Chapters 1, 3, and 4 of Mitchell

## SL1 Decision Trees

> * [detailed notes](https://storage.googleapis.com/supplemental_media/udacityu/313488098/Lesson%201%20Notes.pdf)
> * [ID3 Algorithm for Decision Trees](https://storage.googleapis.com/supplemental_media/udacityu/313488098/ID3%20Algorithm%20for%20Decision%20Trees.pdf)

![Classification and regression](/assets/images/计算机科学/118382-444865757053bae6.png)

* Classification is simply the process of taking some kind of input,
x, and mapping it to some discrete label.
* And regression is mapping from some input space to some real
number

![Quiz1: Supervised Learning](/assets/images/计算机科学/118382-5e30c92bc2a946de.png)

![Classification learning terms](/assets/images/计算机科学/118382-d596628e5147d365.png)

* Instances is input;
* Concept is the function to generate labels
* Target concept: answer the question
* Hypothesis: all possible concepts?
* Sample: the training set
* candidate: all concepts of the target concept
* testing set
  * TEsting set should never be the same as the training set to show generalization.

![Decision trees](/assets/images/计算机科学/118382-437816e07f715374.png)

* start with the root node
* edges represent different choice
* leaf is final output

![Quiz 2: Representation](/assets/images/计算机科学/118382-c5248d6ef1e8f722.png)

![20 Question](/assets/images/计算机科学/118382-2abe6d687ab77c74.png)

![20 Question algorithm](/assets/images/计算机科学/118382-bad65eb9e947a2d3.png)

![Quiz 3: Best Attribute](/assets/images/计算机科学/118382-a5c4e9ee7270c0ee.png)

![ Decision Trees Expressiveness AND](/assets/images/计算机科学/118382-0c61e4695bb6d130.png)

![ Decision Trees Expressiveness OR](/assets/images/计算机科学/118382-131fac439c3ac236.png)

 ![Decision Trees Expressiveness XOR
](/assets/images/计算机科学/118382-569e7378a4e183a7.png)

* A and B are commutative so that switching the position of A and B on the trees above is OK

![Decision Trees Expressiveness Or and XOR generalization](/assets/images/计算机科学/118382-61092d0ae3a3e27b.png)

* Linear tree: number of nodes = number of attributes
* exponential tree: number of nodes grows exponentially to the number of attributes 

![Decision Tree Expressiveness Quiz 4 and 5](/assets/images/计算机科学/118382-d95bbdf5185bcd82.png)

* the number possible trees can be huge

![ ID3 algorithm](/assets/images/计算机科学/118382-4ac71de57eaa2c81.png)

* information gain:
* What is Entropy? - a measure of randomness。 ∑P(v) log(P(v))

![ID3 Bias](/assets/images/计算机科学/118382-beeb83f79c27a4d1.png)

* The inductive Bias of ID3 is (Preference bias)
  * good splits at top
  * correct over incorrect
  * shorter trees

![Quiz 6: Decision Trees Other Considerations](/assets/images/计算机科学/118382-0f864f06cb177066.png)

* For continuous-valued Attributes, we can group them by a range
* It does not make sense to repeat a discrete-valued attribute, but continuous attribute could be repeated if a different question is asked.

![Decision Trees Other Considerations](/assets/images/计算机科学/118382-e9ad7f01e193efaf.png)

* all attributes are correctly classified: this can't happen if data is noisy.
* Run out of attributes: if attributes are continuous, will never run out.
* No overfitting: pruning.

![Wrap up](/assets/images/计算机科学/118382-5b1c7747e2fcc0a8.png)


----

## SL2: Regression and Classification

> * [Lesson 2 Notes](https://storage.googleapis.com/supplemental_media/udacityu/312357973/Lesson%202%20Notes.pdf)
> * [Linear regression overview](https://storage.googleapis.com/supplemental_media/udacityu/312357973/Linear%20Regression%20Review.pdf)


Recap: Supervised learning: learn from pairs of input and output, then given a new set of input, predict the output. This is mapping input to output. If the output is discrete, it's classification. If the output is continuous, it is Regression.

![Quiz 1: ](/assets/images/计算机科学/118382-fbf35109ad1dcd45.png)

* Originally, regression means regress to the mean

![Regression and function approximation](/assets/images/计算机科学/118382-4172bc5b7cd30236.png)

* regression now means the find the function to represent to the relationship of 2 variables.

![Regression, the best line](/assets/images/计算机科学/118382-1002183f61a74a4a.png)

* the green line is the best fit linear line, but is it the best line?

![Quiz 2: how to find the best line](/assets/images/计算机科学/118382-52312b0ea0e20a99.png)

![Quiz 2:  answer](/assets/images/计算机科学/118382-b9c57a3936a4c903.png)

* the best constant function is the mean of Y.

![Order of Polynomial](/assets/images/计算机科学/118382-b06e73f35b4c44ff.png)

* in the case, the error for order = 8 is zero

![Order of PolyNomial: Error function](/assets/images/计算机科学/118382-0e127045de63bbe4.png)

* Problem: overfitting

![Quiz 3: find best function](/assets/images/计算机科学/118382-d935c4d108638a60.png)

Polynomial Regression


![Polynomial Regression](/assets/images/计算机科学/118382-b242c01792bf492c.png)

![Polynomial Regression](/assets/images/计算机科学/118382-0691537d6f193850.png)
* here shows the polynomial regression represented by matrix and vectors.
* the coefficient is computable

Errors

![Sources of error ](/assets/images/计算机科学/118382-4f198d423fc1cbb9.png)

* Sensor Error: The actual reading was 10, but a moth landed on the sensor so it read 0 instead. 
* Malicious Error: An intelligent malicious agent got in between the measurement and the receiver of the data, they edited the data to say what they wanted it to say, rather than what it actually was. 
* Transcription Error: A machine copied a number from one place to another and it flattened all of the E notation floats to a bare integer. Or a program cast a UTF16 hieroglyphic to a Unicode pile of poo. 
* Unmodeled influences: Suppose we are predicting house prices based on square footage and the number of bathrooms. The house price sold for very low value and the reason was that of an unmodeled influence, that there was mold in the attic and walls. The unmodeled influence caused the Machine Learning to fail at predicting a low house price.


###  Cross Validation

![Cross Validation](/assets/images/计算机科学/118382-e3c215afe3ecb132.png)

* the goal is to generalize to the world, not to fit certain training or testing data set perfectly.
* we need the training and testing data to be IID: independently identically distributed (Fundamental assumption)
* We can split the data into folds and training while leaving one out and use the one for testing. then we average the error of all combinations. Pick the model with the lowest cross-validation error.

![Fitting curve](/assets/images/计算机科学/118382-8adb383c57d74347.png)

![Other input spaces](/assets/images/计算机科学/118382-4085bb769ef5a26b.png)

![Recap Regression](/assets/images/计算机科学/118382-c72fe7ae616dc6f6.png)

----

## SL3 Neural Networks


> * [Lesson 3 Notes](https://storage.googleapis.com/supplemental_media/udacityu/315142919/Lesson%203%20Notes.pdf)
> * [Neural Networks](https://storage.googleapis.com/supplemental_media/udacityu/315142919/Neural%20Networks.pdf)
> * [Gradient Descent](https://storage.googleapis.com/supplemental_media/udacityu/315142919/Gradient%20Descent.pdf)


![Neuro Networks](/assets/images/计算机科学/118382-aa80489937eea476.png)

* A neuron will get input if all the input reach the firing threshold, it will fire

![Perceptron](/assets/images/计算机科学/118382-b42ac629efaacd56.png)

* X<sub>1</sub>,X<sub>2</sub>,... are inputs
* w<sub>1</sub>,w<sub>2</sub>,... are weights
* if the sum of all the weighted inputs is *activation*, if it passes a threshold θ, the output y=1; if not, y=0.

![Quiz 1: output is given inputs and weights](/assets/images/计算机科学/118382-493678d0a0eaa733.png)

![How Powerful is a Perceptron Unit](/assets/images/计算机科学/118382-0dd4048b26303d13.png)

* weight matters a lot when deciding the line to split the plane.

![Quiz 2: Neural network can represent AND ](/assets/images/计算机科学/118382-e77f97cd2d687a9d.png)

* When X<sub>1</sub>=0 and X<sub>2</sub>=0, y=0
* When X<sub>1</sub>=0 and X<sub>2</sub>=1, y=0
* When X<sub>1</sub>=1 and X<sub>2</sub>=0, y=0
* When X<sub>1</sub>=1 and X<sub>2</sub>=1, y=1; so y represents AND

![Quiz 3: Neural network can represent OR](/assets/images/计算机科学/118382-75ebb55e2d31382d.png)

![Quiz 4: Neural network can represent NOT](/assets/images/计算机科学/118382-48878c8b06e86f86.png)

![Quiz 5: Neural network can represent XOR](/assets/images/计算机科学/118382-0cb9b34763141bfd.png)

* XOR = OR - 2 \* AND

### Perceptron Training

![Perceptron Training](/assets/images/计算机科学/118382-e07a714664c561d7.png)

![Perceptron Training](/assets/images/计算机科学/118382-495afe39b1a55e7b.png)

* the Perceptron Rule updates weight with weight_change ( Δw<sub>i</sub>). ( Δw<sub>i</sub>) is defined by the learning rate, the difference between target and output and input.
* if the data is linearly separable, Perceptron rule will find it, in finite iterations ( but it's hard to know how many iterations are needed)

![ Gradient Descent](/assets/images/计算机科学/118382-7fbfba00424d3c2e.png)

![Quiz 6: Comparison of Learning Rules Quiz](/assets/images/计算机科学/118382-9107e823511125eb.png)

![Sigmoid](/assets/images/计算机科学/118382-0555904869603df1.png)

![Neural Network](/assets/images/计算机科学/118382-d1dfa79405009549.png)

![ Optimizing Weights](/assets/images/计算机科学/118382-7c8ac8f186a73fbc.png)

![ Restriction Bias](/assets/images/计算机科学/118382-5fef7108a371a82f.png)

 Preference Bias

![Preference Bias](/assets/images/计算机科学/118382-289df1980dbd6ff2.png)

* Preference bias tells you something about the algorithm that you are using to learn. 
* Prefer simpler explanations
* do not multiply unnecessarily ( not fitting the data).

### Summary

![Summary](/assets/images/计算机科学/118382-d95ed6e37ad5faff.png)

这些内容本该是Jan 11 – 17, 2016之间完成的，但是因为准备面试，拖到了一周之后。于是不得不一周补两周的内容。现在去看本周内容了……下次不要拖了，一拖就压力陡增啊。

```
2016-01-21 看到 Cross Validation in SL2
2016-01-22 继续SL3，初稿完成。
```
