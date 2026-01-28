
ML combines the two aspects of accessing a one-of value with a **case expression** and **pattern-matching**.

Example:
```sml
fun f x = (* f has type mytype -> int*)
	case x of
		Pizza => 3
	|   TwoInts(i1,i2) => i1+i2
	|   Str s => String.size s
```

- A multi-branch conditional to pick branch based on variant
- Extracts data and binds to variables local to that branch
- Type checking: all branches must have same type
- Evaluation: evaluate between `case...of` and the right branch

Syntactically most patterns (all today) look like expressions
But patterns are not expressions
- We do not evaluate them

## Why this way is better

0. You can use pattern-matching to write your own testing and data-extractions functions if you must
1. You cannot forget a case (inexhaustive pattern-match warning)
2. You cannot duplicate a case (a type-checking error)