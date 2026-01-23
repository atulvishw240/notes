
- **Syntax**: 
```sml
fun x0 (x1 : t1, ... , xn : tn) = e
```

- **Evaluation**: A function is a value! (No evaluation yet, function body is evaluated when function is called)
	- Adds **x0** to environment so later expressions can call it


- **Type-checking**:
	- Adds binding `x0 : (t1 * ... * tn) -> t` if
	- Can type-check body **e** to have type **t** in the static environment containing
		- "Enclosing" static environment (earlier bindings)
		- `x1 : t1, ..., xn : tn` (arguments with their types)
		- `x0 : (t1 * ... * tn) -> t` (for recursion)


## Function calls

**Syntax**:
```sml
e0 (e1,...,en)
```

**Type checking**:
If
- `e0` has some type `(t1 * ... * tn) -> t`
- `e1` has type `t1, ..., en` has type `tn`
Then
- `e0 (e1,...,en)` has type t
Example: `pow(x, y-1)` in previous example has type `int`


