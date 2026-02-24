
Because well-designed objects have a single responsibility, their very nature requires that they collaborate to accomplish tasks. To collaborate, an object must know something about others. *Knowing* creates dependency. If not managed carefully, these dependencies will strangle your application.

# 3.1 Understanding Dependencies

## 3.1.1 Recognizing Dependencies

An object has a dependency when it knows:
- The name of another class
- The name of a message that it intends to send to someone other than `self`
- The arguments that a message requires
- The order of those requirements

## 3.1.2 Coupling Between Objects

The more object A knows about object B, the more tightly coupled they are. The more tightly coupled two objects are, the more they behave like a single entity. Changes to object A force change in object B.

## 3.1.3 Other Dependencies

One especially destructive kind of dependency occurs where an object knows another knows another who knows something; that is, where many messages are chained together to reach behavior that lives in a distant object.

# 3.2 Writing Loosely Coupled Code

Some amount of dependency is inevitable because objects need to collaborate to produce the behavior of the whole. So, reducing dependencies means recognizing and removing the ones you don't need.

## 3.2.1 Inject Dependencies

**Problem with `Wheel.new` in `Gear#gear_inches`**
When `Gear` hard-codes a reference to `Wheel` deep inside its `gear_inches` method, it is explicitly declaring that it is only willing to calculate gear inches for instances of `Wheel`. `Gear` refuses to collaborate with any other kind of object, even if that object has a diameter and uses gears.

Using dependency injection to shape code relies on your ability to recognize that the responsibility for knowing the name of a class and the responsibility for knowing the name of a message to send to that class may belong in different objects. (**Factory**)

## 3.2.2 Isolate Dependencies

### Isolate instance creation

Isolate dependency (`Wheel.new`) from `Gear#gear-inches` method to `Gear#initialize`. This reveals the dependency instead of hiding it inside the class.

>Develop a habit of routinely injecting your dependencies.

### Isolate Vulnerable External Messages

This technique becomes necessary when a class contains embedded references to a *message* that is likely to change.

Example:
```ruby
def gear_inches
  #... A few lines of scary math
  foo = some_intermediate_result * wheel diameter
  #... More lines of scary math
end
```

`wheel.diameter` is embedded inside a complex method.

Removing the external dependency and encapsulating it into its own method:
```ruby
def gear_inches
  #... A few lines of scary math
  foo = some_intermediate_result * diameter
  #... More lines of scary math
end

def diameter
  wheel.diameter
end
```

Now, `gear_inches` can depend on a method sent to `self`. Earlier, `gear_inches` knew that `wheel` (external object) had a `diameter` (external message).

### Use keyword arguments (Ruby specific)

### Explicitly Define Defaults (initialize defaults)

### Isolate Multiparameter Inialization

The classes in your method should depend on code that you own; use a wrapping method to isolate external dependencies.

