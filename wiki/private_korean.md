<!--
Meta Description: # Scala에서의 "private": 접근 제어자 이해하기 ## 개요 Scala에서 "private"는 클래스나 객체 내에서 정의된 멤버에 대한 접근 제어를 설정하는 키워드입니다. 이를 통해 데이터 은닉을 구현하고, 객체 지향 프로그래밍의 원칙을 따르며, 외부에서의 ...
Meta Keywords: private, 클래스의, 접근할, balance, account
-->

# Scala에서의 "private": 접근 제어자 이해하기

## 개요
Scala에서 "private"는 클래스나 객체 내에서 정의된 멤버에 대한 접근 제어를 설정하는 키워드입니다. 이를 통해 데이터 은닉을 구현하고, 객체 지향 프로그래밍의 원칙을 따르며, 외부에서의 불필요한 접근을 방지할 수 있습니다.

## 문서화
### 목적
"private" 키워드는 클래스의 멤버(변수 및 메서드)가 그 클래스의 내부에서만 접근 가능하도록 제한합니다. 이는 객체의 상태를 보호하고, 클래스의 인터페이스를 명확하게 유지하는 데 도움을 줍니다.

### 사용법
"private" 키워드는 클래스 내부에서 멤버를 정의할 때 사용됩니다. 기본적으로 "private"로 정의된 멤버는 해당 클래스의 인스턴스에서만 접근할 수 있으며, 외부 클래스나 객체에서는 접근할 수 없습니다.

#### 문법
```scala
class MyClass {
  private val myPrivateValue = 10
  
  private def myPrivateMethod(): Unit = {
    println("This is a private method.")
  }
}
```

### 세부사항
- "private"는 클래스 내부의 모든 코드에서 접근할 수 있는 멤버를 정의하며, 상속받은 클래스에서도 접근할 수 없습니다.
- Scala에서는 "private" 키워드가 "private[this]"와 구분됩니다. "private[this]"는 해당 인스턴스에서만 접근할 수 있도록 제한합니다.
- "private" 멤버는 패키지 내부에서도 접근이 불가능하므로, 동일 패키지 내의 다른 클래스에서 접근하고자 할 경우 "protected" 키워드를 고려해야 합니다.

## 예제
```scala
class BankAccount {
  private var balance: Double = 0.0
  
  def deposit(amount: Double): Unit = {
    balance += amount
  }
  
  def getBalance: Double = balance
}

object Main extends App {
  val account = new BankAccount()
  account.deposit(100.0)
  println(account.getBalance) // 100.0
  // account.balance // 오류: 'balance'에 접근할 수 없습니다.
}
```

## 설명
"private" 멤버에 접근하려고 할 때 발생하는 오류는 종종 혼란을 초래합니다. 이를 피하기 위해, 클래스의 공개 메서드를 통해 멤버에 접근하는 것이 좋습니다. 또한, "private" 키워드를 사용하는 것은 클래스의 설계를 더욱 견고하게 만들며, 외부의 잘못된 접근을 방지하는 데 기여합니다.

## 한 줄 요약
Scala에서 "private"는 클래스 내부에서만 접근 가능한 멤버를 정의하여 데이터 은닉을 구현하는 접근 제어자입니다.