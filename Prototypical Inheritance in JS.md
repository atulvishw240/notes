
Every object in JS has an internal property called `[[Prototype]]`.  The `[[Prototype]]` is another object. To find the `[[Prototype]]` of an object, we use `getPrototypeOf()` method.

```js
let x = {};
Object.getPrototypeOf(x);
```

Another way to find the `[[Prototype]]` is through the `__proto__` property.
```js
x.__proto__;
```

The output of `__proto__` and `getPrototypeOf()` is same.

