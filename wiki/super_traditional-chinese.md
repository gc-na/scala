<!--
Meta Description: # Scala中的「super」關鍵字：使用與範例 ## 簡介 在Scala編程語言中，「super」關鍵字用於訪問父類中的方法和屬性。這對於多重繼承和類的擴展特別重要，因為它提供了一種簡單有效的方式來調用被覆蓋的方法。 ## 文檔 ### 目的 「super」關鍵字的主要目的是允許子類訪問父類中的...
Meta Keywords: super, child, parent, greet, name
-->

# Scala中的「super」關鍵字：使用與範例

## 簡介
在Scala編程語言中，「super」關鍵字用於訪問父類中的方法和屬性。這對於多重繼承和類的擴展特別重要，因為它提供了一種簡單有效的方式來調用被覆蓋的方法。

## 文檔
### 目的
「super」關鍵字的主要目的是允許子類訪問父類中的成員（方法和屬性），尤其是在這些成員被子類覆蓋的情況下。

### 使用方式
在Scala中，使用「super」關鍵字的基本語法如下：

```scala
super.methodName
```

這樣的調用將指向父類中名為`methodName`的方法，而不是子類中同名的方法。

### 詳細說明
- **類繼承**：當一個類繼承自父類時，它可以使用「super」來調用父類的實現。
- **多重繼承**：Scala不支持多重繼承，但通過特質（trait）來模擬類似的行為。在這種情況下，「super」可以幫助確定調用哪一個特質中的方法。
- **構造器調用**：在子類的構造函數中，可以使用「super」來調用父類的構造函數。

## 範例
### 基本用法
以下是一個使用「super」的簡單範例：

```scala
class Parent {
  def greet(): String = {
    "Hello from Parent"
  }
}

class Child extends Parent {
  override def greet(): String = {
    super.greet() + " and Hello from Child"
  }
}

val child = new Child()
println(child.greet()) // 輸出: Hello from Parent and Hello from Child
```

在這個範例中，`Child`類的`greet`方法使用`super.greet()`來調用`Parent`類中的`greet`方法。

### 構造函數示例
```scala
class Parent(val name: String) {
  println(s"Parent created: $name")
}

class Child(name: String) extends Parent(name) {
  println(s"Child created: $name")
}

val child = new Child("Alice")
// 輸出:
// Parent created: Alice
// Child created: Alice
```

## 說明
- **常見陷阱**：在覆蓋父類方法時，若不正確使用「super」，可能會導致意外的行為或調用錯誤的方法。
- **特質中的使用**：當使用特質時，確保清楚調用的是哪一個特質中的方法，因為特質可以實現相同的方法。

## 總結
「super」關鍵字在Scala中是用於調用父類的方法和屬性的強大工具，能夠有效地解決方法覆蓋的問題。