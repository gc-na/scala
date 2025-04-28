<!--
Meta Description: # Scala 的 Override 關鍵字：用於方法重寫的指南 ## 概述 在 Scala 中，`override` 關鍵字用於標識子類別中重寫的父類別方法或屬性。這一特性允許開發者自定義繼承的行為，使得物件導向編程更為靈活。 ## 文檔 `override` 關鍵字的主要目的是在子類別中重寫父類...
Meta Keywords: override, sound, scala, animal, dog
-->

# Scala 的 Override 關鍵字：用於方法重寫的指南

## 概述
在 Scala 中，`override` 關鍵字用於標識子類別中重寫的父類別方法或屬性。這一特性允許開發者自定義繼承的行為，使得物件導向編程更為靈活。

## 文檔
`override` 關鍵字的主要目的是在子類別中重寫父類別的方法或屬性。當你在子類別中定義一個與父類別同名的方法時，必須使用 `override` 來明確表示這是一個重寫的方法。這樣可以避免潛在的錯誤，並提高代碼的可讀性。

### 用法
- 在定義子類別時，當你想要重寫父類別的方法或屬性時，必須在方法前加上 `override` 關鍵字。
- `override` 僅用於方法和屬性，無法用於類別或對象本身。

### 詳細說明
- 當子類別重寫父類別的方法時，子類別的方法可以有不同的實現，這樣可以提供更具體的行為。
- 如果在子類別中定義了一個與父類別同名但未使用 `override` 的方法，編譯器將會報錯，提示該方法不是有效的重寫。

## 範例
以下是使用 `override` 的簡單範例：

```scala
class Animal {
  def sound(): String = {
    "Some sound"
  }
}

class Dog extends Animal {
  override def sound(): String = {
    "Bark"
  }
}

val myDog = new Dog()
println(myDog.sound()) // 輸出: Bark
```

在上述範例中，`Dog` 類別重寫了 `Animal` 類別中的 `sound` 方法，並提供了具體的實現。

## 解釋
- **常見陷阱**：如果子類別沒有使用 `override`，而又試圖定義與父類別同名的方法，則會導致編譯錯誤。因此，始終建議在重寫方法時使用 `override` 來提高代碼的可讀性和可維護性。
- **注意事項**：當重寫方法時，子類別的返回類型必須與父類別的方法返回類型相同，或者是其子類型（協變返回類型）。

## 一句總結
在 Scala 中，`override` 關鍵字用於明確標示子類別中重寫父類別的方法或屬性，以增強代碼的可讀性和安全性。