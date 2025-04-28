<!--
Meta Description: # Scala에서의 import: 모듈과 패키지 관리의 기초 ## 개요 Scala에서 `import`는 외부 패키지나 모듈의 클래스, 오브젝트, 메서드를 현재 스코프에서 사용할 수 있도록 가져오는 기능입니다. 이는 코드의 재사용성을 높이고, 타 라이브러리와의 통합을 용...
Meta Keywords: import, scala, 가져오기, 있습니다, 사용할
-->

# Scala에서의 import: 모듈과 패키지 관리의 기초

## 개요
Scala에서 `import`는 외부 패키지나 모듈의 클래스, 오브젝트, 메서드를 현재 스코프에서 사용할 수 있도록 가져오는 기능입니다. 이는 코드의 재사용성을 높이고, 타 라이브러리와의 통합을 용이하게 합니다.

## 문서화
`import`는 Scala 프로그램에서 다른 패키지의 구성 요소를 포함시킬 때 사용되는 키워드입니다. 이를 통해 다음과 같은 목적을 달성할 수 있습니다:

- **Namespace 관리**: 동일한 이름을 가진 클래스나 오브젝트가 여러 곳에 있을 때, 필요한 것만 선택하여 사용할 수 있습니다.
- **코드 가독성 향상**: 필요한 구성 요소를 명시적으로 가져옴으로써 코드의 이해도를 높일 수 있습니다.
- **모듈화**: 대규모 프로젝트에서 코드의 모듈화를 지원합니다.

### 사용법
`import`는 다음과 같이 사용할 수 있습니다:

1. 전체 패키지 가져오기:
   ```scala
   import packageName._
   ```

2. 특정 클래스나 오브젝트만 가져오기:
   ```scala
   import packageName.ClassName
   ```

3. 별칭을 사용하여 가져오기:
   ```scala
   import packageName.{ClassName => AliasName}
   ```

4. 중첩된 패키지에서 가져오기:
   ```scala
   import packageName.subPackage.ClassName
   ```

## 예제
다음은 `import`의 기본 사용 예제입니다.

1. 전체 패키지 가져오기
   ```scala
   import scala.collection._
   val list = List(1, 2, 3)
   ```

2. 특정 클래스 가져오기
   ```scala
   import scala.math.sqrt
   val squareRoot = sqrt(16)
   ```

3. 별칭 사용하기
   ```scala
   import scala.collection.{mutable => m}
   val map = m.HashMap[Int, String]()
   ```

4. 중첩 패키지에서 가져오기
   ```scala
   import java.util.Date
   val currentDate = new Date()
   ```

## 설명
`import` 사용 시 몇 가지 주의해야 할 점이 있습니다:

- **이름 충돌**: 동일한 이름의 클래스나 메서드를 가져올 경우, 컴파일 오류가 발생할 수 있습니다. 이 경우 별칭을 사용하는 것이 좋습니다.
  
- **가져온 구성 요소의 가시성**: `import`는 현재 스코프에만 영향을 미치므로, 다른 스코프에서 사용할 수 없습니다.

- **최적화**: 불필요한 전체 패키지 가져오기는 성능 저하를 초래할 수 있으므로, 필요한 구성 요소만 가져오는 것이 바람직합니다.

## 한 줄 요약
Scala에서 `import`는 다른 패키지의 클래스나 메서드를 현재 스코프에서 사용할 수 있도록 가져오는 기능입니다.