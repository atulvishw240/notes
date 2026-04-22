
JavaScript classes are syntactic sugar for **prototypes** and object **constructors**. Although some things are unique to them.

>[!tip]
>In Object Oriented Programming, there is state and behavior. Behavior leads to state change. When an object goes into an invalid stage, that's called a bug. In this way, an object can be thought of as a Finite state machine and finite machines can have many variations. Its also possible to have behaviors without any state, that's why we have **Service Objects**.

In JS, a class is a kind of function. Here's what the `class User {...}` construct really does:
1. Creates a function named **User**, that becomes the result of the class declaration. The function code is taken from the **constructor** method (assumed empty if we don't write such method).
2. Stores class methods, such as `sayHi`, in `User.prototype`.

![[attachments/js-inheritance.png]]


>[!question] Why would I want to hide as many things from the client as possible?

Because if I hide it then client won't depend on it and as a result I can change that later. The client only knows the interface and I can control the implementation however I want. Ex: `sort()` method which was earlier 4 lines but slow is now 50 lines but fast, as it considers various scenarios and optimizations for those scenarios. The good thing is client can't tell and doesn't have to.