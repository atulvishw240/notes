
**concrete code :** easier to understand and harder to change
**abstract code :** harder to understand but easier to change

>By making your code more abstract you trade-off code **understandability** with **changeability**. So your code is now harder to understand but easier to change as per new requirements.

OOP promises that if you are willing to accept increases in the complexity of your code along *some* dimensions, you'll be rewarded with decreases in complexity along *others*.

The code becomes **changeable** by becoming more abstract. The principles like **DRY**, Dependency Injection, etc. introduces a new abstraction. Design is thus the art of picking right abstractions. Each design decision has a cost, therefore, it makes sense to pay this cost if you get some benefits in return.

Unfortunately, getting the right abstractions is hard. Early abstractions are often not quite right, and therefore they create a catch-22.

>You can't create the right abstraction until you fully understand the code, but the existence of the wrong abstraction may prevent you from ever doing so. This suggests that you should not *reach* for abstractions, but instead, you should resist them until they absolutely insist upon being created.

## 1.1 Simplifying Code

There's a sweet spot that represents the perfect compromise between comprehension and changeability, and it's your job as a programmer to find it.

