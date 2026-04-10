
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

The `new` Operator creates a new Object, makes `this` keyword inside the function refer to that object, and makes that object inherit from the function's `.prototype` property.

## The prototype

All objects in JavaScript have a **prototype**, otherwise referred to as its `[[Prototype]]` (`[[]]` indicates that its an internal property). The `[[Prototype]]` is another object that the original object *inherits* from.

```js
function Player(name, marker) {
	this.name = name;
	this.marker = marker;
}
```

The moment JS sees `function Player(...) { ... }` it automatically creates:
```js
Player.prototype = { constructor: Player }
```

I only created the `Player` function and JS created `Player.prototype` internally automatically. JS did this so I can share methods across all player objects. For example, if I add a method to above code sample, like
```js
function Player(name, marker) {
	// same code as above
	this.sayName = function() {
		console.log(this.name);
	};
}
```

Now every time I create a `new` Player, a new copy of this function is created. If you create 1000 objects, 1000 `sayName()` function will be created, which is very inefficient.
```js
const player1 = new Player("Atul", "X");
const player2 = new Player("Gaurav", "O");

console.log(player1.sayName == player2.sayName) // false
```

To solve the above problem, we can define the `sayName` method on `Player.prototype` because for each `<playerObject>`:
```js
<playerObject>.[[Prototype]] = Player.prototype
```

Internally: `player1 => Player.prototype => Object.prototype => null` (**prototype chain**)

So each player object will have a link (`[[Prototype]]`) from where it can access methods defined on `Player.prototype`. As a result we will always have a single `sayName` function and
```js
player1.sayName == player2.sayName; // true
```


>[!question] How JS internally executes `new Player()`?

**Constructor**
```js
function Player(name, marker) {
	this.name = name;
	this.marker = marker;
	this.sayName = function() {
		console.log(this.name);
	};
}
```

When you run:
```js
const p1 = new Player("Gaurav", "X");
```

JS internally perform **4 exact steps**:
