<!--
Meta Description: # Understanding Sealed Classes and Traits in Scala: A Comprehensive Guide ## Synopsis In Scala, a `sealed` keyword is used to define a class or trait ...
Meta Keywords: sealed, case, class, trait, classes
-->

# Understanding Sealed Classes and Traits in Scala: A Comprehensive Guide

## Synopsis
In Scala, a `sealed` keyword is used to define a class or trait that restricts the inheritance of subclasses to the same file, promoting type safety and exhaustiveness in pattern matching.

## Documentation
### Purpose
The `sealed` modifier is a powerful feature in Scala that allows developers to define a limited class hierarchy. When a class or trait is marked as `sealed`, it can only be extended in the same file where it is defined. This encapsulation helps in maintaining control over the subclassing and enhances the safety of pattern matching.

### Usage
To declare a sealed class or trait, simply precede the class or trait definition with the `sealed` keyword. The subclasses must be defined in the same source file. This is particularly useful in situations where you want to ensure that all possible subclasses are known at compile-time, enhancing type safety.

### Details
- **Sealed Classes:** A sealed class can have multiple subclasses, which are defined in the same file. This provides a clear and manageable way to handle a closed set of types.
  
- **Sealed Traits:** Similarly, sealed traits can also be extended by classes or traits in the same file, allowing for a controlled environment for type definitions.

- **Pattern Matching:** When using sealed classes or traits in pattern matching, the Scala compiler knows all possible subclasses, allowing exhaustive checks and reducing runtime errors.

## Examples

### Example 1: Sealed Class
```scala
sealed class Animal
case class Dog(name: String) extends Animal
case class Cat(name: String) extends Animal

def describe(animal: Animal): String = animal match {
  case Dog(name) => s"This is a dog named $name."
  case Cat(name) => s"This is a cat named $name."
}
```

### Example 2: Sealed Trait
```scala
sealed trait Shape
case class Circle(radius: Double) extends Shape
case class Rectangle(width: Double, height: Double) extends Shape

def area(shape: Shape): Double = shape match {
  case Circle(radius) => math.Pi * radius * radius
  case Rectangle(width, height) => width * height
}
```

### Example 3: Exhaustiveness in Pattern Matching
```scala
sealed trait TrafficLight
case object Red extends TrafficLight
case object Yellow extends TrafficLight
case object Green extends TrafficLight

def signalAction(light: TrafficLight): String = light match {
  case Red    => "Stop!"
  case Yellow => "Caution!"
  case Green  => "Go!"
  // No need for a default case, all cases are covered.
}
```

## Explanation
### Common Pitfalls
1. **Extending Sealed Classes Outside the File:** One of the most common mistakes is attempting to extend a sealed class or trait outside of its defining file, which will result in a compilation error.
  
2. **Not Utilizing Exhaustive Pattern Matching:** While sealed classes provide exhaustive pattern matching capabilities, developers sometimes forget to handle all cases, leading to potential `MatchError` at runtime. Always ensure that all subclasses are accounted for.

3. **Overusing Sealed Classes:** While sealed classes offer benefits, overusing them can lead to overly complex designs. Consider if a sealed hierarchy is genuinely necessary, or if a more open architecture would suffice.

## One Line Summary
In Scala, the `sealed` keyword restricts class and trait inheritance to the same file, enhancing type safety and enabling exhaustive pattern matching.