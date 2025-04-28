<!--
Meta Description: # TypeScript의 Enum: 타입 안전성을 위한 열거형 ## 개요 TypeScript의 Enum은 관련된 상수 집합을 정의할 수 있는 강력한 기능으로, 코드의 가독성과 유지 보수를 향상시키는 데 기여합니다. Enum은 명확한 의미를 가진 값으로 코드를 작성할 수...
Meta Keywords: enum, 문자열, enum은, typescript, yes
-->

# TypeScript의 Enum: 타입 안전성을 위한 열거형

## 개요
TypeScript의 Enum은 관련된 상수 집합을 정의할 수 있는 강력한 기능으로, 코드의 가독성과 유지 보수를 향상시키는 데 기여합니다. Enum은 명확한 의미를 가진 값으로 코드를 작성할 수 있게 해줍니다.

## 문서화

### 목적
Enum은 관련된 값을 그룹화하여 코드의 의미를 명확히 하고, 타입 안전성을 제공하는 데 사용됩니다. 이를 통해 개발자는 코드에서 상수를 사용할 때 발생할 수 있는 오류를 줄일 수 있습니다.

### 사용법
TypeScript에서 Enum을 정의하려면 `enum` 키워드를 사용합니다. 기본적으로 숫자 값에 매핑되지만, 문자열 값도 사용할 수 있습니다.

#### 기본 구문
```typescript
enum EnumName {
    Member1,
    Member2,
    Member3,
}
```

### 자세한 설명
TypeScript에서 Enum은 다음과 같은 유형으로 나뉩니다:

1. **숫자 Enum**: 기본적으로 0부터 시작하여 자동으로 증가하는 숫자 값을 가집니다.
   ```typescript
   enum Direction {
       Up,
       Down,
       Left,
       Right,
   }
   ```

2. **문자열 Enum**: 각 멤버에 대해 수동으로 문자열 값을 지정할 수 있습니다.
   ```typescript
   enum Response {
       Yes = "YES",
       No = "NO",
   }
   ```

3. **이니셜라이즈된 숫자 Enum**: 첫 번째 값을 지정하고 이후 값들을 자동으로 증가시킬 수 있습니다.
   ```typescript
   enum Status {
       Active = 1,
       Inactive,
       Pending,
   }
   ```

4. **이니셜라이즈된 문자열 Enum**: 모든 멤버에 대해 수동으로 문자열 값을 지정해야 합니다.
   ```typescript
   enum Color {
       Red = "RED",
       Green = "GREEN",
       Blue = "BLUE",
   }
   ```

## 예제

### 기본 숫자 Enum 예제
```typescript
enum Direction {
    Up,
    Down,
    Left,
    Right,
}

let move: Direction = Direction.Up;
console.log(move); // 0
```

### 문자열 Enum 예제
```typescript
enum Response {
    Yes = "YES",
    No = "NO",
}

let answer: Response = Response.Yes;
console.log(answer); // "YES"
```

### 이니셜라이즈된 숫자 Enum 예제
```typescript
enum Status {
    Active = 1,
    Inactive,
    Pending,
}

let currentStatus: Status = Status.Pending;
console.log(currentStatus); // 3
```

## 설명
Enum 사용 시 주의해야 할 점은 다음과 같습니다:

- Enum은 항상 특정 타입을 갖는 것이 아니며, 숫자 Enum은 기본적으로 숫자 타입으로 취급됩니다.
- 문자열 Enum은 항상 문자열 타입으로 취급되며, 각 멤버는 고유한 문자열 값을 가져야 합니다.
- Enum 멤버는 항상 고유해야 하며, 중복된 값이 존재할 경우 예기치 않은 동작이 발생할 수 있습니다.
- Enum을 사용하여 잘못된 값이 할당되는 것을 방지하기 위해, Enum 타입을 사용하여 변수의 타입을 제한하는 것이 좋습니다.

## 한 줄 요약
TypeScript의 Enum은 관련된 상수 집합을 정의하여 코드의 가독성과 타입 안전성을 높이는 기능입니다.