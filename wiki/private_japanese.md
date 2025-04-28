<!--
Meta Description: # Scalaの「private」修飾子: アクセス制御の基本 ## 概要 Scalaにおける「private」修飾子は、クラスまたはオブジェクト内のメンバー（フィールドやメソッド）のアクセスを制限するために使用されます。この修飾子を使用することで、データの隠蔽を実現し、オブジェクト指向プログラミン...
Meta Keywords: private, counter, count, 修飾子は, def
-->

# Scalaの「private」修飾子: アクセス制御の基本

## 概要
Scalaにおける「private」修飾子は、クラスまたはオブジェクト内のメンバー（フィールドやメソッド）のアクセスを制限するために使用されます。この修飾子を使用することで、データの隠蔽を実現し、オブジェクト指向プログラミングの原則に従った設計が可能になります。

## ドキュメンテーション
「private」修飾子は、クラスの外部からはアクセスできないメンバーを定義するために使用されます。これにより、クラスの内部実装を隠蔽し、外部からの不正な操作を防ぐことができます。

### 目的
- データの隠蔽を実現する。
- クラスの外部からの不正なアクセスを防ぐ。

### 使用法
「private」修飾子は、クラス内のメンバーに対して以下のように使用します。

```scala
class MyClass {
  private var secret: Int = 0

  private def secretMethod(): String = {
    "This is a private method."
  }
}
```

この例では、`secret`変数と`secretMethod`メソッドはクラス`MyClass`の外部からはアクセスできません。

### 詳細
- `private`は同じクラス内からのみアクセス可能です。
- `private`の代わりに`protected`を使うことで、サブクラスからのアクセスを許可することもできます。

## 例
以下は「private」修飾子の基本的な使用例です。

```scala
class Counter {
  private var count = 0

  def increment(): Unit = {
    count += 1
  }

  def getCount: Int = count
}

val counter = new Counter()
counter.increment()
println(counter.getCount) // 出力: 1
// println(counter.count) // エラー: countはprivateです
```

この例では、`count`は`private`として定義されているため、`Counter`クラスの外部からは直接アクセスできません。

## 説明
「private」修飾子を使用する際の一般的な落とし穴や注意点は以下の通りです。

- **アクセスエラー**: `private`メンバーにアクセスしようとすると、コンパイルエラーが発生します。これは意図した動作ですが、思わぬエラーとなることがあります。
- **テストの難しさ**: プライベートメンバーに依存するテストコードを書くことが難しくなります。この場合、テスト対象のクラスを設計する際に、どのようにプライベートメンバーを利用するかを考慮する必要があります。

## 一行要約
Scalaの「private」修飾子は、クラスの内部メンバーへのアクセスを制限し、データ隠蔽を実現します。