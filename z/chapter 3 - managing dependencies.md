
Because well-designed objects have a single responsibility, their very nature requires that they collaborate to accomplish tasks. To collaborate, an object must know something about others. *Knowing* creates dependency. If not managed carefully, these dependencies will strangle your application.

# 3.1 Understanding Dependencies

## 3.1.1 Recognizing Dependencies

An object has a dependency when it knows:
- The name of another class
- The name of a message that it intends to send to someone other than `self`
- The arguments that a message requires
- The order of those requirements

