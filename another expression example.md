
```sml
fun max_constant e =
    case e of
	Constant i => i
      | Negate e2 => max_constant e2
      | Add(e1, e2) => Int.max(max_constant e1, max_constant e2)
      | Multiply(e1, e2) => Int.max(max_constant e1, max_constant e2)
```

