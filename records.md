
Record *types* are "each-of" types. Record values have fields (any name) holding values
```sml
{f1 = v1, ..., fn = vn}
```

Record *types* have fields (and name) holding types
```sml
{f1 : t1, ..., fn : tn}
```

**Building records**:
```sml
{f1 = e1, ..., fn = en}
```

**Accessing pieces**:
`#myfieldname e`

(Evaluation rules and type checking as expected)


## By name vs by position

A common decision for a construct's syntax is whether to refer to things **by position** (as in tuples) or **by some** (field) name (as with records).

A common hybrid is like with Java method arguments (and ML functions used so far):
- Caller uses position (to give arguments)
- Callee uses variables (function body)
- Could do it differently