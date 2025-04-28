<!--
Meta Description: # Scala中的「sealed」關鍵字：提升型別安全性的利器 ## 摘要 在Scala中，「sealed」關鍵字用於定義密封類別和密封特徵，限制了其子類別的數量，從而提高了型別安全性和可預測性。 ## 文檔 ### 目的 「sealed」關鍵字的主要目的是限制一個類別的所有子類別只能在同一檔案中定...
Meta Keywords: sealed, case, animal, name, dog
-->

# Scala中的「sealed」關鍵字：提升型別安全性的利器

## 摘要
在Scala中，「sealed」關鍵字用於定義密封類別和密封特徵，限制了其子類別的數量，從而提高了型別安全性和可預測性。

## 文檔
### 目的
「sealed」關鍵字的主要目的是限制一個類別的所有子類別只能在同一檔案中定義。這樣的設計使得開發者能夠清楚地知道所有可能的子類型，並在模式匹配中提供更高的安全性。

### 使用方式
要使用「sealed」，只需在類別或特徵的定義前添加該關鍵字。密封類別可以擁有多個子類別，但這些子類別必須在同一檔案中定義。

```scala
sealed trait Shape
case class Circle(radius: Double) extends Shape
case class Rectangle(width: Double, height: Double) extends Shape
```

在上述範例中，`Shape`是一個密封特徵，`Circle`和`Rectangle`是其子類別。

### 詳細說明
- **型別安全性**：使用「sealed」類別時，編譯器可以檢查所有可能的子類型，這在使用模式匹配時尤為重要。若未考慮所有子類型，編譯器會發出警告。
- **可讀性**：透過將所有子類型集中在同一檔案中，程式碼的可讀性和維護性得以提高。
- **模式匹配**：當進行模式匹配時，Scala會檢查所有的子類型，如果不處理所有的情況，將會導致編譯錯誤。

## 範例
以下是一個使用「sealed」關鍵字的簡單範例：

```scala
sealed trait Animal
case class Dog(name: String) extends Animal
case class Cat(name: String) extends Animal

def printAnimal(animal: Animal): Unit = animal match {
  case Dog(name) => println(s"狗的名字是: $name")
  case Cat(name) => println(s"貓的名字是: $name")
}

// 使用範例
val dog = Dog("小黑")
val cat = Cat("小白")
printAnimal(dog) // 輸出: 狗的名字是: 小黑
printAnimal(cat) // 輸出: 貓的名字是: 小白
```

## 解釋
- **常見錯誤**：在定義密封類別時，確保所有子類別都位於同一檔案中，否則將導致編譯錯誤。
- **缺失子類別**：在模式匹配中未處理所有子類別會導致編譯器警告，這樣會降低型別安全性。
- **使用情境**：適合用在需要明確定義所有可能型別的情況，例如狀態機或命令模式。

## 一句總結
Scala中的「sealed」關鍵字可用於提升型別安全性，確保所有子類別都在同一檔案中定義並可被明確處理。