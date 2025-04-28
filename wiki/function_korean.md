<!--
Meta Description: # TypeScript 함수: 기본 개념과 활용법 ## 개요 TypeScript에서 함수는 특정 작업을 수행하고, 재사용 가능한 코드 블록을 정의하는 중요한 개념입니다. JavaScript의 함수 개념을 바탕으로 하여, TypeScript는 정적 타입을 추가하여 더욱 ...
Meta Keywords: typescript, number, typescript에서, 함수는, 작업을
-->

# TypeScript 함수: 기본 개념과 활용법

## 개요
TypeScript에서 함수는 특정 작업을 수행하고, 재사용 가능한 코드 블록을 정의하는 중요한 개념입니다. JavaScript의 함수 개념을 바탕으로 하여, TypeScript는 정적 타입을 추가하여 더욱 안전하고 명확한 함수 정의를 가능하게 합니다.

## 문서화
TypeScript에서 함수는 입력값(매개변수)을 받아 특정한 작업을 수행한 후, 결과값(반환값)을 반환하는 코드 블록입니다. 함수는 다음과 같은 목적을 가지고 사용됩니다:

- **코드 재사용성**: 동일한 코드를 여러 번 작성할 필요 없이, 함수 호출만으로 반복적인 작업을 수행할 수 있습니다.
- **모듈화**: 기능별로 코드를 나누어 관리할 수 있어 유지보수와 가독성을 높입니다.
- **타입 안전성**: TypeScript의 정적 타입 시스템을 통해 함수의 매개변수와 반환값에 대한 타입을 명확히 지정할 수 있습니다.

### 함수 정의
TypeScript에서 함수는 다음과 같은 형식으로 정의할 수 있습니다:

```typescript
function 함수이름(매개변수: 타입): 반환타입 {
    // 실행할 코드
}
```

## 예제
1. 기본 함수 정의 및 호출
```typescript
function greet(name: string): string {
    return `Hello, ${name}!`;
}

console.log(greet("TypeScript")); // 출력: Hello, TypeScript!
```

2. 선택적 매개변수
```typescript
function multiply(a: number, b?: number): number {
    return b ? a * b : a;
}

console.log(multiply(5)); // 출력: 5
console.log(multiply(5, 2)); // 출력: 10
```

3. 기본 매개변수
```typescript
function add(a: number, b: number = 10): number {
    return a + b;
}

console.log(add(5)); // 출력: 15
```

## 설명
TypeScript에서 함수 사용 시 주의해야 할 몇 가지 사항은 다음과 같습니다:

- **타입 불일치**: 매개변수의 타입이 함수 호출 시 제공된 인수의 타입과 일치하지 않으면 컴파일 오류가 발생합니다.
- **this 키워드**: 클래스 내부의 메서드에서 `this`를 사용할 때, 함수의 호출 방식에 따라 값이 달라질 수 있습니다. 이를 피하기 위해 화살표 함수를 사용하는 것이 좋습니다.
- **콜백 함수**: 비동기 작업이나 이벤트 처리 시 콜백 함수를 사용할 때, 타입을 명확히 지정하여 코드의 가독성을 높이는 것이 유리합니다.

## 한줄 요약
TypeScript에서 함수는 입력값을 받아 특정 작업을 수행하고 결과값을 반환하는 재사용 가능한 코드 블록입니다.