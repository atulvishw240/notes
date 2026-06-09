
Bindings are *immutable*. There are no assignment statements in ML. When you do something like this

```sml
val a = 10;
val b = a;
val a = 5; (* Creates a new environment in which a = 5 shadows the old binding *)
```
