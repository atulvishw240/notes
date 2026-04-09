
```js
function Player(name, marker) {
  if (!new.target) {
    throw Error("You must use the 'new' operator to call the constructor");
  }
  this.name = name;
  this.marker = marker;
  this.sayName = function() {
    console.log(this.name);
  };
}

const player = new Player("steve", "X");
console.log(player.name);
```

The `new` Operator creates a new Object, makes `this` keyword inside the function refer to that object, and makes that object inherit from the function's .[[The prototype | prototype]] property.



