
Already know:
- Have various *base types* like `int bool unit char`
- Ways to build (nested) *compound types*: tuples, lists, options

To create a compound type, there are really only three essential building blocks. Any decent programming language provides these building blocks in some way:
- "Each-of":  A compound type t describes values that contain each of values of type `t1, t2, ..., and tn.` Ex: tuples and records
- “One-of”: A compound type t describes values that contain a value of one of the types `t1, t2, ..., or tn.` Ex: Option and in OOP subclassing.
- “Self-reference”: A compound type t may refer to itself in its definition in order to describe recursive data structures like lists and trees.


## Examples

- Tuples build each-of types
	- `int * bool` contains an `int` *and* `a bool`
- Options build one-of types
	- `int option` contains an `int` or it contains no data
- Lists use all three building blocks
	- `int list` contains an `int` *and* another `int list` *or* it contains no data
