
IDE => Integrated Development Environment. It is basically a text editor with a bunch of features "integrated" that ease "development" of software.

>[!question] Why would you make a variable `final`?
>If you have 100s of lines of code and want the mental comfort of knowing you couldn't have reassigned that variable at any point between its declaration and its use.


>[!bug] Downside of making a variable final
>If a variable is only "alive" for a small part of the code, then adding `final` might make it harder to read the code, not easier.


**Type inference in Java**
```java
var name = "Atul"; // type of name will be String
```

**Boolean precedence Order**
`! > && > ||`

Section 7 Integers se padhna 