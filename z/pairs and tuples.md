
**Tuples**: fixed "number of pieces" that may have different types.

## Pairs (2-tuples)

For every **compound data type** we need a way to *build* it and a way to *access* to pieces. **Pairs** are no different.

***Build***
- **Syntax**: `(e1,e2)`
- **Evaluation**: Evaluate `e1` to `v1` and `e2` to `v2`; result is `(v1,v2)`
	- A pair of values is a value
- **Type-checking**: `e1` has type `ta` and `e2` has type `tb`, the pair expression has type `(ta * tb)`
	- A new kind of type


***Access***
- **Syntax**: `#1 e` and `#2 e`
- **Evaluation**: Evaluate `e` to a pair of values and return first or second piece
	- Example: If `e` is a variable `x`, then look up `x` in environment
- **Type-checking**: If `e` has type `ta * tb`, then `#1 e` has type `ta` and `#2 e` has type `tb`

---
## Tuples 

A generalization of pairs
- `(e1,e2,...en)`
- `(ta,tb,..tn)`
- `#1 e, #2 e, #3 e, ...`

>Pairs and tuples can be nested however you want

```sml
val x1 = (7, (true, 9));
```

