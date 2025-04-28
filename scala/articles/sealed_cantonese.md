<!--
Meta Description: # Scala 中的 "sealed" 關鍵字：用於增強類型安全性 ## 簡介 在 Scala 編程語言中，`sealed` 關鍵字用於聲明密封類（sealed class）或密封特質（sealed trait）。密封類和密封特質能夠限制其子類型的定義範圍，這樣可以提高類型安全性並幫助編譯器在模式匹...
Meta Keywords: sealed, shape, case, scala, class
-->

# Scala 中的 "sealed" 關鍵字：用於增強類型安全性

## 簡介
在 Scala 編程語言中，`sealed` 關鍵字用於聲明密封類（sealed class）或密封特質（sealed trait）。密封類和密封特質能夠限制其子類型的定義範圍，這樣可以提高類型安全性並幫助編譯器在模式匹配時提供更好的錯誤檢查。

## 文檔
### 目的
`sealed` 關鍵字的主要目的是限制類或特質的繼承。當一個類或特質被標記為密封時，所有的子類型必須在同一個檔案中定義，這樣可以確保所有可能的子類型都被考慮到，並且可以讓編譯器在進行模式匹配時發出警告，從而避免潛在的錯誤。

### 用法
要使用 `sealed` 關鍵字，只需在類或特質聲明前添加 `sealed` 關鍵字。例如：

```scala
sealed trait Animal
case class Dog(name: String) extends Animal
case class Cat(name: String) extends Animal
```

在這個例子中，`Animal` 是一個密封特質，`Dog` 和 `Cat` 是其子類型。所有的子類型必須在同一檔案中定義。

## 範例
### 基本用法
以下是一個使用 `sealed` 的簡單範例：

```scala
sealed trait Shape
case class Circle(radius: Double) extends Shape
case class Rectangle(width: Double, height: Double) extends Shape

def area(shape: Shape): Double = shape match {
  case Circle(radius) => Math.PI * radius * radius
  case Rectangle(width, height) => width * height
}
```

在這個例子中，`Shape` 是一個密封特質，`Circle` 和 `Rectangle` 是其唯一的子類型。`area` 函數使用模式匹配來計算不同形狀的面積。

## 解釋
使用 `sealed` 關鍵字有幾個常見的陷阱和注意事項：

1. **必須在同一檔案中定義子類型**：所有的子類型必須在與密封類或密封特質相同的檔案中聲明，否則編譯器會報錯。

2. **只能在頂層或對象中使用**：密封類和特質不能在其他類或特質內部定義。

3. **模式匹配的優勢**：由於所有子類型都在同一檔案中定義，編譯器能夠確保在使用模式匹配時考慮到所有可能的情況，使得代碼更安全。

## 一句總結
在 Scala 中，`sealed` 關鍵字用來限制類型的繼承範圍，增強類型安全性並改善模式匹配的準確性。