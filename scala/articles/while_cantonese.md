<!--
Meta Description: # Scala 中的 while 循環：用法與範例 ## 簡介 `while` 循環是 Scala 語言中的基本控制結構，用於重複執行一段程式碼，直到指定的條件不再滿足。這種迴圈特別適合於在不確定執行次數的情況下使用。 ## 文檔 `while` 循環的語法如下： ```scala while (條...
Meta Keywords: while, scala, count, input, true
-->

# Scala 中的 while 循環：用法與範例

## 簡介
`while` 循環是 Scala 語言中的基本控制結構，用於重複執行一段程式碼，直到指定的條件不再滿足。這種迴圈特別適合於在不確定執行次數的情況下使用。

## 文檔
`while` 循環的語法如下：

```scala
while (條件) {
  // 執行的程式碼
}
```

### 用途
`while` 循環的主要用途是根據特定條件重複執行一段程式碼，直到條件為假。這使得 `while` 循環非常適合於需要不斷檢查狀態的場景，例如等待用戶輸入或處理流數據。

### 使用方式
1. **條件**：在循環開始前評估的布爾表達式，若為 `true`，則執行循環體內的程式碼。
2. **循環體**：當條件為 `true` 時執行的程式碼塊。

## 範例
以下是 `while` 循環的基本用法示例：

### 示例 1：計數器
```scala
var count = 0
while (count < 5) {
  println(s"計數器: $count")
  count += 1
}
```
這段程式碼會輸出計數器的值，從 0 到 4。

### 示例 2：用戶輸入
```scala
import scala.io.StdIn._

var input = ""
while (input != "exit") {
  input = readLine("請輸入命令 (輸入 'exit' 退出): ")
  println(s"您輸入的命令是: $input")
}
```
在這個例子中，程式會持續要求用戶輸入，直到用戶輸入 "exit" 為止。

## 解釋
### 常見陷阱
- **無窮迴圈**：如果條件永遠為 `true`，則會導致無窮迴圈，必須小心在循環體內適當更新條件。
- **條件評估**：在使用 `while` 循環時，確保條件能在適當的時候返回 `false`，否則程序將無法終止。

### 附加說明
- `while` 循環可與 `break` 語句搭配使用，但 Scala 的 `break` 需要導入 `scala.util.control.Breaks`，且通常不建議在功能性編程中使用，因為這會使代碼的可讀性降低。

## 一句總結
`while` 循環在 Scala 中是一種用於根據指定條件重複執行程式碼的基本控制結構。