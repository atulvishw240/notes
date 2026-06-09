
Construct to introduce local bindings. Its also an expression, so can be used anywhere we can use an expression.

**Syntax**: 
```sml
let b1 b2 ... bn in e end
```
- Each `bi` is any binding and `e` is any expression

**Type-checking**:  Type check each `bi` and `e` in a static environment that includes the previous bindings.
Type of whole let-expression is the type of **e**.

**Evaluation**: Evaluate each **bi** and **e** in a dynamic environment that includes the previous bindings.
Result of whole let-expression is the result of evaluating **e**

>The bindings in let-expressions are in scope only in later bindings for the let-expression and body of the let-expression


---

## Nested Functions

```sml
fun countup_from1 (x : int) =
    let
	fun count (from : int) =
	    if from = x
	    then x :: []
	    else from :: count(from + 1)
    in
	count(1)
    end
```

- Good style to define helper functions inside the function they help if they are:
	- Unlikely to be useful elsewhere
	- Likely to be misused if available elsewhere
	- Likely to be changed or removed later

A fundamental trade-off in code design: reusing code saves effort and avoid bugs, but makes the reused code harder to change later. 

OR

You want to put your functions in a narrow enough scope that you can restrict how they're used but a wide enough scope that they can be used as much as is helpful in your program.

When you change a function, you have to check all the uses of that function to make sure everything is working correctly. Thus, restricting the scope where the function can be used, can make it easier to check for this.

---

## Let and Efficiency

Computing `bad_max` twice is not efficient.
![[let-and-efficiency.png]]

