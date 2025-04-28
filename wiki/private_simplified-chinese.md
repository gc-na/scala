<!--
Meta Description: # Scala 中的 private 修饰符详解 ## 摘要 在 Scala 中，`private` 修饰符用于限制字段和方法的可访问性，确保只有定义它们的类或对象内部可以访问这些成员。 ## 文档 `private` 是 Scala 中的一种访问控制修饰符，用于控制类成员（字段、方法）的可见性。它...
Meta Keywords: private, scala, int, person, def
-->

# Scala 中的 private 修饰符详解

## 摘要
在 Scala 中，`private` 修饰符用于限制字段和方法的可访问性，确保只有定义它们的类或对象内部可以访问这些成员。

## 文档
`private` 是 Scala 中的一种访问控制修饰符，用于控制类成员（字段、方法）的可见性。它的主要目的是增强封装性，防止外部代码直接访问类的内部实现。

### 用法
在 Scala 中，使用 `private` 修饰符时，可以应用于类的字段、方法以及嵌套类。被标记为 `private` 的成员只能在定义它们的类内部访问，外部类、子类或其他对象无法访问。

### 语法示例
```scala
class MyClass {
  private var secret: Int = 42

  private def revealSecret(): Int = secret
}
```

在上述示例中，`secret` 字段和 `revealSecret` 方法都是私有的，外部代码不能直接访问。

## 示例
以下是一些基本的使用示例：

### 示例 1: 基本使用
```scala
class Person {
  private var name: String = "John Doe"

  def getName: String = name
}

val person = new Person()
// 无法访问 person.name，因为它是私有的
println(person.getName) // 输出: John Doe
```

### 示例 2: 私有方法
```scala
class Calculator {
  private def add(x: Int, y: Int): Int = x + y

  def calculateSum(a: Int, b: Int): Int = add(a, b)
}

val calc = new Calculator()
// 无法直接调用 calc.add(2, 3) 会导致编译错误
println(calc.calculateSum(2, 3)) // 输出: 5
```

## 解释
使用 `private` 修饰符时需要注意以下几点：

1. **只能在同一类中访问**：被 `private` 修饰的成员只能在其定义的类内部访问，无法在子类或其他类中访问。
  
2. **嵌套类中的访问**：如果有嵌套类，外层类的 `private` 成员可以被嵌套类访问。

3. **与 `protected` 的区别**：与 `protected` 修饰符不同，`protected` 成员可以在子类中访问，而 `private` 成员则不能。

4. **编译时错误**：尝试从外部访问 `private` 成员将导致编译错误，确保在设计类时合理设计访问权限。

## 一句话总结
在 Scala 中，`private` 修饰符用于限制类成员的可见性，仅允许在定义它们的类内部访问。