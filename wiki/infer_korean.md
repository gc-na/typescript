<!--
Meta Description: # TypeScript의 infer: 타입 추론의 모든 것 ## 개요 TypeScript의 `infer` 키워드는 타입 추론을 통해 보다 유연한 타입 정의를 가능하게 하는 기능입니다. 이를 통해 복잡한 타입을 동적으로 추론할 수 있어 코드의 가독성과 유지보수성을 높일 ...
Meta Keywords: infer, 타입을, type, typescript의, 복잡한
-->

# TypeScript의 infer: 타입 추론의 모든 것

## 개요
TypeScript의 `infer` 키워드는 타입 추론을 통해 보다 유연한 타입 정의를 가능하게 하는 기능입니다. 이를 통해 복잡한 타입을 동적으로 추론할 수 있어 코드의 가독성과 유지보수성을 높일 수 있습니다.

## 문서화
`infer`는 TypeScript의 조건부 타입에서 사용되며, 특정 타입을 추론할 수 있게 합니다. 이 기능은 주로 타입 매개변수의 유형을 결정하는 데 유용합니다. `infer`를 사용할 때는 다음과 같은 문법을 사용합니다:

```typescript
type MyType<T> = T extends SomeType<infer U> ? U : never;
```

위 예제에서 `T`가 `SomeType`의 하위 타입인 경우, `U`를 추론하여 반환합니다. 그렇지 않다면 `never`를 반환합니다. 이를 통해 복잡한 타입의 변환이나 조작이 가능해집니다.

## 예제
### 기본 사용 예제

```typescript
type ElementType<T> = T extends (infer U)[] ? U : never;

type NumberArray = number[];
type ExtractedType = ElementType<NumberArray>; // ExtractedType은 number가 됩니다.
```

위의 예제에서, `ElementType`은 배열의 요소 타입을 추론하여 반환합니다. `NumberArray`가 `number[]`이므로, `ExtractedType`은 `number`로 추론됩니다.

### 조건부 타입과 결합된 예제

```typescript
type ReturnType<T> = T extends (...args: any[]) => infer R ? R : never;

type MyFunction = (input: string) => boolean;
type Result = ReturnType<MyFunction>; // Result는 boolean이 됩니다.
```

여기서는 함수의 반환 타입을 추론하는 `ReturnType` 타입을 정의했습니다. `MyFunction`의 반환 타입은 `boolean`이므로, `Result`는 `boolean`으로 추론됩니다.

## 설명
`infer`를 사용할 때 몇 가지 주의할 점이 있습니다:

1. **제한된 범위**: `infer`는 조건부 타입 내에서만 사용할 수 있습니다. 이 점을 유의해야 합니다.
2. **명확한 타입 표현**: `infer`를 사용할 때는 타입이 명확해야 합니다. 그렇지 않으면 TypeScript가 타입을 올바르게 추론하지 못할 수 있습니다.
3. **복잡한 타입**: 복잡한 타입의 경우, `infer`를 사용하여 중첩된 타입을 추론하는 것이 가능합니다. 그러나 이로 인해 코드가 복잡해질 수 있으므로 가독성을 고려해야 합니다.

## 한 줄 요약
TypeScript의 `infer`는 조건부 타입 내에서 특정 타입을 동적으로 추론하는 기능입니다.