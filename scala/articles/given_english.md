<!--
Meta Description: # Understanding the 'given' Keyword in Scala: An Essential Guide ## Synopsis The `given` keyword in Scala is a powerful feature introduced in Scala 3,...
Meta Keywords: given, scala, instances, instance, using
-->

# Understanding the 'given' Keyword in Scala: An Essential Guide

## Synopsis
The `given` keyword in Scala is a powerful feature introduced in Scala 3, enabling the definition of given instances for type class instances, enhancing the language's capability for contextually passing parameters and promoting better code organization.

## Documentation
In Scala, the `given` keyword is used to define instances of type classes that can be automatically passed to methods that require them. This feature simplifies the process of providing implicit parameters, making code more readable and maintainable.

### Purpose
The primary purpose of `given` is to allow developers to create contextually relevant instances that can be automatically derived by the compiler when needed. This eliminates the need for explicit parameter passing, streamlining function calls and enhancing code expressiveness.

### Usage
The `given` keyword is used in conjunction with the `using` keyword. When you define a method that requires an implicit parameter, you can specify that parameter using `using`. The compiler will automatically resolve and provide the appropriate `given` instance.

#### Defining a Given Instance
To create a given instance, you use the following syntax:
```scala
given [Type] as [TypeClass] = new [TypeClass] {
  // implementation
}
```

#### Example Method Using Given Instance
A method that utilizes a given instance would look like:
```scala
def myMethod(using myInstance: MyTypeClass): Unit = {
  // implementation
}
```

### Details
1. **Scope and Visibility**: The scope of a `given` instance is determined by where it is defined. It can be defined at the top level, within a class, or within a trait. The visibility of the given instance follows standard Scala visibility rules.

2. **Multiple Given Instances**: If multiple `given` instances are available for a particular type, the compiler will raise ambiguity errors. Developers must ensure that only one `given` instance is applicable in the context.

3. **Combining With Other Features**: The `given` feature works well with the `extension` methods, allowing for flexible and expressive APIs.

## Examples
### Basic Example

```scala
trait Show[A] {
  def show(a: A): String
}

given Show[Int] with {
  def show(a: Int): String = a.toString
}

def printValue[A](value: A)(using showInstance: Show[A]): Unit = {
  println(showInstance.show(value))
}

// Usage
printValue(42) // Output: 42
```

### Using Given Instances with Custom Types

```scala
case class Person(name: String, age: Int)

given Show[Person] with {
  def show(person: Person): String = s"${person.name}, Age: ${person.age}"
}

// Usage
printValue(Person("Alice", 30)) // Output: Alice, Age: 30
```

## Explanation
When using the `given` keyword, it's important to remember the following common pitfalls:

- **Ambiguity**: If multiple `given` instances are defined for the same type, the compiler will not know which one to use, leading to compilation errors. Make sure to avoid naming clashes or provide clear contexts for each instance.

- **Scope Issues**: A `given` instance defined in a local scope (e.g., inside a method) will not be accessible outside that scope. Ensure that `given` instances are defined where they are needed.

- **Performance Considerations**: While `given` makes code cleaner, excessive use of implicit parameters can lead to performance overhead. Always evaluate if the use of `given` enhances code readability without sacrificing performance.

## One Line Summary
The `given` keyword in Scala simplifies the provision of type class instances, enabling automatic passing of parameters for cleaner and more maintainable code.