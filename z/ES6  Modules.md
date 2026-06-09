
Unlike languages like Java and Python, JS didn't use to provide `import` statements to share code across files. As a result if you have code across various files you would do something like:

```html
<script src="one.js"></script>
<script src="two.js"></script>
.
.
.
```

This will load the two scripts `one.js` and `two.js` in the same global scope. Our top level variables are not safe.

Before we got **ES6 Modules** in javascript you could use **IIFE** to wrap some things and now any variables inside this module will be scoped to that function and not globally.

With **ES6 Modules** each files gets its own private scope by default, and not only can we choose what things we export from that file, we can also choose what things we import into other files. A top level variable in a module will not be accessible in a global scope.

## Named Exports

```js
// one.js
export const greeting = "Hello, Odinite!";
export const farewell = "Bye bye, Odinite!";
```

```js
// one.js
const greeting = "Hello, Odinite!";
const farewell = "Bye bye, Odinite!";
export { greeting, farewell };
```

```js
// two.js
import { greeting, farewell } from "./one.js";

console.log(greeting); // "Hello, Odinite!"
console.log(farewell); // "Bye bye, Odinite!"
```

## Default exports

In contrast to named exports, a file can only default export a single thing. 

```js
// one.js
export default "Hello, Odinite!";
```

```js
// one.js
const greeting = "Hello, Odinite!";
export default greeting;
```

```js
// two.js
import helloOdinite from "./one.js";

console.log(helloOdinite); // "Hello, Odinite!"
```


## Entry Points

When we use ESM, instead of adding every JavaScript file to our HTML in order, we only need to link a single file - the **entry point**. (**Dependency graph**)
```js
<script src="two.js" type="module"></script>
```

We didn't use `defer` because `type=module` automatically defers script execution for us.


