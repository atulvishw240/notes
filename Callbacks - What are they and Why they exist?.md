
https://github.com/max-mapper/art-of-node#callbacks

Callbacks are functions that are executed asynchronously or at a later time.
Here's a simple synchronous example, meaning the code executes from top to bottom:

```js
function gotSalary() {
  console.log('I got my salary.');
}

function eatPizza() {
  console.log("Eating Pizza.");
}

function finishPizza() {
  console.log('Finished Pizza. It was delicious :)');
}

gotSalary(); // I got my salary.
eatPizza(); // Eating Pizza.
finishPizza(); // Finished Pizza. It was delicious :)
```
This code defines three functions and later calls them.
The order of execution of these three functions matters, eating a pizza after its already finished sounds ridiculous.
The functions in the above example gets executed in the same order in which we call them.






