<!--
Meta Description: # Scala 中的 def：定義函數的關鍵字 ## Synopsis 在 Scala 編程語言中，`def` 是用來定義函數的關鍵字，允許開發者創建可以重用的程式碼塊，從而提高程式的可讀性和可維護性。 ## Documentation `def` 是 Scala 中的核心構造之一，主要用於定義函數...
Meta Keywords: scala, def, int, string, hello
-->

# Scala 中的 def：定義函數的關鍵字

## Synopsis
在 Scala 編程語言中，`def` 是用來定義函數的關鍵字，允許開發者創建可以重用的程式碼塊，從而提高程式的可讀性和可維護性。

## Documentation
`def` 是 Scala 中的核心構造之一，主要用於定義函數。函數可以接收參數並返回一個值，並且可以使用可選的返回類型進行明確的類型聲明。函數的定義一般包含以下幾個部分：

- **函數名稱**：用來標識函數的名稱。
- **參數列表**：括號內的參數名稱及其類型。
- **返回類型**（可選）：使用冒號指定返回值的類型。
- **函數體**：用於實現函數邏輯的程式碼區塊。

### 语法
```scala
def 函數名稱(參數1: 類型1, 參數2: 類型2): 返回類型 = {
  // 函數體
}
```

## Examples
### 基本用法
```scala
// 定義一個簡單的加法函數
def add(a: Int, b: Int): Int = {
  a + b
}

// 使用函數
val sum = add(5, 3) // sum 會等於 8
```

### 無返回類型
```scala
// 定義一個無返回值的函數
def printMessage(message: String) = {
  println(message)
}

// 使用函數
printMessage("Hello, Scala!")
```

### 默認參數
```scala
// 使用默認參數的函數
def greet(name: String, greeting: String = "Hello") = {
  println(s"$greeting, $name!")
}

// 使用默認參數
greet("Alice") // 輸出: Hello, Alice!
greet("Bob", "Hi") // 輸出: Hi, Bob!
```

## Explanation
在使用 `def` 定義函數時，開發者應注意以下幾點：

- **函數命名規範**：函數名稱應該具有描述性，便於理解其功能。
- **類型推斷**：在很多情況下，Scala 會自動推斷返回類型，但明確指定類型能提高程式的可讀性。
- **嵌套函數**：Scala 允許在一個函數內部定義另外一個函數，這可以用於封裝邏輯。
- **可變參數**：Scala 支持可變長度的參數，使用 `*` 符號來實現。

### 常見問題
- **忘記返回類型**：雖然 Scala 可以自動推斷返回類型，但在某些情況下，明確聲明類型能避免潛在的錯誤。
- **命名衝突**：確保函數名稱不與其他變量或函數衝突，以免引發混淆。

## One Line Summary
`def` 是 Scala 中用來定義函數的關鍵字，讓開發者能夠創建可重用的程式碼塊。