<!--
Meta Description: # Scala 中的 "protected" 關鍵字：保護訪問修飾符 ## 概述 在 Scala 中，`protected` 是一種訪問修飾符，用於控制類成員的可見性。它允許子類別訪問父類別中的成員，同時防止外部類別訪問這些成員。這對於封裝和繼承的使用至關重要。 ## 文檔 ### 目的 `prot...
Meta Keywords: protected, scala, child, secret, val
-->

# Scala 中的 "protected" 關鍵字：保護訪問修飾符

## 概述
在 Scala 中，`protected` 是一種訪問修飾符，用於控制類成員的可見性。它允許子類別訪問父類別中的成員，同時防止外部類別訪問這些成員。這對於封裝和繼承的使用至關重要。

## 文檔
### 目的
`protected` 修飾符的主要目的是提供一種方法，讓子類可以訪問父類中的成員，而不允許其他類別訪問這些成員。這有助於在繼承樹中創建強大的封裝。

### 使用
在 Scala 中，當你聲明一個變量或方法時，可以使用 `protected` 修飾符。其語法如下：

```scala
protected val memberName: Type
protected def methodName(parameters): ReturnType
```

這樣聲明的成員只能被同一類或其子類訪問，而無法被其他類別直接訪問。

### 詳細說明
- **可見性**：`protected` 修飾符使得成員在同一包內的子類以及不同包中的子類中可見，但在其他類別中不可見。
- **與 `private` 和 `public` 的區別**：`private` 使得成員對所有其他類別不可見，而 `public` 則使成員對所有類別可見。相比之下，`protected` 提供了一種介於兩者之間的可見性。
- **抽象類和特徵**：在抽象類和特徵中使用 `protected` 成員，可以強化子類的行為，並且強制子類實現某些方法。

## 範例
以下是使用 `protected` 修飾符的基本範例：

```scala
class Parent {
  protected val secret: String = "這是保護的秘密"

  protected def revealSecret(): String = secret
}

class Child extends Parent {
  def showSecret(): String = revealSecret()
}

val child = new Child()
println(child.showSecret()) // 輸出: 這是保護的秘密
// println(child.secret) // 編譯錯誤: 'secret' 不是可見的
```

## 說明
- **常見誤區**：開發者在使用 `protected` 時可能會誤以為它對所有類別可見。實際上，只有子類和同一包中的類別可以訪問 `protected` 成員。
- **繼承中的使用**：當建立一個類層次結構時，合理使用 `protected` 可以增加代碼的可讀性和可維護性，因為它限制了對內部狀態的直接訪問。
- **Scala 版本**：確保使用的 Scala 版本支持 `protected` 修飾符的語法，不同版本間可能存在細微差異。

## 總結
在 Scala 中，`protected` 修飾符是一種重要的可見性控制工具，允許子類訪問父類成員，同時保持封裝性。