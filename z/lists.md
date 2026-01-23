
- Despite nested tuples, the type of a variable still "commits" to a particular "amount" of data

In contrast, a list:
- can have any number of elements
- but all list elements must have the same type

Just like with other data structures, we need a way to *build* list and *access* the pieces.


## Building Lists

- The empty list is a value: `[]`
- In general, a list of values is a value; elements separated by commas:
- `[v1,v2,.....vn]`
- If `e1` evaluates to `v` and `e2` evaluates to a list `[v1,v2,...vn]`, then `e1::e2` evaluates to `[v,...vn]`


## Accessing Lists

- `null e` evaluates to **true** if and only if `e` evaluates to `[]`
- `hd e` returns head of the list
- `tl e` returns the tail of the list


## Special case

- `[]` has type `a' list` where a' can be any type, which is good as it allows us to cons anything on an empty list like:

```sml
(3,4)::[];
(true, [3,4])::[];
```

`a'` is a polymorphic type here.

---

## Recursion

Functions over lists are usually recursive
	- Only way to "get to all the elements"
- What should the answer be for the empty list?
- What should the answer be for non-empty list?
	- Typically in terms of the answer for the tail of the list!

Similarly, functions that produce lists of potentially any size will be recursive
- You create a list out of smaller lists



