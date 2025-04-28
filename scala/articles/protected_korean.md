<!--
Meta Description: # Scala의 protected 접근 제어자 ## 개요 Scala에서 `protected`는 클래스의 멤버에 대한 접근 제한을 설정하는 접근 제어자입니다. 이 제어자는 멤버가 해당 클래스를 상속하는 서브클래스에서 접근할 수 있도록 허용합니다. ## 문서 `protec...
Meta Keywords: protected, 접근할, sound, 클래스의, 클래스
-->

# Scala의 protected 접근 제어자

## 개요
Scala에서 `protected`는 클래스의 멤버에 대한 접근 제한을 설정하는 접근 제어자입니다. 이 제어자는 멤버가 해당 클래스를 상속하는 서브클래스에서 접근할 수 있도록 허용합니다.

## 문서
`protected` 접근 제어자는 클래스의 필드나 메서드가 외부에서 직접 접근되지 않도록 보호합니다. 그러나 이 멤버는 해당 클래스를 상속한 서브클래스에서는 접근할 수 있습니다. 이는 객체 지향 프로그래밍에서 캡슐화를 유지하면서도 상속을 통해 코드의 재사용성을 높이는 데 유용합니다.

### 사용법
`protected` 키워드는 클래스의 멤버를 정의할 때 사용합니다. 예를 들어, 다음과 같이 클래스 내에서 필드나 메서드를 정의할 수 있습니다:

```scala
class Parent {
  protected def show(): Unit = {
    println("Protected Method in Parent")
  }
}

class Child extends Parent {
  def display(): Unit = {
    show() // 서브클래스에서 접근 가능
  }
}
```

위의 예시에서 `Child` 클래스는 `Parent` 클래스의 `protected` 메서드 `show()`에 접근할 수 있습니다.

### 세부 사항
- `protected` 접근 제어자는 클래스 내부와 서브클래스에서만 접근할 수 있습니다. 외부에서는 접근할 수 없습니다.
- `protected`는 클래스 멤버에만 적용되며, 객체 인스턴스에는 적용되지 않습니다.
- `protected`는 Scala의 클래스 계층 구조에서 상속을 통해 재사용성을 높이는 데 중요한 역할을 합니다.

## 예제
다음은 `protected` 접근 제어자를 사용하는 간단한 예제입니다:

```scala
class Animal {
  protected def sound(): Unit = {
    println("Animal sound")
  }
}

class Dog extends Animal {
  def bark(): Unit = {
    sound() // "Animal sound" 출력
  }
}

object Main extends App {
  val dog = new Dog
  dog.bark() // 메서드 호출이 가능
  // dog.sound() // 컴파일 오류: 'sound'는 protected이므로 외부에서 접근 불가
}
```

## 설명
- `protected` 멤버는 서브클래스에서만 접근할 수 있지만, 외부에서 직접 접근할 수 없으므로 주의해야 합니다.
- `protected`는 클래스 내에서만 정의될 수 있으며, 객체의 인스턴스나 외부에서 접근할 수 없습니다.
- 서브클래스의 인스턴스에서만 접근 가능하므로, 설계할 때 어떤 멤버를 `protected`로 설정할지 신중히 결정해야 합니다.

## 한 줄 요약
Scala의 `protected` 접근 제어자는 클래스의 멤버를 서브클래스에서만 접근 가능하도록 제한하는 기능입니다.