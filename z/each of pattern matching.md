
- Every val-binding and function-binding uses pattern-matching
- Every function in ML takes exactly one argument


## Each-of types

So far have used pattern-matching for one of types because we needed a way to access the values

Pattern matching also works for records and tuples:
- The pattern `(x1,...,xn)` matches the tuple value `(v1,...,vn)`
- The pattern `{f1=x1, ..., fn=xn}` matches the record value `{f1=v1, ..., fn=vn}` (and fields can be recorded)


## Example

works but poor style to have one-branch cases
```sml
fun sum_triple triple =
	case triple of
		(x,y,z) => x + y + z
```


## Function-argument patterns

A function argument can also be a pattern
- match against the argument in a function call

```sml
fun sum_triple (x,y,z) =
	x + y + z
```

## The truth about functions

- In ML, every function takes exactly one argument
- What we call multi-argument functions are just functions taking one tuple argument, implemented with a tuple pattern in the function binding
	- Elegant and flexible language design
- Enables cute and useful things you cannot do in Java, e.g.
```sml
fun rotate_left (x,y,z) = (y,z,x)
fun rotate_right t = rotate_left(rotate_left t)
```

- "Zero arguments" is the unit pattern `()` matching the unit value `()`