<!--
Meta Description: # Scala의 "new" 키워드: 객체 생성의 기본 ## 개요 Scala에서 "new" 키워드는 클래스의 인스턴스를 생성하는 데 사용되는 기본적인 키워드입니다. 이 키워드를 통해 프로그래머는 객체를 초기화하고 메모리에 할당할 수 있습니다. ## 문서화 "new" 키워...
Meta Keywords: new, val, 키워드는, 클래스의, 인스턴스를
-->

# Scala의 "new" 키워드: 객체 생성의 기본

## 개요
Scala에서 "new" 키워드는 클래스의 인스턴스를 생성하는 데 사용되는 기본적인 키워드입니다. 이 키워드를 통해 프로그래머는 객체를 초기화하고 메모리에 할당할 수 있습니다.

## 문서화
"new" 키워드는 Scala에서 객체 지향 프로그래밍의 중추적인 요소로, 클래스의 인스턴스를 생성하는 데 필수적입니다. 사용법은 다음과 같습니다.

### 목적
- 객체를 생성하고 초기화하기 위해 사용됩니다.
  
### 사용법
- 기본 사용법: `val instance = new ClassName(arguments)`
- 생성자는 클래스에 정의된 매개변수에 따라 호출됩니다.

### 세부사항
- "new" 키워드는 변수를 선언할 때 사용되며, 생성자 호출 시 클래스 이름 뒤에 위치합니다.
- Scala는 보통 생성자 매개변수를 간단하게 사용할 수 있도록 추가적인 문법적인 편의성을 제공합니다. 예를 들어, `class ClassName(val param: Int)`와 같이 정의된 클래스는 `new ClassName(10)`으로 간단히 인스턴스를 생성할 수 있습니다.

## 예제
```scala
// 클래스 정의
class Person(val name: String, val age: Int)

// 객체 생성
val person1 = new Person("Alice", 30)
val person2 = new Person("Bob", 25)

// 출력
println(s"${person1.name} is ${person1.age} years old.") // Alice is 30 years old.
println(s"${person2.name} is ${person2.age} years old.") // Bob is 25 years old.
```

## 설명
- **공통적인 함정**: "new" 키워드를 사용하는 것이 필수적이지만, Scala에서는 `case class`와 같은 특정 클래스에서 `new` 없이 객체를 생성할 수 있습니다. 예를 들어, `val person3 = Person("Charlie", 40)`과 같이 사용할 수 있습니다.
- **부가적인 주의사항**: 생성자가 여러 개일 경우, 어떤 생성자를 호출할지 명확히 이해하고 있어야 합니다. 또한, 클래스가 상속받은 경우, 부모 클래스의 생성자를 호출하는 것을 잊지 않아야 합니다.

## 한 줄 요약
Scala에서 "new" 키워드는 클래스의 인스턴스를 생성하고 초기화하는 데 사용되는 기본 키워드입니다.