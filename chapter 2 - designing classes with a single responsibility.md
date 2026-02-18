
## Grouping Methods into Classes

The classes you create will affect how you think about your application forever. They define a virtual world, one that constrains the imagination of everyone downstream.

Despite the importance of correctly grouping methods into classes, at this early stage of your project you cannot possibly get it right.

>Design is the art of preserving changeability than it is the act of achieving perfection.

## Organizing Code to Allow for Easy Changes

We define *easy to change* as:
- changes have no unexpected side effects,
- small changes in requirements require correspondingly small changes in code,
- existing code is easy to reuse, and
- the easiest way to make a change is to add code that in itself is easy to change

then the code you write should have the following qualities. Code should be:
- **Transparent**
- **Reasonable**
- **Usable**
- **Exemplary**

## Why Single Responsibility Matters

Applications that are easy to change consists of classes that are easy to reuse.

A class that has more than one responsibility is difficult to reuse. The various responsibilities are likely thoroughly entangled *within* the class. If you want to reuse some (but not all) of its behavior, it is impossible to get only the parts you need. You are faced with two options and neither is particularly appealing.

More responsibility means many reasons to change. Each time it changes, there's a possibility of breaking every class that depends on it.

## Determining If a Class Has a Single Responsibility

