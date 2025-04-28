<!--
Meta Description: # Scala에서 "true": 불리언 값의 기본 ## 개요 Scala에서 "true"는 불리언 타입의 기본 값 중 하나로, 조건문의 평가 및 논리 연산에 사용됩니다. 이 값은 프로그램의 흐름을 제어하는 중요한 역할을 합니다. ## 문서화 Scala에서는 불리언 타입이...
Meta Keywords: true, println, 불리언, boolean, false
-->

# Scala에서 "true": 불리언 값의 기본

## 개요
Scala에서 "true"는 불리언 타입의 기본 값 중 하나로, 조건문의 평가 및 논리 연산에 사용됩니다. 이 값은 프로그램의 흐름을 제어하는 중요한 역할을 합니다.

## 문서화
Scala에서는 불리언 타입이 `Boolean`으로 정의되며, 이 타입은 두 가지 값인 `true`와 `false`를 가집니다. `true`는 논리적으로 참(True)을 나타내며, 다양한 제어 구조와 조건문에서 필수적으로 사용됩니다.

### 사용 목적
- 조건문 및 반복문에서의 흐름 제어
- 논리 연산에서의 사용
- 함수의 반환 값으로 사용

### 사용법
`true`는 직접적으로 사용할 수 있으며, 다음과 같이 여러 상황에서 활용됩니다:
```scala
if (true) {
  println("이 문장은 항상 실행됩니다.")
}
```

## 예시
1. **조건문에서의 사용**
   ```scala
   val condition: Boolean = true
   if (condition) {
     println("조건이 참입니다.")
   } else {
     println("조건이 거짓입니다.")
   }
   ```

2. **논리 연산에서의 사용**
   ```scala
   val a = true
   val b = false
   val result = a && b // 결과는 false
   println(result)
   ```

3. **함수의 반환 값으로 사용**
   ```scala
   def isPositive(num: Int): Boolean = {
     num > 0
   }

   println(isPositive(5))  // true
   println(isPositive(-3)) // false
   ```

## 설명
Scala에서 `true` 값을 사용할 때 유의해야 할 점은 다음과 같습니다:
- **Boolean 연산**: 불리언 연산은 다른 데이터 타입과 결합할 때 예상치 못한 결과를 초래할 수 있습니다. `true`와 `false`는 항상 명확하게 비교할 수 있어야 합니다.
- **지연 평가**: 조건문에서 `true`를 사용할 경우 항상 조건문이 실행됩니다. 따라서 무한 루프와 같은 상황을 피하기 위해 조건을 명확히 설정해야 합니다.
- **타입 일치**: `true`는 `Boolean` 타입으로만 사용되어야 하며, 다른 타입과의 혼용 사용은 컴파일 오류를 발생시킬 수 있습니다.

## 한 줄 요약
Scala에서 "true"는 불리언 값의 기본으로, 조건문 및 논리 연산에서 필수적으로 사용된다.