<!--
Meta Description: # Scala에서의 Sealed 클래스와 특성 이해하기 ## 개요 Scala에서 `sealed`는 클래스나 trait의 상속 범위를 제한하는 특성입니다. `sealed`로 선언된 클래스는 동일한 파일 내에서만 하위 클래스를 가질 수 있어, 서브타입의 개수를 통제하고 패...
Meta Keywords: sealed, animal, dog, cat, 클래스를
-->

# Scala에서의 Sealed 클래스와 특성 이해하기

## 개요
Scala에서 `sealed`는 클래스나 trait의 상속 범위를 제한하는 특성입니다. `sealed`로 선언된 클래스는 동일한 파일 내에서만 하위 클래스를 가질 수 있어, 서브타입의 개수를 통제하고 패턴 매칭 시 안전성을 높이는 데 유용합니다.

## 문서화
`sealed` 키워드는 Scala에서 클래스 또는 trait를 정의할 때 사용됩니다. 이를 통해 해당 클래스 또는 trait의 하위 클래스를 동일한 파일 내에서만 정의할 수 있습니다. 이 기능은 특히 패턴 매칭에서 유용하며, 컴파일러는 모든 가능한 서브타입을 인식할 수 있어 안전한 코드 작성을 도와줍니다.

### 목적
- **제한된 상속**: `sealed` 클래스를 사용하면, 해당 클래스의 하위 클래스는 오직 정의된 파일 내에서만 생성됩니다.
- **안전한 패턴 매칭**: 모든 서브타입이 컴파일 타임에 명확히 정의되어 있어, 패턴 매칭에서 모든 경우를 처리할 수 있습니다.

### 사용법
`sealed` 키워드는 클래스나 trait 정의 앞에 위치합니다. 예를 들어:

```scala
sealed trait Shape
case class Circle(radius: Double) extends Shape
case class Rectangle(width: Double, height: Double) extends Shape
```

위의 예시에서 `Shape`는 sealed trait로, `Circle`과 `Rectangle`은 같은 파일 내에 정의된 하위 클래스입니다.

## 예제
아래는 `sealed` 클래스를 사용하는 기본적인 예제입니다.

```scala
sealed trait Animal {
  def sound: String
}

case class Dog() extends Animal {
  def sound: String = "Woof"
}

case class Cat() extends Animal {
  def sound: String = "Meow"
}

def animalSound(animal: Animal): String = {
  animal match {
    case Dog() => "Dog says: " + animal.sound
    case Cat() => "Cat says: " + animal.sound
  }
}

val dog = Dog()
val cat = Cat()
println(animalSound(dog)) // Dog says: Woof
println(animalSound(cat)) // Cat says: Meow
```

위의 코드는 `Animal`이라는 sealed trait와 이를 상속받는 `Dog`와 `Cat` 클래스를 정의하고, 패턴 매칭을 통해 각각의 소리를 출력하는 예시입니다.

## 설명
`sealed`를 사용할 때 주의해야 할 점은 다음과 같습니다:
- **파일 내에서만 하위 클래스 정의 가능**: 하위 클래스는 반드시 `sealed` 클래스가 정의된 동일 파일 내에 있어야 합니다.
- **패턴 매칭 안전성**: 모든 서브타입이 알려져 있기 때문에 `match` 문에서 모든 경우를 처리하지 않으면 컴파일 경고가 발생합니다.
- **상속 구조의 명확성**: `sealed` 클래스를 사용하면 상속 구조가 명확해져, 코드 유지보수에 도움이 됩니다.

## 한 줄 요약
Scala에서 `sealed`는 클래스나 trait의 하위 클래스를 제한하여 안전한 패턴 매칭과 상속 구조를 제공합니다.