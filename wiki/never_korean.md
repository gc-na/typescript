<!--
Meta Description: # TypeScript의 never 타입: 완벽 가이드 ## 개요 TypeScript의 `never` 타입은 함수가 절대 값을 반환하지 않거나, 변수가 절대 유효한 값을 가질 수 없음을 나타냅니다. 이는 오류 처리, 무한 루프, 또는 특정 조건에서 실행되지 않는 코드 ...
Meta Keywords: never, value, 타입은, function, string
-->

# TypeScript의 never 타입: 완벽 가이드

## 개요
TypeScript의 `never` 타입은 함수가 절대 값을 반환하지 않거나, 변수가 절대 유효한 값을 가질 수 없음을 나타냅니다. 이는 오류 처리, 무한 루프, 또는 특정 조건에서 실행되지 않는 코드 경로를 나타내는 데 유용합니다.

## 문서화
`never` 타입은 TypeScript의 강력한 타입 시스템에서 중요한 역할을 합니다. 이 타입은 다음과 같은 경우에 사용됩니다:

- **함수가 오류를 던질 때**: 함수가 예외를 발생시켜 종료되는 경우, 이 함수의 반환 타입은 `never`입니다.
- **무한 루프**: 끝없이 실행될 것이라고 예상되는 함수의 경우, 마찬가지로 `never` 타입을 사용합니다.
- **유효한 값이 존재하지 않을 때**: 특정 조건에 따라 코드 실행이 불가능할 경우, `never`를 사용하여 해당 코드 경로가 존재하지 않음을 명확히 할 수 있습니다.

### 사용법
`never` 타입은 일반적으로 다음과 같은 방식으로 사용됩니다:

```typescript
function throwError(message: string): never {
    throw new Error(message);
}

function infiniteLoop(): never {
    while (true) {}
}

function checkValue(value: string | null): string {
    if (value === null) {
        throwError("value cannot be null");
    }
    return value;
}
```

## 예시
1. **오류 발생 함수**:
   ```typescript
   function throwError(message: string): never {
       throw new Error(message);
   }
   ```

2. **무한 루프 함수**:
   ```typescript
   function infiniteLoop(): never {
       while (true) {}
   }
   ```

3. **조건부 체크**:
   ```typescript
   function checkValue(value: string | null): string {
       if (value === null) {
           throwError("value cannot be null");
       }
       return value;
   }
   ```

## 설명
`never` 타입을 사용할 때 주의해야 할 점은 다음과 같습니다:

- **타입 추론**: TypeScript는 함수가 어떤 값을 반환하지 않거나, 특정 조건에서 종료되는 경우 `never` 타입을 자동으로 추론합니다. 이는 코드의 가독성과 안전성을 높여줍니다.
- **함수의 반환 타입**: 반환 타입이 `never`인 함수를 호출한 후에는 그 이후의 코드가 실행되지 않음을 이해해야 합니다.
- **사용 시기**: `never` 타입은 일반적으로 예외 처리나 유효성 검증에 사용되며, 잘못 사용하면 코드의 의미를 왜곡할 수 있습니다.

## 한 줄 요약
TypeScript의 `never` 타입은 함수가 값을 반환하지 않거나, 변수가 유효한 값을 가질 수 없음을 나타내는 강력한 타입입니다.