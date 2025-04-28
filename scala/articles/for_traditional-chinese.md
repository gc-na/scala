<!--
Meta Description: # Scala 中的 for 迴圈：用法、示例與注意事項 ## 概述 在 Scala 編程語言中，`for` 迴圈是一種強大的控制結構，用於遍歷集合、生成序列及執行重複操作。這個語法簡潔且易於理解，能夠提高代碼的可讀性。 ## 文檔 ### 目的 `for` 迴圈主要用於遍歷資料結構，如數組、列表和...
Meta Keywords: scala, yield, val, numbers, println
-->

# Scala 中的 for 迴圈：用法、示例與注意事項

## 概述
在 Scala 編程語言中，`for` 迴圈是一種強大的控制結構，用於遍歷集合、生成序列及執行重複操作。這個語法簡潔且易於理解，能夠提高代碼的可讀性。

## 文檔
### 目的
`for` 迴圈主要用於遍歷資料結構，如數組、列表和集合。它不僅可以用來進行簡單的迭代，還支援生成新的集合，並可與其他控制結構結合使用。

### 用法
在 Scala 中，`for` 迴圈的基本語法如下：

```scala
for (variable <- collection) {
  // 執行的操作
}
```

這裡，`variable` 是從 `collection` 中取得的每一個元素。您可以使用 `yield` 關鍵字來生成新的集合：

```scala
val newCollection = for (variable <- collection) yield {
  // 返回的操作
}
```

### 詳細說明
`for` 迴圈在 Scala 中支持多種用法：
- **簡單迴圈**：遍歷集合中的每一個元素。
- **條件過濾**：使用 `if` 條件來過濾元素。
- **多重迴圈**：嵌套使用多個 `for` 迴圈以達到更複雜的遍歷需求。

## 示例
### 基本用法
```scala
val numbers = List(1, 2, 3, 4, 5)
for (n <- numbers) {
  println(n)
}
```

### 使用 `yield` 生成新集合
```scala
val squares = for (n <- numbers) yield n * n
println(squares) // 輸出: List(1, 4, 9, 16, 25)
```

### 條件過濾
```scala
val evenNumbers = for (n <- numbers if n % 2 == 0) yield n
println(evenNumbers) // 輸出: List(2, 4)
```

### 多重迴圈
```scala
for (i <- 1 to 3; j <- 1 to 2) {
  println(s"i: $i, j: $j")
}
```

## 解釋
使用 `for` 迴圈時，開發者應注意以下幾點：
- **不可變性**：Scala 偏向使用不可變集合，這意味著在 `for` 迴圈中生成的新集合不會影響原始集合。
- **性能考量**：在處理大型集合時，`for` 迴圈的性能可能會受到影響，尤其是當多次迭代或過濾時。
- **語法錯誤**：確保使用正確的符號和結構，否則編譯器將無法正確解讀代碼。

## 一句話總結
`for` 迴圈在 Scala 中是一個靈活且強大的工具，適用於遍歷和生成集合的操作。