<!--
Meta Description: # Scalaにおける「match」: パターンマッチングの詳細ガイド ## 概要 Scalaの「match」は、与えられた値に基づいて異なる処理を実行するための強力な機能です。パターンマッチングを使用することで、複雑な制御フローを簡潔に表現できます。 ## ドキュメント ### 目的 「match...
Meta Keywords: case, match, println, shape, circle
-->

# Scalaにおける「match」: パターンマッチングの詳細ガイド

## 概要
Scalaの「match」は、与えられた値に基づいて異なる処理を実行するための強力な機能です。パターンマッチングを使用することで、複雑な制御フローを簡潔に表現できます。

## ドキュメント
### 目的
「match」は、値を特定のパターンに照らし合わせて評価し、一致するパターンに対して特定のコードブロックを実行するための構文です。これにより、条件分岐をより直感的に記述できます。

### 使用法
基本的な構文は以下の通りです。

```scala
value match {
  case pattern1 => // 処理1
  case pattern2 => // 処理2
  case _ => // デフォルト処理
}
```

- `value`は評価する対象です。
- 各`case`は特定のパターンを定義し、それに一致した場合に実行される処理を示します。
- 最後の`case _`はデフォルトの処理を定義し、どのパターンにも一致しない場合に実行されます。

## 例
### 基本的な使用例
以下は、整数の値に基づいて異なるメッセージを表示する例です。

```scala
val number = 2

number match {
  case 1 => println("一です")
  case 2 => println("二です")
  case 3 => println("三です")
  case _ => println("その他の数です")
}
```

この例では、`number`が2であるため、「二です」と表示されます。

### クラスとパターンマッチング
クラスを利用した例も示します。

```scala
sealed trait Shape
case class Circle(radius: Double) extends Shape
case class Rectangle(width: Double, height: Double) extends Shape

def area(shape: Shape): Double = {
  shape match {
    case Circle(radius) => Math.PI * radius * radius
    case Rectangle(width, height) => width * height
  }
}

val circle = Circle(5)
val rectangle = Rectangle(4, 6)

println(area(circle))     // 78.53981633974483
println(area(rectangle))  // 24.0
```

## 説明
### よくある落とし穴
- **パターンの順序**: `case`の順序が重要で、より具体的なパターンを先に書く必要があります。一般的なパターン（例: `_`）を先に書くと、他の具体的なパターンが無視されてしまいます。
- **不変性**: `case class`を使用する場合、フィールドは不変であるため、ミスを避けるために適切な設計が必要です。

### 注意点
- `match`式は必ず値を返します。返り値が必要ない場合でも、全ての`case`に対して処理を記述する必要があります。
- 型安全性があるため、特定の型の値に対してのみ処理を行うことができます。

## 一文要約
Scalaの「match」は、値に基づいて異なる処理を簡潔に実行するための強力なパターンマッチング機能です。