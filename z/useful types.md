
## Expression Trees

A more exciting example of a datatype, using self-reference
```sml
datatype exp = Constant of int | Negate of int | Add of exp * exp | Multiply of exp * exp;
```

An expression in ML of type exp;
```sml
Add (Constant (10 + 9), Negate (Constant 4));
```

![[exp-tree.png]]

## Recursion

Not surprising: Functions over recursive datatypes are usually recursive
```sml
fun eval e =
	case e of
		Constant i => i
	|   Negate e2 => ~ (eval e2)
	|   Add(e1, e2) => (eval e1) + (eval e2)
	|   Multiply(e1, e2) => (eval e1) * (eval e2)
```

>