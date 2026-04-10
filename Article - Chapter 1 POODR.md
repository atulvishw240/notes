
## The Problem Design Solves

Imagine you wrote an application, also imagine that once written this application need never change. In this case design does not matter.

Unfortunately, something *will* change. Change is unavoidable. The application was a huge success but now everyone is asking for more features.

>It is this need for change that makes design matter.

## Why Change is Hard

Object-Oriented applications are made up of parts that interact to produce the behaviour of the whole. The parts are **objects**; interactions are embodied in the **messages** that pass between them. Getting the right message to the correct target object requires that the sender of the message know things about the receiver. This knowledge creates dependency between the two, and these dependencies stand in the way of change.

When objects know too much, they have expectations about the world in which they reside. They're picky, they need things to be "just so". These expectations constrain them. The objects resist being reused in different contexts; they are painful to test and susceptible to being duplicated.

## A Practical Definition of Design

>Every application is a collection of code; the code's arrangement is the **design**.

Designs that anticipate specific future requirements almost always end up badly. Practical design does not anticipate what will happen to your application; it merely accepts that something will and that, in the present, you cannot know what. It doesn't guess the future; it preserved your options for accomodating the future. It doesn't choose; it leaves you room to move.

## When to Design

Agile believes that your customers can't define the software they want before seeing it, so it's best to show them sooner rather than later. It also believes that the most cost-effective way to produce what customers really want is to collaborate with them, building software one small bit at a time such that each delivered bit has the opportunity to alter ideas about the next.

If Agile is correct, then :-
- there is absolutely no point in doing a Big Up Front Design (BUFD)
- no one can predict when the application will be done

The desire for BUFD exists because, for some, it provides a feeling of control that would otherwise be lacking. Comforting though this feeling may be, it is a temporary illusion that will not survive the act of writing the application.

The word *design* when used in BUFD has a different meaning than when used in OOD. BUFD is about completely specifying and totally documenting the anticipated future inner workings of all of the features of the proposed application. If there's a software architect involved, this may extend to deciding, in advance, how to arrange all of the code. OOD is concerned with a much narrower domain. It is about arranging what code you have so that it will be easy to change.

>Agile processes *guarantee change*, and your ability to make these changes depends on your application's design. If you cannot write well-designed code, you'll have to rewrite your application during every iteration.

## Judging Design

Bad OOD metrics are indisputably a sign of bad design; code that scores poorly will be hard to change. Unfortunately, good scores don't prove the opposite; that is, they don't guarantee that the next change you make will be easy or cheap. The problem is that it is possible to create beautiful designs that over-anticipate the future