<!--
Meta Description: # Understanding the "protected" Access Modifier in Scala ## Synopsis The `protected` access modifier in Scala restricts the visibility of class member...
Meta Keywords: protected, class, access, scala, subclasses
-->

# Understanding the "protected" Access Modifier in Scala

## Synopsis
The `protected` access modifier in Scala restricts the visibility of class members to the class itself and its subclasses, providing a balance between encapsulation and flexibility in inheritance.

## Documentation
In Scala, the `protected` keyword is used to define access levels for class members (variables and methods). When a member is declared as `protected`, it can be accessed only within its own class and by subclasses (even if they are in different packages). This is particularly useful when you want to allow certain functionality to be inherited while still keeping it hidden from the outside world.

### Purpose
The main purpose of using `protected` is to enable a controlled level of encapsulation in the inheritance hierarchy. It allows subclasses to use and override methods or access variables without exposing them to the broader application context.

### Usage
To declare a member as `protected`, you simply prefix it with the `protected` keyword:

```scala
class Parent {
  protected def display(): Unit = {
    println("This is a protected method.")
  }
}

class Child extends Parent {
  def show(): Unit = {
    display() // Accessing the protected method from the parent class
  }
}
```

In the example above, `display()` is a protected method in the `Parent` class, which can be accessed within the `Child` class.

## Examples

### Example 1: Basic Usage of Protected
```scala
class Animal {
  protected def sound(): String = "Some sound"
}

class Dog extends Animal {
  def makeSound(): String = sound() // Accessing protected method
}

val dog = new Dog()
println(dog.makeSound()) // Outputs: Some sound
```

### Example 2: Protected Members in Subclasses
```scala
class Vehicle {
  protected var wheels: Int = 4
}

class Car extends Vehicle {
  def getWheels: Int = wheels // Accessing protected variable
}

val car = new Car()
println(car.getWheels) // Outputs: 4
```

### Example 3: Protected Constructors
```scala
class Base protected() {
  // Protected constructor
}

class Derived extends Base {
  // Can instantiate Base
}

val obj = new Derived() // Works, as Derived can call the protected constructor
```

## Explanation
While `protected` provides useful functionality, there are common pitfalls to be aware of:

1. **Visibility**: Members marked as `protected` cannot be accessed from instances of the class that are not subclasses. For example, if you try to access a protected member from an unrelated class, it will result in a compilation error.

2. **Package Access**: Unlike `private`, which restricts access to the class itself, `protected` allows subclasses in different packages to access the member. This can lead to unintended access if not carefully managed.

3. **Inheritance Hierarchy**: When using `protected`, it's essential to understand the inheritance hierarchy to prevent misuse or confusion regarding which classes can access the `protected` members.

4. **Mixing with Other Access Modifiers**: Be cautious when combining `protected` with other access modifiers like `private` or `public`, as this can lead to complex visibility situations that may be difficult to maintain.

## One Line Summary
The `protected` access modifier in Scala limits the visibility of class members to the class itself and its subclasses, promoting encapsulation while allowing inheritance.