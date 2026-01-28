
A very important non-feature
- Huh? How could the *lack* of a feature be important?
- When it lets you know things *other* code will *not* do with your code and the results your code produces

![[mutation.png]]

What is z?
- Would depend on how we implemented `sort_pair`
	- would have to decide carefully and document `sort_pair`
- But without mutation, we can implement "either way"
	- No code can never distinguish aliasing vs identical copies
	- No code to think about aliasing focus on other things
	- can use aliasing, which saves space without danger

## ML vs Imperative Languages

- In ML, we create aliases all the time without thinking about it because it is *impossible* to tell where there is aliasing
	- Example: `tl` is constant time; does not copy rest of the list
	- so don't worry and focus on your algorithm


- In languages with mutable data (e.g. Java), programmers are *obsessed* with aliasing and object identity
	- They have to be(!) so that subsequently assignments affect the right parts of the program
	- Often crucial to make copies in just the right places
		- Optional Java example in next segment

