<!--
Meta Description: # Scala 中的 "yield"：理解與應用 ## 摘要 在 Scala 中，`yield` 是用於生成集合的強大工具，尤其在使用循環表達式時。透過 `yield`，開發者能夠從現有的集合中生成新的集合，提升代碼的可讀性和簡潔性。 ## 文檔 `yield` 是 Scala 中的關鍵字，通常與 ...
Meta Keywords: yield, scala, val, numbers, newcollection
-->

# Scala 中的 "yield"：理解與應用

## 摘要
在 Scala 中，`yield` 是用於生成集合的強大工具，尤其在使用循環表達式時。透過 `yield`，開發者能夠從現有的集合中生成新的集合，提升代碼的可讀性和簡潔性。

## 文檔
`yield` 是 Scala 中的關鍵字，通常與 `for` 循環結合使用，以便從一個集合中提取和轉換數據，並生成一個新的集合。其主要功能是將每次迭代的結果收集起來，形成一個新的集合。

### 用法
`yield` 的基本語法如下：
```scala
val newCollection = for (element <- originalCollection) yield {
  // 轉換邏輯
}
```
在這段代碼中，`originalCollection` 中的每個 `element` 都會被轉換成一個新的格式，並在 `newCollection` 中收集結果。

### 詳情
- `yield` 可以用於各種集合類型，包括 `List`、`Set` 和 `Array` 等。
- 支持多層嵌套循環，能夠處理更複雜的數據結構。
- 可以與條件語句結合使用，進一步過濾生成的數據。

## 範例
以下是使用 `yield` 的基本範例：

```scala
// 將數字從 1 到 10 乘以 2
val numbers = 1 to 10
val doubled = for (n <- numbers) yield n * 2
println(doubled) // 輸出: Vector(2, 4, 6, 8, 10, 12, 14, 16, 18, 20)
```

另一個範例是結合條件過濾：
```scala
// 過濾出偶數並平方
val evenSquares = for (n <- numbers if n % 2 == 0) yield n * n
println(evenSquares) // 輸出: Vector(4, 16, 36, 64, 100)
```

## 解釋
在使用 `yield` 時，開發者需注意以下幾點：
- 確保在 `for` 循環中正確使用 `if` 條件，以防止生成不必要的元素。
- `yield` 會返回一個新的集合，原有的集合不會被改變，這意味著需要理解何時需要這種不變性。
- 在大數據集合上使用 `yield` 可能會導致性能問題，因為每次迭代都會生成新集合。

## 一行總結
在 Scala 中，`yield` 是一個強大的工具，用於從集合生成新集合，提升代碼的整潔性與可讀性。