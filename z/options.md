
Having **max** return 0 for the empty list is really awful
- Could raise an *exception* (future topic)
- Could return a zero-element or one-element list
	- That works but is poor style because the built-in support for *options* expresses this situation directly


## Options

- `t option` is a type for any type t

**Building**:
- **NONE** has type **'a option**
- **SOME e** has type **t option** if e has type t

**Accessing**:
- **isSome** has type `'a option -> bool`
- **valOf** has type `'a option -> 'a` (exception if given NONE)

