- We can nest patterns as deep as we want
	- Just like we can nest expressions as deep as we want
	- Often avoids hard-to-read, wordy nested case expressions

- So the full meaning of pattern-matching is to compare a pattern against a value for the "same shape" and bind variables to the "right parts"

```sml
fun zip3 list_triple =
	case list_triple of
		([],[],[]) => []
	|   (hd1::tl1,hd2::tl2,hd3::tl3) => (hd1,hd2,hd3)::zip3(tl1,tl2,tl3)
	|   __ => raise ListLengthMismatch
	
fun unzip3 lst =
	case lst of
		[] => ([],[],[])
	|   (a,b,c)::tl => let val (l1,l2,l3) = unzip3 tl
					   in
						   (a::l1,b::l2,c::l3)
					   end
```