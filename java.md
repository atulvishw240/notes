
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

**Operator Precedence** : PEMDAS (Parentheses, Exponentiation, Multiply, Division, Add, Subtract)
When same precedence (Multiply, Add) perform operations Left to Right

**Limits** : Integers in range (`-2^31 to 2^31 -1`)
If you do math that should produce a larger number than is representable, the value will "loop around."
When a value loops around because it got too big we call that "**overflow**." When it loops around because it got too small we call that "**underflow**."

[floating point numbers - computerphile](https://youtu.be/PZRI1IfStY0?si=ry3oRKLakNKfbYNI)

