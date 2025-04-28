<!--
Meta Description: # Scalaにおけるsealedキーワードの完全ガイド ## 概要 Scalaの`sealed`キーワードは、クラスやトレイトが特定のスコープ内でのみサブクラス化可能であることを保証します。これにより、コードの保守性と安全性が向上します。 ## ドキュメンテーション `sealed`は、Scala...
Meta Keywords: sealed, shape, case, class, extends
-->

# Scalaにおけるsealedキーワードの完全ガイド

## 概要
Scalaの`sealed`キーワードは、クラスやトレイトが特定のスコープ内でのみサブクラス化可能であることを保証します。これにより、コードの保守性と安全性が向上します。

## ドキュメンテーション
`sealed`は、Scalaでクラスやトレイトの階層を制限するために使用されます。このキーワードを使用することで、サブクラスを同じファイル内に限定し、全ての可能なサブクラスを明示的に定義することが求められます。これにより、パターンマッチング時に全てのケースを把握できるため、バグの発生リスクが減少します。

### 使用法
`sealed`をクラスまたはトレイトの前に記述することで、その型がsealedであることを示します。以下のように使用します。

```scala
sealed trait Animal
case class Dog(name: String) extends Animal
case class Cat(name: String) extends Animal
```

## 例
基本的な使用例を以下に示します。

```scala
sealed trait Shape
case class Circle(radius: Double) extends Shape
case class Rectangle(width: Double, height: Double) extends Shape

def area(shape: Shape): Double = shape match {
  case Circle(radius) => Math.PI * radius * radius
  case Rectangle(width, height) => width * height
}
```

この例では、`Shape`トレイトがsealedであり、`Circle`と`Rectangle`がそのサブクラスです。`area`関数では、パターンマッチングを使用して形状の面積を計算しています。

## 説明
`sealed`キーワードを使用する際の一般的な落とし穴や注意点は以下の通りです。

1. **ファイル制約**: `sealed`クラスやトレイトは、その定義とサブクラスが同じファイル内に存在しなければなりません。他のファイルでサブクラスを定義することはできません。
   
2. **パターンマッチング**: `sealed`を使用することで、コンパイラは全てのサブクラスを把握できるため、パターンマッチング時に警告を出さずにすべてのケースを網羅しているか確認できます。

3. **拡張性**: `sealed`クラスは、他のクラスに比べて拡張が制限されるため、将来的に新しいサブクラスを追加する際には、元のファイルに追加する必要があります。

## 一文の要約
Scalaの`sealed`キーワードは、クラスやトレイトのサブクラスを同じファイル内に限定し、コードの安全性と保守性を向上させるために使用されます。