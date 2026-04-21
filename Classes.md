
JavaScript classes are syntactic sugar for **prototypes** and object **constructors**. Although some things are unique to them.

>[!tip]
>In Object Oriented Programming, there is state and behavior. Behavior leads to state change. When an object goes into an invalid stage, that's called a bug. In this way, an object can be thought of as a Finite state machine and finite machines can have many variations. Its also possible to have behaviors without any state, that's why we have **Service Objects**.

In JS, a class is a kind of function. Here's what the `class User {...}` construct really does:
1. Creates a function named **User**, that becomes the result of the class declaration. The function code is taken from the **constructor** method

