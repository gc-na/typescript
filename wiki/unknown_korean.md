<!--
Meta Description: # TypeScript의 unknown 유형: 사용법 및 설명 ## 개요 TypeScript에서 `unknown`은 모든 값의 상위를 나타내는 특수한 타입으로, 안전한 타입 검사를 가능하게 합니다. 이는 `any` 타입보다 더 안전하며, 개발자가 값의 타입을 명확히 확...
Meta Keywords: unknown, value, 검사를, 타입을, 합니다
-->

# TypeScript의 unknown 유형: 사용법 및 설명

## 개요
TypeScript에서 `unknown`은 모든 값의 상위를 나타내는 특수한 타입으로, 안전한 타입 검사를 가능하게 합니다. 이는 `any` 타입보다 더 안전하며, 개발자가 값의 타입을 명확히 확인하도록 요구합니다.

## 문서화
`unknown` 타입은 TypeScript 3.0에서 도입된 기능으로, 예상치 못한 값이 들어올 수 있는 변수에 대해 안전성을 제공합니다. `unknown` 타입의 변수를 사용하면 해당 변수를 사용할 때 반드시 타입 검사를 수행해야 하므로, 코드의 안정성을 높이는 데 도움이 됩니다.

### 용도
- `unknown`은 값이 어떤 타입일지 모를 때 사용되며, 나중에 정확한 타입을 확인한 후에 사용될 수 있습니다.
- 외부 API로부터 받은 데이터나, 유저 입력과 같이 예측할 수 없는 값을 처리할 때 유용합니다.

### 사용법
타입을 명시적으로 지정하지 않고 변수에 `unknown`을 할당할 수 있습니다. 이후, 사용하기 전에 반드시 해당 값의 타입을 체크해야 합니다.

## 예제
```typescript
let value: unknown;

// unknown 타입의 변수에 값 할당
value = 42;
value = "Hello TypeScript";

// 타입 체크 후 사용
if (typeof value === "string") {
    console.log(value.toUpperCase()); // "HELLO TYPESCRIPT"
}

// 오류 발생: value가 string이 아닐 경우
// console.log(value.length); // 오류: 'length'는 'unknown' 타입에 존재하지 않습니다.
```

## 설명
`unknown`을 사용할 때 주의할 점은, 이 타입의 변수를 사용할 때 반드시 타입 검사를 수행해야 한다는 것입니다. 이는 `any` 타입과의 큰 차별점이며, `any`는 타입 검사를 우회할 수 있도록 해줍니다. 즉, `unknown`은 보다 안전한 타입 시스템을 제공합니다. 

### 흔한 함정
- `unknown` 타입의 변수를 직접 사용하려고 하면 오류가 발생합니다. 반드시 타입을 확인한 후에 사용해야 합니다.
- `unknown`은 다른 타입으로 자동 변환되지 않기 때문에, 특정 타입으로 변환하려면 타입 단언(type assertion)을 사용해야 합니다.

## 한 줄 요약
TypeScript의 `unknown` 타입은 안전한 타입 검사를 제공하여 예측할 수 없는 값을 다룰 때 유용한 타입입니다.