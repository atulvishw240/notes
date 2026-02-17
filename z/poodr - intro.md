
If once written, an application need never change then in this case design doesn't matter. Unfortunately something will change. It is this need for change that makes design matter.

## Why Change is Hard

>Object-Oriented design is about *managing dependencies*. It is a set of coding techniques that arrange dependencies such that objects can tolerate change.

When objects know too much, they have many expectations about the world in which they reside. They're picky, they need things to be "just so". These expectations constrain them. The objects resist being reused in different contexts; they are painful to test and susceptible to being duplicated.

### A Practical Definition of Design

>Every application is a collection of code; the code's arrangement is the *design*.

Designs that anticipate specific future requirements almost always end badly. Practical design does not anticipate what will happen to your application; it merely accepts that something will and that, in the present, you cannot know what. It doesn't guess the future; it preserves your options for accommodating the future. It doesn't choose; it leaves you room to move.

>The purpose of design is to allow you to design *later*, and its primary goal is to reduce the cost of change.

## The Tools of Design

Design is not the act of following a fixed set of rules, it's a journey along a branching path wherein earlier choices close off some options and open access to others. During design, you wander through a maze of requirements where every juncture represents a decision point that has consequences for the future.

## When to Design

BUFD is about completely specifying and totally documenting the anticipated future inner workings of all of the features of the proposed application. If there's a software architect involved, this may extend to deciding, in advance, how to arrange all of the code. OOD is concerned with a much narrower domain. It is about arranging what code you have so that it will be easy to change.

>Agile thus does not prohibit design, it requires it. Not only does it require design, it requires really good design. If you cannot write well-designed code, you'll have to rewrite your application during every iteration.


## Judging Design

Metrics software works by scanning source code and counting things that predict quality.

Bad OOD metrics are indisputably a sign of bad design; code that scores poorly *will* be hard to change. Unfortunately, good scores don't prove the opposite; that is, they don't guarantee that the next change you make will be easy or cheap. The problem is that it is possible to create beautiful designs that over-anticipate the future.

While these designs may generate very good OOD metrics, if they anticipate the *wrong* future, they will be expensive to fix when the real future finally arrives. OOD metrics cannot identify designs that do the wrong thing in the right way.



