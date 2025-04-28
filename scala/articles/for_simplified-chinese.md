<!--
Meta Description: # Scala 中的 "for" 循环使用指南 ## 概述 在 Scala 编程语言中，`for` 循环是一种强大的控制结构，用于遍历集合并执行重复操作。`for` 循环不仅支持基本的迭代，还允许使用条件和生成器实现复杂的数据处理。 ## 文档 `for` 循环的主要目的是简化对集合的遍历和操作。它...
Meta Keywords: scala, number, yield, numbers, val
-->

# Scala 中的 "for" 循环使用指南

## 概述
在 Scala 编程语言中，`for` 循环是一种强大的控制结构，用于遍历集合并执行重复操作。`for` 循环不仅支持基本的迭代，还允许使用条件和生成器实现复杂的数据处理。

## 文档
`for` 循环的主要目的是简化对集合的遍历和操作。它可以用于数组、列表、集合等多种数据类型。Scala 的 `for` 循环具有灵活性，可以与 `yield` 关键字结合使用，以生成新的集合。

### 语法
基本语法如下：
```scala
for (element <- collection) {
  // 执行的代码
}
```
这里，`element` 是集合中当前元素的变量，`collection` 是要遍历的集合。

### 其他用法
`for` 循环还可以与条件结合使用：
```scala
for (element <- collection if condition) {
  // 执行的代码
}
```
使用 `yield` 返回一个新集合：
```scala
val newCollection = for (element <- collection) yield {
  // 生成新元素的代码
}
```

## 示例
以下是一些基本的 `for` 循环示例：

### 示例 1：简单遍历
```scala
val numbers = List(1, 2, 3, 4, 5)
for (number <- numbers) {
  println(number)
}
```

### 示例 2：带条件的遍历
```scala
val numbers = List(1, 2, 3, 4, 5)
for (number <- numbers if number % 2 == 0) {
  println(number)
}
```

### 示例 3：使用 `yield` 创建新集合
```scala
val numbers = List(1, 2, 3, 4, 5)
val squares = for (number <- numbers) yield number * number
println(squares) // 输出: List(1, 4, 9, 16, 25)
```

## 解释
使用 `for` 循环时，常见的陷阱包括：

- **不可变性**：Scala 的集合通常是不可变的，使用 `yield` 时需要注意生成新的集合，而不是修改原有集合。
- **条件语句**：在条件语句中，确保逻辑正确，避免遗漏条件或错误的条件判断。
- **类型推导**：Scala 对类型推导非常强大，但在某些情况下，可能需要显式指定类型，以避免混淆。

## 一句话总结
Scala 中的 `for` 循环是一种高效的集合遍历工具，支持条件过滤和生成新集合。