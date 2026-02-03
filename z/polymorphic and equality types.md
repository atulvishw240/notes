
- "Write a function that appends two string lists"
```sml
fun append(xs,ys) =
	case xs of
		[] => ys
	|   x :: xs' => x :: append(xs',ys)
```

- You expect `string list * string list -> string list`
- Implementation says `'a list * 'a list -> 'a list`
- The type `'a list * 'a list -> 'a list` is more general than the type `string list * string list -> string list`
