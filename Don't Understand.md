
```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  get name() {
    return this.name;
  }
  
  set name(n) {
    this.name = n;
  }
  
  get age() {
    return this.age;
  }
  
  set age(n) {
    this.age = n;
  }
}
```

This throws error. StackOverFlow error. When instantiating a person object it keeps calling `set name(n)`.

