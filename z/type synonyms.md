
A **datatype binding** introduces a new type name
- Distinct from all existing types
- Only way to create values of the new type is the constructors

A **type synonym** is a new kind of binding
```sml
type aname = t
```

- Just creates another name for a type
- The type and the name are **interchangeable in every way**
- Do not worry about what REPL prints: picks what it wants just like it picks the order of record field names

## Why have this?

For now, type synonyms just a convenience for talking about types
- Example (where `suit` and `rank` are already defined)
```sml
type card = suit * rank
```

- Write a function of type `card -> bool`
- Okay if REPL says your function has type `suit * rank -> bool`

Convenient, but does not let us "do" anything new. Later in course will see another use related to modularity.

