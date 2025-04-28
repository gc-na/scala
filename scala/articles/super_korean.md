<!--
Meta Description: # Scala에서의 "super" 키워드: 개념 및 사용법 ## 개요 Scala에서 "super" 키워드는 상속 관계에서 부모 클래스의 메서드나 속성에 접근할 때 사용되는 키워드입니다. 이를 통해 상위 클래스의 기능을 재사용하고, 메서드 오버라이딩 시 부모 클래스의 구...
Meta Keywords: super, 클래스의, sound, 메서드를, 메서드
-->

# Scala에서의 "super" 키워드: 개념 및 사용법

## 개요
Scala에서 "super" 키워드는 상속 관계에서 부모 클래스의 메서드나 속성에 접근할 때 사용되는 키워드입니다. 이를 통해 상위 클래스의 기능을 재사용하고, 메서드 오버라이딩 시 부모 클래스의 구현을 호출할 수 있습니다.

## 문서화
"super" 키워드는 Scala의 객체지향 프로그래밍 모델에서 매우 중요한 역할을 합니다. 클래스가 다른 클래스를 상속받을 때, 자식 클래스는 부모 클래스의 메서드를 재정의(overriding)할 수 있습니다. 이때 "super" 키워드를 사용하면 부모 클래스의 메서드를 명시적으로 호출할 수 있습니다. 

### 사용 목적
- 부모 클래스의 메서드 호출: 자식 클래스에서 오버라이드한 메서드 내에서 부모 클래스의 메서드를 호출할 수 있습니다.
- 다중 상속 지원: Scala는 혼합형 상속을 지원하므로, 여러 부모 클래스 중에서 특정 부모의 메서드를 선택하여 사용할 수 있습니다.

### 사용 방법
"super"는 다음과 같이 사용됩니다:
```scala
class Parent {
  def greet(): Unit = {
    println("Hello from Parent!")
  }
}

class Child extends Parent {
  override def greet(): Unit = {
    super.greet() // 부모 클래스의 greet 메서드 호출
    println("Hello from Child!")
  }
}
```

## 예제
다음은 "super" 키워드를 사용하는 간단한 예제입니다.

```scala
class Animal {
  def sound(): Unit = {
    println("Animal sound")
  }
}

class Dog extends Animal {
  override def sound(): Unit = {
    super.sound() // 부모 클래스의 sound 메서드 호출
    println("Woof")
  }
}

object Main extends App {
  val dog = new Dog()
  dog.sound()
}
```
출력:
```
Animal sound
Woof
```

## 설명
"super" 키워드를 사용할 때 유의해야 할 점은 다음과 같습니다:

- **다중 상속**: Scala에서는 트레이트(trait)와 클래스를 혼합하여 다중 상속을 지원합니다. 이 경우, "super"는 가장 가까운 부모의 메서드를 호출합니다.
- **상속 구조**: "super" 키워드를 사용할 때, 호출되는 메서드는 항상 부모 클래스 또는 트레이트에서 정의된 것이어야 합니다. 자식 클래스에서 정의된 메서드는 호출되지 않습니다.
- **명시적 호출**: "super"를 사용하여 부모 클래스의 메서드를 호출할 때, 부모 클래스의 메서드가 오버라이드될 수 있으므로, 항상 의도한 메서드가 호출되는지 확인해야 합니다.

## 한 줄 요약
Scala에서 "super" 키워드는 상위 클래스의 메서드나 속성에 접근하기 위해 사용하는 키워드입니다.