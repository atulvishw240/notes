
- Claimed built-in options and lists are not needed/special
	- Other than special syntax for list constructors

- But these datatype bindings are polymorphic type constructors
	- `int list` and `string list` and `int list list` are all types, not **list**
	- Functions might or might not be polymorhphic
		- `val sum_list : int list -> int`
		- `val append : 'a list * 'a list -> 'a list`

>Good language design: Can define new polymorphic types

>[!question] Before moving on, though, which of the following is a valid SML type?

- [ ] option
- [ ] list
- [ ] NONE
- [x] 'a list

Good! Only `'a list` was a valid type out of the listed options. The first two choices (**option** and **list**) were not valid because they were missing their type parameters (**'a, int, etc.**). **NONE** is not a valid type because it is actually a value of type **'a option**.

## Defining polymorphic datatypes

- Syntax: put one or more type variables before datatype name
```sml
datatype 'a option = NONE | SOME of 'a

datatype 'a mylist = Empty | Cons of 'a * 'a mylist

datatype ('a,'b) tree = Node of 'a * ('a,'b) tree * ('a,'b) tree | Leaf of 'b
```

