
Python Data Model, and it is the API that we use to make our own objects play well with the most idiomatic language features.

You can think of the data model as a description of a Python as a framework. When using a framework, we spend a lot of time coding methods that are called by the framework. The same happens when we leverage the **Python Data Model** to build new classes.

>[!question] What does  "Thanks to composition, the __len__ and __getitem__ implementations can delegate all the work to a list object, `self._cards`."  mean in context of `FrenchDeck`
>
>This means that **you din't implement deck behavior yourself - you reused an existing object (a list) to do it for you**. `FrenchDeck` *has* a list (composition). 




