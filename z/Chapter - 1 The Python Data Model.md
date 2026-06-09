
Python Data Model is the API that we can use to make our own objects play well with the most idiomatic language features.

You can think of the data model as a description of a Python as a framework. When using a framework, we spend a lot of time coding methods that are called by the framework. The same happens when we leverage the **Python Data Model** to build new classes.

>[!question] What does  "Thanks to composition, the __len__ and __getitem__ implementations can delegate all the work to a list object, `self._cards`."  mean in context of `FrenchDeck`
>
>This means that **you didn't implement deck behavior yourself - you reused an existing object (a list) to do it for you**. `FrenchDeck` *has* a list (composition). 

>Don't call special methods directly, let the interpreter call it.

You don't write `my_object.__len__()`, you write `len(my_object)` and , if `my_object` is an instance a user-defined class, then Python calls the `__len__` method you implemented. 

But the interpreter takes a shortcut when dealing for built-in types like `list`, `str`, `bytearray`, or extensions like the NumPy arrays. Python variable-sized collections written in C include a struct[2](ch01.xhtml#idm46582509922000) called `PyVarObject`, which has an `ob_size` field holding the number of items in the collection. So, if `my_object` is an instance of one of those built-ins, then `len(my_object)` retrieves the value of the `ob_size` field, and this is much faster than calling a method.

**Important uses of special methods:**
- Emulating numeric types (objects can respond to `+`, `*`, `/`)
- String representation of objects (`__repr__` and `__str__`)
- Boolean value of an object (`__bool__`)
- Implementing collections

## Summary

By implementing special methods, your objects can behave like the built-in types, enabling the expressive coding style the community considers Pythonic.
