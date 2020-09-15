---
layout: post
title: "HCI-笔记---Week-03-Direct-Manipulation-and-Human-Abilities"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

OMS CS6750: Human-Computer Interaction – Summer 2018 笔记 

Week 03： lessons [2.3](https://classroom.udacity.com/courses/ud400/lessons/9170599610/concepts/last-viewed) and [2.4](https://classroom.udacity.com/courses/ud400/lessons/9232968306/concepts/last-viewed) Human Abilities

# 2.3 Direct Manipulation

## Introduction to Direct Manipulation and Invisible Interfaces
![](/assets/images/计算机科学/118382-11e9e05134641e9a.png)

Direct manipulation and invisible interfaces are two applications of good feedback cycles.
* Direct manipulation: the user should feel as much as possible like they're directly controlling the object of their task.
* At their best, the interface actually disappears

## Direct Manipulation: The Desktop Metaphor

* Files and folders on my computer are meant to mimic files and folders on my physical desk.
* when using command-line, these actions were not direct at all.
* With GUI and mouse, now we can achieve the goal of direct manipulation of computer files and folders.

## Paper Spotlight: "Direct Manipulation Interfaces"

![Paper by Edwin Hutchins, James Hollan, and Don Norman](/assets/images/计算机科学/118382-23d18a1c560f1b7c.png)

two aspects of directness: 
1. Distance is the distance between the users' goals and the system itself. 
![Distance](/assets/images/计算机科学/118382-46ffba852b3dd8db.png)

> __Semantic distance__ refers to the distance between the user's goals and their expression in the system. 
> __Articulatory distance__ is the distance between expression and its execution.
![](/assets/images/计算机科学/118382-8c8201a7bf8f0695.png)

2. direct engagement
![direct engagement](/assets/images/计算机科学/118382-521c4bb30230b4d0.png)

direct manipulation is a powerful method for shortening that distance.
![](/assets/images/计算机科学/118382-26c0997fbe0d23f9.png)

## Exploring HCI: Direct Manipulation
The virtual reality is allowing us to bring the principle of direct manipulation to tasks it hasn't been able to touch before.

* designers are able to view what they're designing in 3D 
* They can rotate it around with the same hand motions you'd use to rotate a physical object. 
* They can physically move around the object to get different angles on it. 

But technology is replacing things you used to do manually, thus not using direct manipulation.

### Quiz: Exercise: Direct Manipulation

![quize](/assets/images/计算机科学/118382-b2d115fbcfadd158.png)
> pressing down to click; scroll; pinching.. are the choices.

## Making Indirect Manipulation direct

Example of the Mac touchpad.

## Invisible Interface

* our ultimate goal is for the interface between the user and the task to become invisible.
* Good design. Interfaces that are metaphorically invisible

### Invisibility by Learning

* With enough practice and experience, many users will become sufficiently comfortable with many interfaces to feel invisibly integrated into the task (e.g. Driving)

### Invisibility by Design
* Our goal is to create interfaces that are invisible from the moment the user starts using them.

### 5 tips: Invisible Interfaces
![5 tips](/assets/images/计算机科学/118382-7662265daea64a62.png)

1. use affordances. 
2. know your user. Invisibility to a novice means the interactions are all natural. But invisibility to an expert means maximizing efficiency.
3. Differentiate your user. Provide multiple ways of accomplishing tasks. 
4. Let your interface teach. Ideally, the interface itself will do the teaching. 
5. Talk to your user. Ask them what they're thinking while they use an interface. If users are talking about the interface, then it's pretty visible.

----

# 2.4 Human Abilities

The lesson discusses the psychology of what humans can do. 
* three systems. Input, processing, and output.
* Input is how stimuli are sent from the world and perceived inside the mind.
* Processing is cognition, how the brain stores, and reasons over the input it's received.
* __Output__ is how the brain then controls the individual's actions out in the world

## Sensation and Perception: Visual

* The center of eye:  focusing closely on color or tracking movement. 
* peripheral vision: good for detecting motion.
* colorblind: 1 in 12 men, 1 in 200 women
* visual acuity will decrease as aging.

## Sensation and Perception: Auditory

* can discern noises based on both their pitch and their loudness.
* good at localizing sound
* is NOT directional
* Always on

## Sensation and Perception: Haptic

* skin can feel things.
* things must touch right up against it.
* pressure, vibration, and temperature.
* always on but require physical touch.

## Design Challenge: Message Alerts

## Memory: Perceptual Store
![Memory](/assets/images/计算机科学/118382-dec57b5b83a27837.png)

![Perceptual Store](/assets/images/计算机科学/118382-7a4528896fcbabe9.png)

The perceptual store is a very short-term memory:
1. visuospatial sketchpad which holds visual information for active manipulation
2. phonological loop for verbal or auditory information
3. The episodic buffer: integrating information from the other systems as well as chronological ordering 

__all three of these are coordinated by a central executive__.

Expertise, or rehearsal, delays the decay of the perceptual buffer.

## Quiz: Memory: Short Term and Chunking
![](/assets/images/计算机科学/118382-59b623fffa0059b0.png)

* users can really only store four to five chunks of information at a time
* it's far easier to recognize something you know than to recall it independently.

Takeaways:
1. we don't want to ask the user to hold too much in memory at a time,
2. ask the users to recognize, not recall.

## Long-term memory 
![image.png](/assets/images/计算机科学/118382-4bff54ec077e29b8.png)

Long-term memory is a seemingly unlimited store of memories, but it's harder to put something into long-term memory, than to put it into short-term memory

## Cognition: Learning

![](/assets/images/计算机科学/118382-a836a02ebac9da7d.png)

* Procedural is how to do something. It's a task in which you're engaged or an activity you are performing, it's something that you do. 
* Declarative learning is knowledge about something. It's what you know in your head. It's what you can answer when asked.
* while declarative knowledge is how we generally communicate with one another, __procedural knowledge is generally what we do in HCI__

![](/assets/images/计算机科学/118382-2ec5acb764a74ede.png)

You're __unconsciously competent__ with what you're doing. When you're in that state, it can be difficult to explain to someone who lacks that competence, because you aren't sure what makes you so good at it.

## Cognition: Cognitive Load

1. Reduce the cognitive load posed by the interface, so that the users can focus on the task.
2. understand the context of what else is competing for cognitive resources while users are using our interface

## 5 Tips: Reducing Cognitive Load

![5 Tips: Reducing Cognitive Load](/assets/images/计算机科学/118382-d8fbfe6ccaf6e7fd.png)

1. use multiple modalities. describe things verbally and also present them visually. 
2. let the modalities complement each other.
3. give the user control of the pace. 
4. emphasize essential content and minimize clutter. The principle of discoverability. 
5. offload tasks. try offload part of that task on to the interface. 

## Motor System

Speed, or precision of actions or movement.
The goal of design here is to reduce the penalty for errors.

```
2018-06-18 初稿
```
