
Bundling **data** and **functions** that manipulates this **data** into a single entity called **Object**. This way we draw boundaries at a **Class or Module** level. When the **data** and **functions** that manipulate that data lives in the same place, it limits the side effects to this single module.

Occasionally, we may want to bundle a group of functionalities together (without any data). This way we can share this functionality across various objects. Since everything in an Object Oriented language like Java is an Object, hence we will call this a **Service Object**.

If a class method heavily relies on another class data then it's a sign that this method ought to be in that class.

>The whole idea of encapsulation is to bundle related methods and data. In functional programming it can be done via closures. In OOP it is done via Objects.

