<!--
Meta Description: # Scala의 "case" 키워드: 패턴 매칭과 데이터 클래스 ## 개요 Scala의 "case" 키워드는 패턴 매칭 및 데이터 클래스 정의에 사용되는 강력한 기능입니다. 이 키워드는 프로그램에서 복잡한 데이터 구조를 쉽게 다루고, 조건부 로직을 간결하게 작성할 수 ...
Meta Keywords: case, 데이터, 클래스, println, person
-->

# Scala의 "case" 키워드: 패턴 매칭과 데이터 클래스

## 개요
Scala의 "case" 키워드는 패턴 매칭 및 데이터 클래스 정의에 사용되는 강력한 기능입니다. 이 키워드는 프로그램에서 복잡한 데이터 구조를 쉽게 다루고, 조건부 로직을 간결하게 작성할 수 있도록 돕습니다.

## 문서화
### 목적
"case" 키워드는 주로 두 가지 용도로 사용됩니다:
1. **패턴 매칭**: 다양한 데이터 유형을 검사하고, 해당 유형에 따라 조건부 로직을 실행할 수 있도록 합니다.
2. **데이터 클래스**: 불변 데이터를 정의하는데 사용되며, 데이터 클래스의 자동 생성된 메서드(예: `equals`, `hashCode`, `toString`)를 제공합니다.

### 사용법
- **패턴 매칭**: `match` 키워드와 함께 사용하여 여러 조건을 정의할 수 있습니다.
- **데이터 클래스 정의**: `case class` 키워드를 사용하여 간단하게 클래스 정의를 할 수 있습니다.

```scala
case class Person(name: String, age: Int)

val person = Person("Alice", 30)

person match {
  case Person("Alice", age) => println(s"Alice is $age years old")
  case Person(name, age) => println(s"$name is $age years old")
}
```

## 예제
### 데이터 클래스 예제
```scala
case class Point(x: Int, y: Int)

val p1 = Point(1, 2)
val p2 = Point(3, 4)

println(p1) // 출력: Point(1, 2)
```

### 패턴 매칭 예제
```scala
def describe(x: Any): String = x match {
  case 5 => "Five"
  case "hello" => "A greeting"
  case _: Int => "An integer"
  case _ => "Something else"
}

println(describe(5))         // 출력: Five
println(describe("hello"))   // 출력: A greeting
println(describe(10))        // 출력: An integer
println(describe(3.14))      // 출력: Something else
```

## 설명
- **공통 실수**: `case` 키워드를 사용할 때, 패턴 매칭에서 모든 가능성을 처리하지 않으면 `MatchError`가 발생할 수 있습니다. 모든 경우를 처리하는 것이 중요합니다.
- **불변성**: `case class`로 정의된 클래스는 기본적으로 불변(immutable)입니다. 즉, 한 번 생성된 객체는 수정할 수 없습니다.
- **패턴 매칭의 순서**: 패턴 매칭은 위에서 아래로 평가되므로, 더 구체적인 패턴을 위에 배치해야 합니다.

## 한 문장 요약
Scala의 "case" 키워드는 패턴 매칭과 데이터 클래스 정의에 사용되어 코드 작성의 효율성과 가독성을 높이는 중요한 기능입니다.