---
layout: post
title: "KBAI-笔记-12-Logic"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

# Preview

![Logic](/assets/images/计算机科学/118382-d5d0df82cf3b94e6.png)

* Logic is a language allows to make association of the world in a precise way.
* it form the basis of planning

# Why do we need formal logic?

![Logic](/assets/images/计算机科学/118382-8f741cd034d866e5.png)

Knowledge base: sentence in the language of logic; complete and correct
Rules of Inference engine: 

## Inferences About Birds

![Put the sentence classifying birds in to language of logic](/assets/images/计算机科学/118382-0943810715f809db.png)

## Exercise: Inferences About Foos

![](/assets/images/计算机科学/118382-3c46cb5044f7f9fa.png)

The sentences are language of logic

## Predicates

![](/assets/images/计算机科学/118382-44215f2365ec64a5.png)

":" means indicates. 
`If Feathers(animal): Then Bird(animal)` reads if animal has feathers, then animal is bird.

## Conjunctions and Disjunctions

![And](/assets/images/计算机科学/118382-a9f431e88284cddb.png)

![Or](/assets/images/计算机科学/118382-24263429b4448f7e.png)

![Not](/assets/images/计算机科学/118382-78edf0f139a5765a.png)

## Implies

![Implies](/assets/images/计算机科学/118382-6d541e6d0c196135.png)

## Notation Equivalency

![](/assets/images/计算机科学/118382-a34a31bfb3e6e558.png)

## Exercise: Practicing Formal Logic
![](/assets/images/计算机科学/118382-abdf2d0f4a34f21b.png)

## Truth Tables

![](/assets/images/计算机科学/118382-8e476f82cee11dae.png)

## Exercise: Truth Tables I

![](/assets/images/计算机科学/118382-95af55e34cde46c7.png)

Exercise: Truth Tables II (more complicated sentence)

![](/assets/images/计算机科学/118382-6ee9805f65a1c785.png)

In theory, we can calculate True or False values for very complicated sentences.

## Exercise: Commutative Property
![](/assets/images/计算机科学/118382-ad6144ca354fc25c.png)
A & B is the same as B & A

## Exercise: Distributive Property

![](/assets/images/计算机科学/118382-4d5168d058ad0521.png)

* A &(B or C) is equivalent to (A and B)  or (A and C)
Exercise: Associative Property

## Exercise: Associative Property

![](/assets/images/计算机科学/118382-187890dc9f878e12.png)
* The associate property applies when there is only conjunction or disjunctions.

## Exercise: De Morgan's Law 

![](/assets/images/计算机科学/118382-c4d4ab19da3f2e2d.png)

## Truth of Implications

![](/assets/images/计算机科学/118382-032d60cca2f45750.png)
This is hard to understand: need to go back to the examples
But remember `A=> B` is actually `!A | B`.

## Implication Elimination

![](/assets/images/计算机科学/118382-d6b97b52f08d1385.png)

## Rules of Inference

![](/assets/images/计算机科学/118382-ba4e1a81aa0fa3ee.png)
* The rules here can be used for reasoning.

## Prove Harry is a bird

![](/assets/images/计算机科学/118382-e389ce66da960f00.png)

![](/assets/images/计算机科学/118382-036620010a278ca2.png)

Although the rules exist for a long times, it's hard to use these rules in AI agent because the computation is not feasible.

## Universal Quantifiers and Existential Quantifier

![Universal Quantifier](/assets/images/计算机科学/118382-124d9cff3e2c18f8.png)

![Existential Quantifier](/assets/images/计算机科学/118382-d6c8b39a0a642b27.png)

* Propositional logic (zero-order logic): no variables.
* Existential and Universal Quantifier can be used with variables.
* Universal Quantifier mean given all values for the variable
* Existential Quantifier means at least one value 

## A Simple Proof

![resolution theorem proving](/assets/images/计算机科学/118382-c7ed5033541cfa57.png)
1. convert every sentence into a conjunctive normal form.
```
not finished for this part. did not understand
```

## exercise

![Proof I](/assets/images/计算机科学/118382-cc072013aef08bde.png)

![Proof II](/assets/images/计算机科学/118382-c141090bf257bb43.png)

![Proof III](/assets/images/计算机科学/118382-465bad7c04e3015e.png)

![Proof IV](/assets/images/计算机科学/118382-f86b281bf771a7c9.png)

![Proof V](/assets/images/计算机科学/118382-226aa7f77a4f8120.png)

![Proof VI](/assets/images/计算机科学/118382-824be5feea661d26.png)

* A efficient way to proof sentences

## Wrap Up

![](/assets/images/计算机科学/118382-0d8cf80d6048036e.png)
## The Cognitive Connection
* Formal and precise way to reason
* Human uses logic sometimes.. but its not a fundamental method.
* Human uses induction and abduction more for reasoning. logic is deductive.



