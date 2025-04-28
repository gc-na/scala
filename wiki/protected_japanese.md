<!--
Meta Description: # Scalaにおける「protected」アクセス修飾子の完全ガイド ## 概要 Scalaにおける「protected」は、クラスのメンバーに対するアクセス制御を提供するアクセス修飾子です。この修飾子を使用することで、クラス自身とそのサブクラスからのみアクセス可能なメンバーを定義できます。 ##...
Meta Keywords: protected, dog, class, def, unit
-->

# Scalaにおける「protected」アクセス修飾子の完全ガイド

## 概要
Scalaにおける「protected」は、クラスのメンバーに対するアクセス制御を提供するアクセス修飾子です。この修飾子を使用することで、クラス自身とそのサブクラスからのみアクセス可能なメンバーを定義できます。

## ドキュメンテーション
### 目的
「protected」修飾子は、クラスのメンバー（フィールドやメソッド）へのアクセスを制限し、クラスの継承関係において安全に情報を隠蔽するために使用されます。

### 使用法
`protected`を使用するには、クラスのメンバー定義の前に「protected」を記述します。以下はその基本的な構文です。

```scala
class Base {
  protected def protectedMethod(): Unit = {
    println("This is a protected method.")
  }
}

class Derived extends Base {
  def accessProtectedMethod(): Unit = {
    protectedMethod() // OK: DerivedはBaseのprotectedメソッドにアクセスできる
  }
}

val obj = new Derived()
obj.accessProtectedMethod() // "This is a protected method." と表示される
```

### 詳細
- **使用制限**: `protected`メンバーは、そのクラス自体とそのサブクラスからのみアクセスできます。他のクラスやオブジェクトからはアクセスできません。
- **サブクラスでの利用**: サブクラスは親クラスの`protected`メンバーを直接使用することができます。
- **パッケージ内アクセス**: `protected`メンバーは同じパッケージ内のクラスからはアクセスできません。これは、`protected`のアクセスの範囲が継承関係に依存しているためです。

## 例
以下は、`protected`を使用した具体的な例です。

```scala
class Animal {
  protected def makeSound(): Unit = {
    println("Animal sound")
  }
}

class Dog extends Animal {
  def bark(): Unit = {
    makeSound() // OK
    println("Woof!")
  }
}

val dog = new Dog()
dog.bark() // "Animal sound" と "Woof!" が表示される
// dog.makeSound() // エラー: makeSoundはprotectedなのでアクセスできない
```

## 説明
### よくある落とし穴
- **アクセス制限の誤解**: `protected`メンバーはサブクラスからのみアクセス可能であり、インスタンス化したオブジェクトからはアクセスできないことに注意する必要があります。
- **パッケージ内のアクセス**: 同じパッケージ内の異なるクラスからのアクセスは許可されないため、設計時には注意が必要です。

### 注意点
- `protected`修飾子は、クラスの設計において、情報隠蔽のために用いられる重要な手段です。適切に利用することで、クラスの再利用性を高めつつ、セキュリティを強化できます。

## 一文の要約
Scalaの「protected」修飾子は、クラスメンバーへのアクセスをそのクラスとサブクラスに制限するための強力なアクセス制御機能です。