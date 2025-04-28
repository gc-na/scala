<!--
Meta Description: # Scala 中的 "else" 語句：用法與示例 ## 概述 在 Scala 中，`else` 語句用於控制流程，特別是在條件判斷中。它與 `if` 語句配合使用，允許開發者根據不同的條件執行不同的代碼區塊。 ## 文檔 `else` 是一個關鍵字，用於在 `if` 語句中提供替代情況的執行路徑...
Meta Keywords: else, scala, false, 時執行的代碼, println
-->

# Scala 中的 "else" 語句：用法與示例

## 概述
在 Scala 中，`else` 語句用於控制流程，特別是在條件判斷中。它與 `if` 語句配合使用，允許開發者根據不同的條件執行不同的代碼區塊。

## 文檔
`else` 是一個關鍵字，用於在 `if` 語句中提供替代情況的執行路徑。當 `if` 條件判斷為 `false` 時，`else` 後的代碼將會被執行。

### 用法
`else` 的基本語法如下：

```scala
if (condition) {
  // 當 condition 為 true 時執行的代碼
} else {
  // 當 condition 為 false 時執行的代碼
}
```

可以與 `else if` 結合使用來處理多個條件：

```scala
if (condition1) {
  // 當 condition1 為 true 時執行的代碼
} else if (condition2) {
  // 當 condition1 為 false 且 condition2 為 true 時執行的代碼
} else {
  // 當 condition1 和 condition2 均為 false 時執行的代碼
}
```

## 示例
以下是一些使用 `else` 語句的基本示例：

### 示例 1：基本使用
```scala
val number = 10

if (number > 0) {
  println("數字是正數")
} else {
  println("數字不是正數")
}
```

### 示例 2：使用 else if
```scala
val score = 85

if (score >= 90) {
  println("優秀")
} else if (score >= 75) {
  println("良好")
} else {
  println("需要改進")
}
```

## 解釋
在使用 `else` 語句時，開發者需要注意以下幾個常見的陷阱：

1. **缺失的花括號**：如果 `if` 或 `else` 區塊只有一行代碼，花括號是可選的，但為了可讀性，建議始終使用花括號。
  
2. **邏輯錯誤**：確保條件的順序正確，`else if` 的條件將在前面的 `if` 條件為 `false` 時進行評估。

3. **使用條件表達式**：在 Scala 中，可以使用條件表達式（`if` 表達式）來返回值，而不僅僅是執行代碼塊。這樣可以在一行中使用 `if` 和 `else` 進行簡潔的條件賦值。

## 總結
`else` 語句是 Scala 中控制流程的關鍵組件，幫助開發者根據條件執行不同的代碼。