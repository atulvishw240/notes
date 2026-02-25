
# 1. Fundamental Programming Structures

## 1.1.3 Object Instances and Method Calls

```java
System.out.println("Hello, World!");
```

- `System.out` is an object. It is an *instance* of a class called `PrintStream`

```java
new Random().nextInt() // Example of creating new instances
```

*Factory methods* provide an alternate way of producing objects. For example,
```java
RandomGenerator generator = RandomGenerator.getDefault();
```

- In modern Java, this is the preferred way of getting a random number generator. The factory method yields a generator with better characteristics than the legacy `Random` class.

## 1.2 Primitive Types

java signed integer types - byte, short, int, long
floating point types - float, double

>[!note]
>Use `BigIntegerl` if you want integers greater than `long`.
>Use `BigDecimal` if you want to perform precise calculations, without rounding errors.

The name of a variable, method, or class is called an _identifier_. You cannot use spaces or symbols in identifiers. Finally, you cannot use keywords.

>[!tip]
>It is considered good style to declare a variable as late as possible, just before you need it for the first time.

>[!note] The system class declares a constant
>```java
>public static final PrintStream out
>```
>that you can use anywhere as `System.out`. This is one of the few examples of a constant that is not written in uppercase.

>[!bug] Always be careful using `%` with potentially negative operands.

>[!note] 
>`++n` and `n++` both increase the value of n by 1 but they have different values when used inside an expression. For example,
>```java
>int n = 5;
>IO.println(n++); // 5, yields the value before the increment
>IO.println(++n); // 7, yields the value after the increment
>```

