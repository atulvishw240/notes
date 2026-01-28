
If once written, your application need never change then in this case design doesn't matter.

But change is unavoidable.

>It is the need for change that makes design matter.

## Why Change is Hard

Object Oriented applications are made up of parts that interact to produce the behavior of the whole. The parts are *objects*; interaction s are embodied in the *messages* that pass between them. Getting the right message to the correct target object requires that the sender of the message know things about the receiver. This knowledge creates dependencies between the two, and these dependencies stand in the way of change.

>Object-oriented design is about *managing dependencies*. It is a set of coding techniques that arrange dependencies such that objects can tolerate change.


When objects know too much, they have many expectations about the world in which they reside. These expectations constrain them. The objects resist being reused in different contexts; they are painful to test and susceptible to being duplicated.


## A Practical Definition of Design

Every application is a collection of code; the code's arrangements is the *design*.

Designs that anticipated specific future requirements almost always end badly. Practical design does not anticipate what will happen to your application; it merely accepts that something will and that, in the present, you cannot know what. It doesn't guess the future; it preserved your options for accomodating the future. It doesn't choose; it leaves you room to move.


## The Tools of Design

Design is not the act of following fixed set of rules, it's a journey along a branching path wherein earlier choices close of some options and open access to others. During design, you wander through a maze of requirements where every juncture represents decision point that has consequences for the future.


## The Act of Design

Design is a process of progressive discovery that relies on a feedback loop. This feedback loop should be timely and incremental; the iterative techniques of the agile software movement are thus perfectly suited to the creation of well designed OO applications. The iterative nature of agile development allows design to adjust regularly and to evolve naturally. When design is dictated from afar, none of the necessary adjustments can occur and early failures of understanding get cemented into the code.


## When to Design

It should come as no surprise that some people are uncomfortable with Agile. "We don't know what we are doing" and "we don't know when we will be done" can be a difficult sell. The desire for BUFD persists because, for some, it provides a feeling of control that would otherwise be lacking.

The word *design* when used in BUFD has a different meaning than when used in OOD. BUFD is about completely specifying and totally documenting the anticipated future inner workings of all of the features of the proposed application. If there's a software architect involved, this may extend to deciding, in advance, how to arrange all of the code. OOD is concerned with a much narrower domain. It is about arranging what code you have so that it will be easy to change.


## Judging Design

Bad OOD metrics are indisputably a sign of bad design; code that scores poorly *will* be hard to change. Unfortunately, good scores don't prove the opposite; that is, they don't guarantee that the next change your make will be easy or cheap. The problem is that it is possible to create beautiful designs that over-anticipate the future. While these design may generate very good OOD metrics, if they anticipate the *wrong* future, they will be expensive to fix when the real future finally arrives. OOD metrics cannot identify designs that do the wrong thing in the right way.

>The ultimate software metrics would be *cost per feature over the time interval that matters*


## A Brief Introduction to Object-Oriented Programming


| **S. No.** | **Feature** | **Procedural Languages**                                                  | **Object-Oriented Languages**                                                                      |
| ---------- | ----------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| 1.         | Basic Units | Divided between **data** and **behavior**                                 | Combines **data** and **behavior** into a single unit: the **object**                              |
| 2.         | Data Types  | A small, fixed set of built-in data types (e.g. strings, numbers, arrays) | Open-ended; programmers can invent brand new types specifically tailored to their domain.          |
| 3.         | Operations  | Built into the syntax of the language to manipulate various data types.   | Built into the objects themselves; objects decide how much data to expose                          |
| 4.         | Interaction | Data is packaged into variables and passed around to behavior/functions.  | Objects invoke behavior in one another by sending messages                                         |
| 5.         | Structure   | Uses functions to group operations and data structures to group types.    | Uses classes as blueprints to manufacture many objects with identical behavior but different data. |
| 6.         | Visibility  | Influences on data can be unpredictable and largely untraceable           | Objects **encapsulate** (hide) their data from the outside world.                                  |
