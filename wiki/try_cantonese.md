<!--
Meta Description: # Scala 中的 try: 錯誤處理的基本工具 ## Synopsis 在 Scala 中，`try` 是用來處理異常的一個基本控制結構，使得開發者能夠捕捉和處理運行時的錯誤，從而提高程式的穩定性和可預測性。 ## Documentation `try` 語句的主要目的是捕捉程式運行過程中可能出...
Meta Keywords: try, catch, scala, case, finally
-->

# Scala 中的 try: 錯誤處理的基本工具

## Synopsis
在 Scala 中，`try` 是用來處理異常的一個基本控制結構，使得開發者能夠捕捉和處理運行時的錯誤，從而提高程式的穩定性和可預測性。

## Documentation
`try` 語句的主要目的是捕捉程式運行過程中可能出現的異常。它的基本結構如下：

```scala
try {
  // 可能會引發異常的程式碼
} catch {
  case e: ExceptionType => {
    // 處理異常的程式碼
  }
} finally {
  // 可選的清理程式碼，無論是否發生異常都會執行
}
```

- **try**: 包含可能引發異常的程式碼。
- **catch**: 用來捕捉異常，並執行相應的處理程式碼。可以有多個 `case` 來處理不同類型的異常。
- **finally**: 無論是否發生異常，這部分程式碼都會執行，通常用於資源釋放等清理任務。

## Examples
### 基本示例
以下是一個簡單的例子，演示如何使用 `try` 來捕捉除零異常：

```scala
val numerator = 10
val denominator = 0

val result = try {
  numerator / denominator
} catch {
  case e: ArithmeticException => "除零錯誤"
}

println(result) // 輸出: 除零錯誤
```

### 捕捉多個異常
可以使用多個 `case` 來捕捉不同類型的異常：

```scala
def safeDivide(a: Int, b: Int): String = {
  try {
    (a / b).toString
  } catch {
    case e: ArithmeticException => "除零錯誤"
    case e: Exception => "發生其他錯誤"
  }
}

println(safeDivide(10, 0)) // 輸出: 除零錯誤
println(safeDivide(10, 2)) // 輸出: 5
```

## Explanation
在使用 `try` 的過程中，有一些常見的陷阱和注意事項：

1. **未捕捉的異常**: 如果 `catch` 部分未涵蓋某種異常，則該異常會在運行時導致程式崩潰。
2. **性能考量**: 使用 `try` 的性能開銷相對較大，尤其在高頻次的呼叫中，應謹慎使用。
3. **finally 的使用**: `finally` 块非常有用，但是如果在 `try` 或 `catch` 中有 `return` 語句，`finally` 仍會執行，但返回的值會是 `try` 或 `catch` 中的值，而不是 `finally` 中的值。

## One Line Summary
在 Scala 中，`try` 是用來捕捉和處理異常的控制結構，以提高程式的穩定性和可預測性。