<!--
Meta Description: # Understanding the "extends" Keyword in Scala: A Comprehensive Guide ## Synopsis The `extends` keyword in Scala is pivotal for defining class inherit...
Meta Keywords: class, extends, scala, inheritance, abstract
-->

# Understanding the "extends" Keyword in Scala: A Comprehensive Guide

## Synopsis
The `extends` keyword in Scala is pivotal for defining class inheritance and trait mixing. It allows a class to inherit the properties and methods of another class or trait, facilitating code reuse and polymorphism.

## Documentation
In Scala, `extends` is used to create a subclass from a superclass or to implement a trait. It establishes an "is-a" relationship between the derived class and the base class, enabling the derived class to inherit the functionalities of the base class. 

### Purpose
The primary purpose of using `extends` is to enable inheritance, allowing a new class to inherit fields and methods from an existing class. This mechanism promotes code reusability and a hierarchical class structure.

### Usage
To use `extends`, you specify it after the class name followed by the superclass or trait you wish to inherit from. The syntax is as follows:

```scala
class SubClassName extends SuperClassName {
  // Class body
}
```

You can also extend multiple traits using the `with` keyword, like so:

```scala
class SubClassName extends SuperClassName with TraitName {
  // Class body
}
```

### Details
- **Single Inheritance**: Scala supports single class inheritance where a class can inherit from only one superclass.
- **Multiple Traits**: A class can implement multiple traits, which allows for a form of multiple inheritance.
- **Abstract Classes**: If the superclass is an abstract class, the derived class must implement the abstract methods defined in the superclass.
- **Constructor Inheritance**: When extending a class, the constructor of the superclass can be called using `extends` followed by parentheses.

## Examples
### Basic Class Inheritance
```scala
class Animal {
  def sound(): String = "Animal sound"
}

class Dog extends Animal {
  override def sound(): String = "Bark"
}

val dog = new Dog()
println(dog.sound()) // Output: Bark
```

### Trait Implementation
```scala
trait CanFly {
  def fly(): String
}

class Bird extends Animal with CanFly {
  override def fly(): String = "Flies high"
}

val sparrow = new Bird()
println(sparrow.sound()) // Output: Animal sound
println(sparrow.fly())   // Output: Flies high
```

### Abstract Class Example
```scala
abstract class Shape {
  def area(): Double
}

class Circle(radius: Double) extends Shape {
  override def area(): Double = Math.PI * radius * radius
}

val circle = new Circle(5)
println(circle.area()) // Output: 78.53981633974483
```

## Explanation
When using `extends`, it is essential to be aware of a few common pitfalls:
- **Single vs. Multiple Inheritance**: Remember that Scala does not support multiple inheritance from classes but allows mixing in multiple traits. Misunderstanding this can lead to design issues.
- **Abstract Classes**: If you try to instantiate a class derived from an abstract class without implementing all its abstract members, the code will not compile.
- **Method Overriding**: When overriding methods, ensure to use the `override` keyword; failing to do so results in a compilation error.

## One Line Summary
The `extends` keyword in Scala is used to inherit properties and methods from a superclass or trait, facilitating code reuse and the implementation of polymorphism.