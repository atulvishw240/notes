```sml
(* int * int *int -> int *)
fun sum_triple (x,y,z) =
	x + y + z
	
(* This works fine *)
fun sum_triple2 (triple: int * int * int) =
	#1 triple + #2 triple + #3 triple

(* This won't type check because the Type System knows that tuples need to have atleast 3 fields but how does it know that it doesn't have a fourth position or a fifth position. It doesn't and every type system has some limitation and in ML it is that you can't write a function that takes on both three tuples and four tuples*)	
fun sum_triple3 (triple) =
	#1 triple + #2 triple + #3 triple
```


