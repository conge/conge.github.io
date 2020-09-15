---
layout: post
title: "Machine Learning笔记 第03周"
date: "2016-01-28 00:19:15"
categories: 计算机科学
excerpt: "Week 03 tasks： Lectures:  Kernel Methods & SVMs as well as Computational..."
auth: conge
---
* content
{:toc}

Week 03 tasks：
- Lectures:  Kernel Methods & SVMs as well as Computational Learning Theory.
- Reading:  the tutorials on SVMs, as well as the relevant portions of Mitchell Chapter 7 for Comp. Learning Theory.

## SL6: Kernel Methods and SVMs

> * [Lesson 6 Notes](https://storage.googleapis.com/supplemental_media/udacityu/386608826/Lesson%206%20Notes.pdf)
> * [Kernel Methods and SVMs](https://storage.googleapis.com/supplemental_media/udacityu/386608826/Kernel%20Methods%20and%20SVMs.pdf)

![Quiz 1: select the best line](/assets/images/计算机科学/118382-fedd25c9a2883c94.png)

* the middle line is consistent with the data but least commitmented to the data ( to avoid overfitting)


![How to find the best line](/assets/images/计算机科学/118382-a232451582274df1.png)

* y is classification label, and the boundary line (orange line) and negative and positive plane is defined.
* We should maximize the vector between the two grey lines.

![Quiz 2: how to measure the distance between two grey plane](/assets/images/计算机科学/118382-1d3f6ebb23fc305e.png)

* This finding the best line (least commitment line that separates the data) problem it actually maximizing the margin (2/||w||)

![SVM](/assets/images/计算机科学/118382-7741318b78b80400.png)

* maximizing the margin problem can be converted to minimizing  1/2 * ||w||<sup>2</sup>, which is a quadratic programming problem.
* it can be further expressed as another quadratic programming problem W(α)

![Quiz 3: Optimal Separator ](/assets/images/计算机科学/118382-2ae10f257cfd35c6.png)

* w is the sum of the product of α<sub>i</sub>, y<sub>i</sub> and x<sub>i</sub>
* for the most of time, α<sub>i</sub> is 0.
* quiz: in the graph in the right-bottom corner, which point is most likely to have an α<sub>i</sub> == 0? 
  * answer: the points that are faraway from the optimal separator (or decision boundary) doesn't matter.
  *  It's like KNN but you already figured out which points actually matter by quadratic program
* x<sub>i</sub><sup>T</sup> x<sub>j</sub> is a measure of how similar x<sub>i</sub> and x<sub>j</sub> are.

### 

![Quiz 4: Linearly Married](/assets/images/计算机科学/118382-a9f1be1ed8bb907a.png)

* for the pluses surrounded by minuses, they are not linear separable.
* by introducing an function with a three dimensional tuple, we can separate them in a higher dimension.
* the new function is equivalent to take the squared value of x<sub>i</sub><sup>T</sup> x<sub>j</sub>
* with more complicated data, higher dimension can be used. this is called the __Kernel trick__. the kernel function can be expressed by k(x<sub>i</sub>, x<sub>j</sub>)
* Kernel captures the domain knowledge

![Kernel](/assets/images/计算机科学/118382-9ef8e23f4ac7adf3.png)

* radial basis kernel 
* sigmoid-like kernel
* Mercer Condition:  it acts like a distance, or a similarity

![recap](/assets/images/计算机科学/118382-7c7944b503e09e27.png)

----

![Why Boosting tends not to overfitting](/assets/images/计算机科学/118382-c550b993e4b49a53.png)

* First, we normalize the final hypothesis with Σα<sub>t</sub>.
* With each loop of boosting, the items that were hard to separate got separated further, e.g. pushing negative to the left and positive signs to the right.
* Without changing the error, booting makes the margin larger and larger, thus it more likely to avoid overfitting.
* But Boosting could be overfitting in practice

![Quiz 5: Boosting tends to overfit when ___.](/assets/images/计算机科学/118382-ea0256b63a7b93a2.png)

* explanation: if using a complex ANN, applying the training might end up no error, and the distribution will not change at all for the next loop. So no matter how many loops boosting goes through, it will end up of only one hypothesis which is the ANN. ANN overfits so that Boosting overfits.
* pink noise, a.k.a uniform noise, also tends to cause boosting to overfit. (by the way, white noise is gaussian noise).

----

## SL7: Computational Learning Theory

> * [Lesson 7 Notes](https://storage.googleapis.com/supplemental_media/udacityu/383498973/Lesson%207%20Notes.pdf)
> * [PAC Learning](https://storage.googleapis.com/supplemental_media/udacityu/383498973/PAC%20Learning.pdf)

![Quiz 1: how the region was labelled? ](/assets/images/计算机科学/118382-658cf78fe9c0241b.png)

* First, decision tree
* second, SVM, or Perceptron or neural network
* Third: K-NN, k =1.

![Learning Theory](/assets/images/计算机科学/118382-515f43902041ddf5.png)

![Quiz 2: resource in machine learning](/assets/images/计算机科学/118382-2d1d03ade1070d4d.png)

* my answer was: space, time, training set, testing set

![Defining inductive learning](/assets/images/计算机科学/118382-0a4d3263723a0a2c.png)

![Three ways of selecting training samples](/assets/images/计算机科学/118382-ed93aca2c4426811.png)

![Quiz 3: Teaching Via 20 questions](/assets/images/计算机科学/118382-af1ffa2a6155283a.png)

* If the teacher (who knows the answer) tells learning to ask X, then learner ask the question. the learner can get the answer in __1__ step.

![Quiz 4: Teaching Via 20 questions](/assets/images/计算机科学/118382-00174f1ee34783ae.png)
* if learner ask questions, how many steps s/he needs to get the correct answer?  log<sub>2</sub> |H|
* Answer: we want to choose a question that can eliminate half of the information at each step. And the number of times you can divide a number in half before you get down to one is exactly the log<sub>2</sub>.

![Teacher With Constrained Queries](/assets/images/计算机科学/118382-ff69ee994ca4ee94.png)

* teacher is constrained because only information of X1, X3 and X5 will be considered

![Quiz 5: Reconstructing Hypothesis](/assets/images/计算机科学/118382-208b0597311a458d.png)


![Quiz 5: answer](/assets/images/计算机科学/118382-5290e9aca93d9483.png)

If the teacher with constrains asked questions, he can ask k+2 questions to figure out the hypothesis, which is linear
* Number of questions needs to ask: k+2
  * shows what's irrelevant :2 
  * show what's relevant: K
* questions that could be asked = 3 <sup>k</sup>

![Learner With Constrained Queries](/assets/images/计算机科学/118382-d85fa0e042f2323e.png)

* If the learner with the same constrains asked the questions, s/he will need to ask at least 2<sup>k</sup> questions.
* most questions asked will not provide any information.

![Leaner with Mistake bands 1](/assets/images/计算机科学/118382-92388bcbcaa67eea.png)

![Leaner with Mistake bands 2](/assets/images/计算机科学/118382-bde36c491abf155e.png)

* The algorithm makes sure that the learning get a lot of information each time it makes a mistake.
* the learner will never make more than K+1 mistakes

![Some definitions](/assets/images/计算机科学/118382-246f4a83691e6691.png)

![Version Spaces difinition](/assets/images/计算机科学/118382-0ec4924924de0d57.png)

![Quiz 6: Terminology](/assets/images/计算机科学/118382-fad0cb57a11c2f30.png)

* choose the hypothesis that are still in the version space after seeing the two training samples.

![Error of h](/assets/images/计算机科学/118382-a65d03e4dec034d1.png)

![PAC Learning](/assets/images/计算机科学/118382-ed956054d1dddd85.png)

* PAC stands for probably approximately correct. 1-𝛿 confident that we will get error ε to find the true concept class h(x)=c(x).
* please note that the leaning time and samples were bounded by 1/ε,1/𝛿 and n.

![Quiz 7: is the h PAC learnable?](/assets/images/计算机科学/118382-2f80add270507e68.png)

* my answer was correct but I don't know why, keep going with the slides below.

![quiz 8: Epsilon Exhausted](/assets/images/计算机科学/118382-f346634ea6e40138.png)

* Epsilon Exhausted: if every hypothesis (h) in the version space have the error that's smaller than ε, then the version space is ε exhausted.
* quiz, given the distribution of the samples data, and we only see the samples in green box, what's the smallest ε such that VS is  ε exhausted?
  * From the two instance we see, we will now only three hypothesis are possible candidates.
  * the distribution for the last instance is 0, so it doesn't matter.
  * for the instance with 0.5 distribution, hypothesis X has error of 0.5, and OR and XOR have error of 0. 
  * so ε should be 0.5 for the VS to be ε exhausted.

![Haussler Theorem](/assets/images/计算机科学/118382-0e3e543973aa10ec.png)
![Haussler Theorem continue](/assets/images/计算机科学/118382-d766599e81f68588.png)

1. High true error: error<sub>D</sub> is higher than ε
2. then the probability of candidate hypothesis is consistent with true hypothesis is less than or equal to 1- ε
3. then is we draw m samples, the probability of h consistent with C on all m samples is (1-ε)<sup>m</sup>
4. then the probability of at least one h consistent with c is <= K(1-ε)<sup>m</sup> <= |H|(1-ε)<sup>m</sup>
5. because -ε >= ln(1-ε), so (1-ε)<sup>m</sup> <=e<sup>-εm</sup>, so that in 4, the probability of at least one h consistent with c is <= |H|e<sup>-εm</sup> <=𝛿 (*𝛿* is failure possibility)
6. given all the above info, ln|H|-em<= ln𝛿, so m>=1/ε(ln|h| + ln(1/𝛿).

![Quiz 9: PAC Learnable Example](/assets/images/计算机科学/118382-d51b0d7ad53cd737.png)

* substitute numbers in the formula above, and will get 40 as answer
* Distribution is not used

![Recap](/assets/images/计算机科学/118382-aafd496927725a2e.png)

* two questions
  * what if m does not satisfy the equation? agnostic
  * what if we have infinite hypothesis? hosedness (see next lesson)

![](https://pbs.twimg.com/media/BYfci7qCEAEgH0O.jpg)


```
2016-01-26 完成SL6
2016-01-27 初稿完成
```
