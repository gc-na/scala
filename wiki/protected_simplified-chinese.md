<!--
Meta Description: # Scala 中的 "protected" 关键字详解 ## 概述 在 Scala 中，"protected" 是一种访问修饰符，用于控制类成员（属性和方法）的可见性。通过使用 "protected"，您可以确保类的成员只能在该类及其子类中访问，从而实现更好的封装。 ## 文档 ### 目的 "p...
Meta Keywords: protected, scala, sound, dog, class
-->

# Scala 中的 "protected" 关键字详解

## 概述
在 Scala 中，"protected" 是一种访问修饰符，用于控制类成员（属性和方法）的可见性。通过使用 "protected"，您可以确保类的成员只能在该类及其子类中访问，从而实现更好的封装。

## 文档
### 目的
"protected" 关键字的主要目的是限制对类成员的访问权限，只有当前类及其子类可以访问这些成员。这种机制有助于保护类的内部实现，防止外部代码直接操作内部状态。

### 用法
在 Scala 中，您可以通过在类成员前加上 "protected" 来定义受保护的成员。例如：

```scala
class Base {
  protected var x: Int = 0
  
  protected def increment(): Unit = {
    x += 1
  }
}

class Derived extends Base {
  def show(): Unit = {
    increment()  // 可以访问受保护的方法
    println(x)   // 可以访问受保护的变量
  }
}
```

在上面的例子中，`Base` 类中的 `x` 变量和 `increment` 方法是受保护的，因此 `Derived` 类可以访问它们，而外部类则无法访问。

### 详细说明
- **访问权限**: "protected" 成员可以被同一类的实例和所有子类的实例访问，但不能被外部类的实例访问。
- **构造函数**: "protected" 修饰符也可以用于构造函数，使得只有子类能够实例化该类。
- **伴生对象**: "protected" 成员在伴生对象中不可见，因此通常不应依赖于伴生对象来访问这些成员。

## 示例
以下是一个简单的示例，展示了如何使用 "protected" 修饰符：

```scala
class Animal {
  protected def sound(): String = "Some sound"
}

class Dog extends Animal {
  def bark(): Unit = {
    println(sound())  // 访问受保护的方法
  }
}

val dog = new Dog()
dog.bark()  // 输出: Some sound
// dog.sound()  // 编译错误: sound 是受保护的
```

## 说明
- **常见陷阱**: 许多初学者在使用 "protected" 时会误解其可见性，认为它可以在类外部被访问。实际上，"protected" 仅允许在类及其子类中访问，确保对类内部状态的保护。
- **子类访问**: 只有直接继承的子类可以访问 "protected" 成员，跨层级的子类访问将受到限制。
- **不适用于对象**: "protected" 不能用于顶级的对象或方法。

## 一句话总结
Scala 的 "protected" 关键字用于定义只能在类及其子类中访问的类成员，以实现更好的封装和数据保护。