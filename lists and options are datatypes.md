
Options are just a predefined datatype binding
- `NONE` and `SOME` are *constructors*, not just functions
- So use pattern-matching not `isSome` and `valOf`
```sml
fun inc_or_zero intoption =
	case intoption of
		NONE => 0
	|   SOME i => i + 1
```


## Lists are datatypes

Do not use `hd, tl` or `null` either
- `[]` and `::` are constructors too
- (strange syntax, particularly infix)
```sml
fun sum_list xs =
	case xs of
		[] => ys
	|   x::xs' => x :: append(xs', ys)
```

