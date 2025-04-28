<!--
Meta Description: # Scala 中的模式匹配 (match) ## 概述 在 Scala 中，`match` 是一種強大的控制結構，用於實現模式匹配。這種語法讓開發者能夠以清晰且簡潔的方式檢查變數的值並根據情況執行不同的代碼塊。 ## 文檔 ### 目的 `match` 語句用於檢查一個表達式的值，並將其與多個模式...
Meta Keywords: match, case, scala, val, result
-->

# Scala 中的模式匹配 (match)

## 概述
在 Scala 中，`match` 是一種強大的控制結構，用於實現模式匹配。這種語法讓開發者能夠以清晰且簡潔的方式檢查變數的值並根據情況執行不同的代碼塊。

## 文檔
### 目的
`match` 語句用於檢查一個表達式的值，並將其與多個模式進行比較。這使得根據不同的條件執行相應的代碼變得更為簡單和可讀。

### 使用方式
`match` 語句的基本語法如下：

```scala
val result = value match {
  case pattern1 => result1
  case pattern2 => result2
  case _ => defaultResult
}
```

在這裡，`value` 是我們要匹配的值，`case` 是我們要比較的模式，而 `result` 是根據匹配的模式返回的結果。`_` 是一個通配符，用於匹配所有其他未被明確列出的情況。

### 詳細信息
- `match` 支持多種模式，包括字面量、變量、類型檢查、序列和元組等。
- 可以使用 `if` 語句添加額外條件。
- `match` 是一個表達式，這意味著它會返回一個值。

## 範例
### 基本用法
以下是使用 `match` 的基本示例：

```scala
val day = "星期一"
val isWeekday = day match {
  case "星期一" | "星期二" | "星期三" | "星期四" | "星期五" => true
  case "星期六" | "星期日" => false
  case _ => false
}

println(isWeekday) // 輸出: true
```

### 帶條件的模式
```scala
val num = 15
val result = num match {
  case x if x < 0 => "負數"
  case x if x == 0 => "零"
  case x if x > 0 => "正數"
}

println(result) // 輸出: 正數
```

## 解釋
在使用 `match` 時，開發者可能會遇到以下常見問題：
- **未覆蓋所有情況**：若沒有提供通配符 `_`，則當沒有匹配的情況時，將會拋出 `MatchError`。
- **類型不匹配**：如果模式和被匹配的值類型不一致，則會導致無法匹配的情況。
- **複雜性**：過於複雜的模式可能導致可讀性下降，建議保持模式簡潔。

## 總結
`match` 是 Scala 中一個強大且靈活的模式匹配工具，可用於基於值執行不同的邏輯。