<!--
Meta Description: # Scala中的抽象類別和抽象方法 ## 摘要 在Scala中，抽象類別和抽象方法是面向對象編程的重要概念，允許開發者定義不完全的類別和方法，從而促進代碼的重用與擴展。 ## 文檔 ### 目的 抽象類別是不能被實例化的類別，主要用於定義子類別必須實現的接口。抽象方法則是沒有具體實現的方法，子類別...
Meta Keywords: animal, sound, class, def, abstract
-->

# Scala中的抽象類別和抽象方法

## 摘要
在Scala中，抽象類別和抽象方法是面向對象編程的重要概念，允許開發者定義不完全的類別和方法，從而促進代碼的重用與擴展。

## 文檔
### 目的
抽象類別是不能被實例化的類別，主要用於定義子類別必須實現的接口。抽象方法則是沒有具體實現的方法，子類別必須提供具體的實現。

### 用法
在Scala中，使用 `abstract` 關鍵字來定義抽象類別和抽象方法。以下是基本語法：

```scala
abstract class ClassName {
  def abstractMethodName(param: Type): ReturnType    // 抽象方法
}
```

### 詳細說明
1. **抽象類別**：可以包含抽象方法和具體方法。抽象類別的主要用途是提供一個基礎類別，讓其他類別繼承並擴展。
2. **抽象方法**：必須在子類中實現，否則子類也必須聲明為抽象類別。
3. **不能實例化**：抽象類別無法直接創建實例，必須通過子類來實現。

## 示例
### 定義抽象類別和抽象方法
```scala
abstract class Animal {
  def sound(): String  // 抽象方法
}

class Dog extends Animal {
  def sound(): String = "Woof"  // 實現抽象方法
}

class Cat extends Animal {
  def sound(): String = "Meow"  // 實現抽象方法
}

// 使用
val myDog: Animal = new Dog()
println(myDog.sound())  // 輸出: Woof

val myCat: Animal = new Cat()
println(myCat.sound())  // 輸出: Meow
```

## 解釋
### 常見陷阱
- **未實現抽象方法**：如果子類沒有實現所有的抽象方法，則會導致編譯錯誤。
- **抽象類別實例化**：嘗試實例化抽象類別會導致編譯錯誤。

### 額外說明
- 抽象類別可以包含其他的具體方法和變數，這使得它們可以提供一些公共的行為給子類。
- 抽象類別與介面（traits）有相似之處，但介面更為靈活且可以多重繼承。

## 一行總結
抽象類別和抽象方法是Scala中定義不完全類別的工具，促進了代碼的重用與擴展。