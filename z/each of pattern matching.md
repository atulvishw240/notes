
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

