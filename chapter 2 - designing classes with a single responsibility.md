
## Grouping Methods into Classes

The classes you create will affect how you think about your application forever. They define a virtual world, one that constrains the imagination of everyone downstream.

Despite the importance of correctly grouping methods into classes, at this early stage of your project you cannot possibly get it right.

>Design is the art of preserving changeability than it is the act of achieving perfection.

## Organizing Code to Allow for Easy Changes

We define *easy to change* as:
- changes have no unexpected side effects,
- small changes in requirements require correspondingly small changes in code,
- existing code is easy to reuse, and
- the easiest way to make a change is to add code that in itself is easy to change

then the code you write should have the following qualities. Code should be:
- **Transparent**
- **Reasonable**
- **Usable**
- **Exemplary**

## Why Single Responsibility Matters

Applications that are easy to change consists of classes that are easy to reuse.

A class that has more than one responsibility is difficult to reuse. The various responsibilities are likely thoroughly entangled *within* the class. If you want to reuse some (but not all) of its behavior, it is impossible to get only the parts you need. You are faced with two options and neither is particularly appealing.

More responsibility means many reasons to change. Each time it changes, there's a possibility of breaking every class that depends on it.

## Determining If a Class Has a Single Responsibility

Re-phrasng methods of a class ought to make sense.
Ex: 
1. "Mr.Gear what is your ratio" (reasonable)
2. "Mr.Gear what are your gear inches" (shaky ground)
3. "Mr.Gear what is your tire (size)?" (ridiculous)

Try to describe a class in one sentence. If it contains words like "and", "or" then it have more than one responsibility
"Calculate the effect that a gear has on a bicycle" (gear_inches is now on solid ground but tire size is still shaky)

Gear has more than one responsibility, but it's not obvious what should be done.

>[!note]
>SRP doesn't require that a class do only one very narrow thing or that it change for only a single nitpicky reason; instead SRP requires that a class be cohesive - that everything the class does be highly related to its purpose.


## Determining When to Make Design Decisions

Do not feel compelled to make design decisions prematurely. Resist, even if you fear your code would dismay the design gurus.

Always ask yourself, "*What is the future cost of doing nothing today?*". If the answer is no, then don't make a design decision.

Conveniently, the new requirements will supply the exact information you need to make good design decisions.

## Write Code That Embraces Change

### Depend on Behavior, Not Data

**Hide Instance Variables** : Always wrap instance variables in accessor methods instead of directly referring to variables. You should hide data from yourself. Doing so protects the code from being affected by unexpected changes. 

Data very often has behavior that you don't yet know about. Send messages to access variables even if you think of them as data.

**Hide Data Structures** : If being attached to an instance variable is bad, depending on a complicated data structure is worse.
```ruby
class ObscuringReferences
  attr_reader :data
  def initialize(data)
    @data = data
  end
  
  def diameters
    #0 is rim, 1 is tire
    data.collect { |cell| cell[0] + (cell[1] * 2)}
  end
  # ... many other methods that index into the array
end
```

```ruby
# rim and tire sizes (in mm) in a 2d array
@data = [[622, 20], [622, 23], [559, 30], [559, 40]]
```

To do anything useful, each sender of `data` must have complete knowledge of what piece of data is at which index in the array.

Direct references into complicated data structures are confusing, because they obscure what the data really is, and they are a maintenance nightmare, because every reference will need to be changed when the structure of the array changes.

To separate structure from meaning in Ruby, use `Struct` class to wrap a structure.

```ruby
class RevealingReferences
  attr_reader :wheels
  def initialize(data)
    @wheels = wheelify(data)
  end
  
  def diameters
    wheels.collect { |wheel| wheel.rim + (wheel.tire * 2) }
  end
  
  # now everyone can send rim/tire to wheel
  Wheel = Struct.new(:rim, :tire)
  def wheelify(data)
    data.collect { |cell| Wheel.new(cell[0], cell[1]) }
  end
end
```

The `wheelfiy` method above isolates the messy structural information and DRYs out the code. It makes this class far more tolerant of change.

Although it might be easier to just have an array of Wheels to begin with, it is not always possible. If you can control the input, pass in a useful object, but if you are compelled to take a messy structure, hide the mess even from yourself.

### Enforce Single Responsibility Everywhere

**Extract Extra Responsibilities from Methods**
Just like classes methods should also follow single responsibility principle.
```ruby
def gear_inches
  ratio * diameter
end

def diameter
  rim + (tire * 2)
end
```

Gear's diameter method depends solely on things in Wheel. This suggest that method ought to be in Wheel.

Gear is definitely responsible for calculating `gear_inches`, but Gear should not be calculating Wheel diameter.

