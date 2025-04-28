<!--
Meta Description: # Scala 中的「protected」關鍵字詳解及用法 ## 概要 在 Scala 中，「protected」是一種訪問修飾符，用於限制對類成員的訪問權限。它允許只有該類及其子類訪問特定的成員。 ## 文檔 ### 目的 「protected」修飾符的主要目的是實現封裝性，讓類的內部細節不對外公...
Meta Keywords: protected, scala, dog, class, def
-->

# Scala 中的「protected」關鍵字詳解及用法

## 概要
在 Scala 中，「protected」是一種訪問修飾符，用於限制對類成員的訪問權限。它允許只有該類及其子類訪問特定的成員。

## 文檔
### 目的
「protected」修飾符的主要目的是實現封裝性，讓類的內部細節不對外公開，同時又允許子類訪問這些成員。這在繼承關係中非常有用，可以保持類的內部邏輯的安全性。

### 用法
在 Scala 中，可將「protected」用於變量、方法和類的成員。當你使用「protected」修飾符時，其可見性如下：
- **在定義類內部**：可以被該類內的所有成員訪問。
- **在子類中**：可以被子類訪問，包括在同一包內或不同包中的子類。
- **在其他類中**：無法直接訪問。

### 詳細
使用「protected」的語法如下：
```scala
class Base {
  protected def protectedMethod(): Unit = {
    println("這是一個受保護的方法")
  }
}

class Derived extends Base {
  def callProtectedMethod(): Unit = {
    protectedMethod() // 可以訪問
  }
}
```
如上例所示，「protectedMethod」方法在「Base」類中定義，並且可以在「Derived」子類中訪問。

## 示例
以下是幾個使用「protected」的基本範例：

```scala
class Animal {
  protected def makeSound(): Unit = {
    println("動物發出聲音")
  }
}

class Dog extends Animal {
  def bark(): Unit = {
    makeSound() // 可以訪問
    println("汪汪")
  }
}

val dog = new Dog()
dog.bark() // 輸出：動物發出聲音，汪汪
// dog.makeSound() // 錯誤：無法訪問受保護的方法
```

## 解釋
- **常見陷阱**：在非子類中，無法訪問受保護的成員，即使這些類在同一包內。
- **語境注意**：需了解「protected」的使用場景，並確保不會在不該訪問的地方使用，這可能導致編譯錯誤。
- **與「private」的區別**：與「private」相比，「protected」允許子類訪問，因此在設計繼承結構時，需要根據需要選擇適合的修飾符。

## 一句總結
在 Scala 中，「protected」關鍵字用於限制成員的訪問權限，允許只有該類及其子類訪問。