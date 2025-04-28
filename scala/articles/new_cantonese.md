<!--
Meta Description: # Scala 中的 "new" 關鍵字：用於物件創建的基礎 ## 簡介 在 Scala 程式語言中，`new` 關鍵字是用來創建物件的主要方法。它允許開發者基於類別的定義來實例化物件，在物件導向程式設計中扮演著關鍵的角色。 ## 文檔 ### 目的 `new` 關鍵字用於創建類的實例。當你想要使用...
Meta Keywords: new, scala, val, john, animal
-->

# Scala 中的 "new" 關鍵字：用於物件創建的基礎

## 簡介
在 Scala 程式語言中，`new` 關鍵字是用來創建物件的主要方法。它允許開發者基於類別的定義來實例化物件，在物件導向程式設計中扮演著關鍵的角色。

## 文檔
### 目的
`new` 關鍵字用於創建類的實例。當你想要使用一個類所定義的屬性和方法時，你需要先通過 `new` 來實例化該類。

### 使用方法
在 Scala 中，使用 `new` 關鍵字的基本語法如下：

```scala
val instanceName = new ClassName(arguments)
```

這裡的 `ClassName` 是你想要實例化的類的名稱，`arguments` 是傳遞給類構造函數的參數（如果有的話）。

### 詳細說明
- **類的構造函數**: 當你使用 `new` 來創建一個物件時，會調用類的構造函數。這可以是主構造函數或輔助構造函數。
- **初始化**: 在創建物件時，類的字段會根據定義進行初始化。
- **可選參數**: Scala 支持帶有可選參數的構造函數，這使得物件創建過程更加靈活。

## 範例
以下是使用 `new` 創建物件的基本範例：

### 簡單類的實例化
```scala
class Person(val name: String, val age: Int)

val john = new Person("John", 30)
println(john.name) // 輸出: John
```

### 使用輔助構造函數
```scala
class Animal(val species: String) {
  def this() = this("未知物種")
}

val dog = new Animal("狗")
val unknownAnimal = new Animal() // 使用輔助構造函數
```

## 說明
- **常見陷阱**: 初學者可能會忘記使用 `new` 來創建物件，而直接調用類名會導致錯誤。Scala 的伴隨對象（companion object）可以定義應用方法，但對於一般的物件實例化，仍需使用 `new`。
- **默認構造函數**: 如果一個類沒有明確定義構造函數，Scala 會自動生成一個默認構造函數，無需使用 `new` 時需注意這一點。
- **參數的傳遞**: 確保傳遞給構造函數的參數類型與定義一致，否則會導致編譯錯誤。

## 一句總結
在 Scala 中，`new` 關鍵字是創建類實例的基本方法，對於物件導向程式設計至關重要。