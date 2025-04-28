<!--
Meta Description: # Scala 中的類 (Class) — 定義、用法與示例 ## 摘要 在 Scala 中，「類」是一種用於定義對象的模板，能夠封裝數據和行為。類是面向對象編程的核心概念，提供了創建複雜數據結構的能力。 ## 文檔 在 Scala 中，類是一種用於創建對象的結構。它包含了屬性（變量）和方法（函數）...
Meta Keywords: scala, val, var, person, class
-->

# Scala 中的類 (Class) — 定義、用法與示例

## 摘要
在 Scala 中，「類」是一種用於定義對象的模板，能夠封裝數據和行為。類是面向對象編程的核心概念，提供了創建複雜數據結構的能力。

## 文檔
在 Scala 中，類是一種用於創建對象的結構。它包含了屬性（變量）和方法（函數）。類的主要目的是組織代碼，促進重用性和可維護性。Scala 支持單一繼承和混合繼承，使得類的設計靈活且功能強大。

### 類的定義
類的基本語法如下：
```scala
class ClassName(param1: Type1, param2: Type2) {
  // 屬性定義
  var attribute1: Type1 = param1
  val attribute2: Type2 = param2

  // 方法定義
  def methodName(): ReturnType = {
    // 方法體
  }
}
```

### 類的使用
要創建類的實例，可以使用 `new` 關鍵字：
```scala
val instance = new ClassName(value1, value2)
```

## 示例
以下是一個簡單的 Scala 類的示例：

```scala
class Person(val name: String, var age: Int) {
  def greet(): String = {
    s"你好，我的名字是 $name，今年 $age 歲。"
  }
}

// 創建實例並調用方法
val person = new Person("小明", 25)
println(person.greet())  // 輸出: 你好，我的名字是 小明，今年 25 歲。
```

## 解釋
在 Scala 中使用類時，開發者需注意以下幾點：

- **屬性聲明**：使用 `val` 和 `var` 聲明屬性，`val` 表示不可變，`var` 表示可變。
- **主構造器**：類的參數可以在類名後面直接聲明，這樣可以簡化代碼。
- **繼承**：Scala 不支持多重繼承，但可以使用特 trait 來實現類似功能。
- **伴隨對象**：可以定義伴隨對象（companion object）來創建類的靜態方法和常量。

常見的陷阱包括不正確初始化屬性和不理解 `val` 與 `var` 的區別。

## 一行總結
在 Scala 中，「類」用於創建對象的模板，封裝數據和行為，是面向對象編程的基石。