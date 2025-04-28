<!--
Meta Description: # TypeScript에서 const의 사용법: 상수 선언과 관리 ## 개요 TypeScript에서 `const`는 변수를 선언할 때 사용되는 키워드로, 선언된 변수의 값을 변경할 수 없도록 제한합니다. 이는 코드의 가독성을 높이고, 의도치 않은 값 변경을 방지하는 데...
Meta Keywords: const, typescript, 변수의, user, age
-->

# TypeScript에서 const의 사용법: 상수 선언과 관리

## 개요
TypeScript에서 `const`는 변수를 선언할 때 사용되는 키워드로, 선언된 변수의 값을 변경할 수 없도록 제한합니다. 이는 코드의 가독성을 높이고, 의도치 않은 값 변경을 방지하는 데 도움을 줍니다.

## 문서화
`const`는 JavaScript와 TypeScript 모두에서 사용되며, 변수의 값을 상수로 유지하려는 목적으로 사용됩니다. `const`로 선언된 변수는 초기화 시 반드시 값을 할당해야 하며, 이후에는 재할당이 불가능합니다. 이는 변수의 불변성을 보장하여, 코드의 안정성과 예측 가능성을 증가시킵니다.

### 사용법
`const`를 사용하여 변수를 선언하는 기본 문법은 다음과 같습니다:

```typescript
const 변수명: 데이터타입 = 초기값;
```

- **변수명**: 선언할 변수의 이름.
- **데이터타입**: 변수의 타입을 지정 (선택적).
- **초기값**: 변수가 가질 초기값.

변수 선언 후에는 해당 변수를 재할당할 수 없습니다. 예를 들어:

```typescript
const PI: number = 3.14;
// PI = 3.14159; // 오류 발생: 'PI'는 읽기 전용입니다.
```

## 예제
### 기본 사용 예제
```typescript
const greeting: string = "안녕하세요";
console.log(greeting); // 출력: 안녕하세요
```

### 배열 사용 예제
```typescript
const numbers: number[] = [1, 2, 3];
console.log(numbers); // 출력: [1, 2, 3]

// numbers.push(4); // 배열의 내용은 변경 가능하지만, numbers 변수 자체는 재할당 불가
```

### 객체 사용 예제
```typescript
const user: { name: string, age: number } = { name: "홍길동", age: 30 };
console.log(user); // 출력: { name: "홍길동", age: 30 }

// user.age = 31; // 객체의 속성은 변경 가능
// user = { name: "이순신", age: 40 }; // 오류 발생: 'user'는 읽기 전용입니다.
```

## 설명
`const` 키워드를 사용할 때 주의해야 할 점은, 변수 자체는 변경할 수 없지만, 객체나 배열의 경우 그 내부 상태는 변경할 수 있다는 것입니다. 이는 종종 혼란을 초래할 수 있으므로, 객체나 배열을 사용할 때는 이러한 점을 인지하고 있어야 합니다.

또한, `const`로 선언된 변수는 블록 스코프를 가지므로, 변수 선언이 이루어진 블록 내에서만 접근할 수 있습니다. 이는 `var`와는 다른 점입니다.

## 한 줄 요약
TypeScript에서 `const`는 변수를 상수로 선언하여 값의 재할당을 방지하는 키워드입니다.