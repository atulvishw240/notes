
>Tuples is just syntactic sugar for records.

- Tuple syntax is just a different way to write certain records
- `(e1, ..., en)` is another way of writing `{1=e1, ..., n=en}`
- `t1*...*tn` is another way of writing `{1:t1 ,..., n:tn}`

"Tuples are just **syntactic sugar** for records with fields name 1,2,...n"

**Syntactic**: Can describe the semantics entirely by the corresponding record syntax
**Sugar**: They make the language sweeter

Will see many more examples of syntactic sugar
- They simplify *understanding* the language
- They simplify *implementing* the language
Why? Because there are fewer semantics to worry about even though we have the syntactic convenience of tuples