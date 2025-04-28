<!--
Meta Description: # Scala 中的 Enum：用於定義枚舉類型的指南 ## 概述 在 Scala 中，`enum` 是一種用於定義枚舉類型的語法結構，允許開發者清晰地定義一組常量值。從 Scala 3 開始，`enum` 提供了一種更具表達力的方式來處理這類型的數據，並支持模式匹配和自定義方法。 ## 文檔 `e...
Meta Keywords: enum, case, scala, day, match
-->

# Scala 中的 Enum：用於定義枚舉類型的指南

## 概述
在 Scala 中，`enum` 是一種用於定義枚舉類型的語法結構，允許開發者清晰地定義一組常量值。從 Scala 3 開始，`enum` 提供了一種更具表達力的方式來處理這類型的數據，並支持模式匹配和自定義方法。

## 文檔
`enum` 的主要目的是為了簡化和增強類型安全的常量定義。使用 `enum` 可以創建一個具名的常量集合，這些常量可以用於控制流程、比較和其他操作。以下是 `enum` 的基本語法和使用方式：

### 語法
```scala
enum Color:
  case Red, Green, Blue
```

### 用法
- **定義枚舉**：使用 `enum` 關鍵字來定義一個枚舉，後面跟著一組用 `case` 關鍵字定義的常量。
- **模式匹配**：使用 `match` 語句可以根據枚舉值執行不同的邏輯。
- **方法**：可以為枚舉定義方法來增加功能性。

## 例子
### 基本用法
```scala
enum Day:
  case Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday

def describeDay(day: Day): String = day match
  case Day.Monday => "開始新的一周"
  case Day.Friday => "即將到來的週末"
  case _ => "普通的一天"

// 使用
val today = Day.Wednesday
println(describeDay(today)) // 輸出：普通的一天
```

### 帶有自定義方法的枚舉
```scala
enum Direction:
  case North, South, East, West

  def opposite: Direction = this match
    case North => South
    case South => North
    case East  => West
    case West  => East

// 使用
val dir = Direction.North
println(dir.opposite) // 輸出：South
```

## 解釋
使用 `enum` 時需要注意以下幾點：
- **可擴展性**：在 `enum` 中可以添加方法和其他成員，這使得枚舉不僅僅是常量集合。
- **模式匹配的安全性**：使用 `match` 語句能夠提供編譯時檢查，避免使用未定義的枚舉值。
- **不支持繼承**：枚舉類型不能繼承其他類或枚舉，這是為了保持其簡潔性和穩定性。

## 一句總結
Scala 的 `enum` 提供了一種強大且類型安全的方式來定義和使用常量值。