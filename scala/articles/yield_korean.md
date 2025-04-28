<!--
Meta Description: # Scala의 "yield"에 대한 완벽 가이드 ## 요약 Scala에서 `yield`는 컬렉션을 변환하고 새로운 컬렉션을 생성하는 데 사용되는 강력한 기능입니다. `for` 표현식과 함께 사용되어 원본 컬렉션의 요소를 기반으로 새로운 값을 생성할 수 있습니다. ##...
Meta Keywords: yield, 새로운, 컬렉션을, val, 합니다
-->

# Scala의 "yield"에 대한 완벽 가이드

## 요약
Scala에서 `yield`는 컬렉션을 변환하고 새로운 컬렉션을 생성하는 데 사용되는 강력한 기능입니다. `for` 표현식과 함께 사용되어 원본 컬렉션의 요소를 기반으로 새로운 값을 생성할 수 있습니다.

## 문서화
`yield`는 Scala의 `for` 루프 내에서 사용되며, 루프의 각 반복에서 생성된 값을 수집하여 새로운 컬렉션을 반환합니다. 이 기능은 주로 컬렉션의 변환 및 매핑에 유용합니다. 

### 목적
`yield`는 반복문에서 각 요소에 대해 특정 연산을 수행하고, 그 결과를 새로운 컬렉션으로 반환하는 것을 가능하게 합니다. 이는 코드의 가독성을 높이고, 함수형 프로그래밍의 패러다임을 따르는 데 기여합니다.

### 사용법
`yield`는 `for` 표현식 안에서 사용됩니다. 기본적인 구조는 다음과 같습니다:

```scala
val newCollection = for (element <- originalCollection) yield {
  // 변환 로직
}
```

## 예제
다음은 `yield`의 기본 사용 예제입니다.

### 예제 1: 숫자 제곱하기
```scala
val numbers = List(1, 2, 3, 4, 5)
val squares = for (n <- numbers) yield n * n
println(squares) // List(1, 4, 9, 16, 25)
```

### 예제 2: 문자열 길이 구하기
```scala
val words = List("Scala", "is", "great")
val lengths = for (word <- words) yield word.length
println(lengths) // List(5, 2, 5)
```

## 설명
`yield`를 사용할 때 주의할 점은 다음과 같습니다:

1. **타입 일치**: `yield`에서 반환되는 값의 타입은 동일해야 합니다. 예를 들어, 숫자 리스트에서 문자열로 변환하면 오류가 발생할 수 있습니다.
  
2. **Nested for 루프**: 중첩된 `for` 표현식에서도 `yield`를 사용할 수 있지만, 각 레벨의 변환 로직을 명확히 해야 합니다.

3. **성능 고려**: `yield`는 새로운 컬렉션을 반환하므로, 큰 데이터셋을 처리할 때는 메모리 사용량에 주의해야 합니다.

## 한 줄 요약
Scala에서 `yield`는 `for` 루프를 사용하여 원본 컬렉션의 각 요소를 변환하여 새로운 컬렉션을 생성하는 기능입니다.