<!--
Meta Description: # Scala 中的 "extends" 關鍵字：繼承與擴展的基礎 ## 簡介 在 Scala 中，`extends` 關鍵字用於定義類別的繼承關係。透過這個關鍵字，開發者可以創建一個新的類別，並從現有的類別獲取屬性和方法，從而實現代碼的重用和擴展。 ## 文件說明 `extends` 是 Scal...
Meta Keywords: scala, extends, animal, sound, class
-->

# Scala 中的 "extends" 關鍵字：繼承與擴展的基礎

## 簡介
在 Scala 中，`extends` 關鍵字用於定義類別的繼承關係。透過這個關鍵字，開發者可以創建一個新的類別，並從現有的類別獲取屬性和方法，從而實現代碼的重用和擴展。

## 文件說明
`extends` 是 Scala 的一個關鍵字，用於表示一個類別（子類）繼承自另一個類別（父類）。這使得子類擁有父類的所有特徵，並且可以進一步擴展或重寫父類的方法。Scala 支持單一繼承，即一個類只能繼承自一個父類，但可以混合使用特徵（traits）來實現多重繼承的效果。

### 目的
- 促進代碼重用：子類可以繼承父類的方法和屬性。
- 提供多態性：透過繼承，子類可以重寫父類的方法，實現不同的行為。
- 清晰的層次結構：透過明確的繼承關係，代碼結構更加清晰易懂。

### 使用方式
`extends` 的基本語法如下：
```scala
class 子類名 extends 父類名 {
  // 額外屬性和方法
}
```

## 範例
### 基本範例
以下是一個簡單的類別繼承範例：

```scala
// 定義一個父類 Animal
class Animal {
  def sound(): String = {
    "Animal sound"
  }
}

// 定義一個子類 Dog，繼承自 Animal
class Dog extends Animal {
  override def sound(): String = {
    "Bark"
  }
}

// 使用子類
val myDog = new Dog()
println(myDog.sound())  // 輸出: Bark
```

### 混合特徵的範例
Scala 允許使用特徵來擴展類的功能，如下所示：

```scala
// 定義一個特徵 CanRun
trait CanRun {
  def run(): String = {
    "Running"
  }
}

// 定義一個子類 Cat，繼承自 Animal 並混合 CanRun 特徵
class Cat extends Animal with CanRun {
  override def sound(): String = {
    "Meow"
  }
}

// 使用子類
val myCat = new Cat()
println(myCat.sound())  // 輸出: Meow
println(myCat.run())    // 輸出: Running
```

## 說明
在使用 `extends` 時，有幾個常見的注意事項：
- **單一繼承**：Scala 不支持多重繼承，但可以使用特徵來實現類似的效果。
- **方法重寫**：在子類中重寫父類的方法時，必須使用 `override` 關鍵字。
- **父類的構造函數**：如果父類有構造函數，子類在定義時需要顯式調用父類的構造函數。

## 一句總結
在 Scala 中，`extends` 關鍵字用於創建類別間的繼承關係，從而實現代碼的重用和擴展。