<!--
Meta Description: # Scala 中的 "super" 關鍵字：超類別的引用 ## 概要 在 Scala 編程語言中，`super` 關鍵字用於引用超類別的方法和屬性，特別是在子類別中重寫了父類別的方法時。這使得子類別能夠調用父類別的實現，從而增強了代碼的可重用性和可讀性。 ## 文檔 `super` 關鍵字的主要用...
Meta Keywords: super, display, scala, class, def
-->

# Scala 中的 "super" 關鍵字：超類別的引用

## 概要
在 Scala 編程語言中，`super` 關鍵字用於引用超類別的方法和屬性，特別是在子類別中重寫了父類別的方法時。這使得子類別能夠調用父類別的實現，從而增強了代碼的可重用性和可讀性。

## 文檔
`super` 關鍵字的主要用途是讓子類別能夠訪問父類別的成員，無論是方法還是變量。當子類別重寫了父類別的方法時，`super` 可以用來調用被重寫的方法的原始實現。這在需要擴展父類別的功能而又不想完全覆蓋其行為時特別有用。

### 用法
在 Scala 中，使用 `super` 的基本語法如下：

```scala
class Parent {
  def greet(): Unit = {
    println("Hello from Parent")
  }
}

class Child extends Parent {
  override def greet(): Unit = {
    super.greet() // 調用父類別的 greet 方法
    println("Hello from Child")
  }
}
```

在上面的例子中，`Child` 類別的 `greet` 方法重寫了 `Parent` 類別的 `greet` 方法，但它仍然可以調用父類別的實現。

## 範例
以下是使用 `super` 的一些基本範例：

### 範例 1：簡單的超類別方法調用

```scala
class Animal {
  def sound(): Unit = {
    println("Animal sound")
  }
}

class Dog extends Animal {
  override def sound(): Unit = {
    super.sound() // 調用 Animal 的 sound 方法
    println("Bark")
  }
}

val dog = new Dog()
dog.sound()
// 輸出:
// Animal sound
// Bark
```

### 範例 2：多層繼承

```scala
class A {
  def display(): Unit = {
    println("A's display")
  }
}

class B extends A {
  override def display(): Unit = {
    println("B's display")
  }
}

class C extends B {
  override def display(): Unit = {
    super.display() // 調用 B 的 display 方法
    println("C's display")
  }
}

val c = new C()
c.display()
// 輸出:
// B's display
// C's display
```

## 解釋
使用 `super` 時，有幾個常見的陷阱和注意事項：
- **多重繼承問題**：在 Scala 中，類別不支持多重繼承，但可以通過特 traits 的結合來實現類似的行為。使用 `super` 時，需要注意特定的繼承順序。
- **隱式調用**：如果在重寫的方法中不明確調用 `super`，則父類別的方法將不會被執行，這可能會導致某些邏輯或初始化步驟被跳過。

## 總結
在 Scala 中，`super` 關鍵字用於在子類別中訪問父類別的方法和屬性，特別是在方法被重寫的情況下，這增強了代碼的靈活性和可讀性。