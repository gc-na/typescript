<!--
Meta Description: # TypeScript의 return: 함수 반환값 관리하기 ## 개요 TypeScript에서 `return` 키워드는 함수의 실행 결과를 반환하는 데 사용됩니다. 이 명령은 함수의 종료를 나타내며, 함수 호출 시 해당 값을 사용할 수 있도록 합니다. ## 문서화 `r...
Meta Keywords: return, 함수의, typescript에서, 사용할, 있습니다
-->

# TypeScript의 return: 함수 반환값 관리하기

## 개요
TypeScript에서 `return` 키워드는 함수의 실행 결과를 반환하는 데 사용됩니다. 이 명령은 함수의 종료를 나타내며, 함수 호출 시 해당 값을 사용할 수 있도록 합니다.

## 문서화
`return`은 TypeScript에서 함수의 결과값을 명시적으로 반환할 때 사용됩니다. 함수는 여러 가지 작업을 수행한 후, 그 결과를 호출된 곳으로 돌려보내야 할 필요가 있습니다. `return`을 사용하면 필요한 데이터나 상태 정보를 전달할 수 있으며, 이를 통해 프로그램의 흐름을 제어할 수 있습니다.

### 용도
- 함수의 결과값을 반환합니다.
- 함수의 실행을 종료합니다.
- 반환 타입을 명시하여 타입 안정성을 높입니다.

### 사용법
TypeScript에서 `return`을 사용할 때는 다음과 같은 형식을 따릅니다:
```typescript
function 함수이름(매개변수: 타입): 반환타입 {
    // 함수 로직
    return 반환값; // 반환값은 반환타입과 일치해야 함
}
```

## 예제
다음은 기본적인 사용 예제입니다:

### 예제 1: 정수 더하기
```typescript
function add(a: number, b: number): number {
    return a + b;
}

const result = add(5, 3); // result는 8이 됩니다.
```

### 예제 2: 문자열 연결
```typescript
function concatenate(str1: string, str2: string): string {
    return str1 + str2;
}

const combined = concatenate("Hello, ", "World!"); // combined는 "Hello, World!"가 됩니다.
```

## 설명
`return` 키워드를 사용할 때 몇 가지 주의할 점이 있습니다:

1. **반환 타입 일치**: `return` 값의 타입이 함수의 반환 타입과 일치해야 합니다. 타입이 다르면 컴파일 오류가 발생합니다.
2. **명시적 반환**: TypeScript는 함수가 반환하는 값의 타입을 유추할 수 있지만, 명시적으로 반환 타입을 정의하는 것이 좋습니다. 이를 통해 코드를 더욱 명확하게 만들 수 있습니다.
3. **여러 반환문**: 함수 내에서 여러 `return` 문을 사용할 수 있지만, 한 번 호출되면 함수는 종료됩니다. 이후의 코드는 실행되지 않으므로 주의해야 합니다.

## 한 줄 요약
TypeScript에서 `return`은 함수의 결과값을 반환하고 실행을 종료하는 데 사용됩니다.