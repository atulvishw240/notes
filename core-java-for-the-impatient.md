
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


