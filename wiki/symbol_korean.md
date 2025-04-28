<!--
Meta Description: # TypeScript의 Symbol: 고유한 식별자를 생성하는 방법 ## 개요 TypeScript에서 `Symbol`은 고유하고 변경 불가능한 데이터 타입으로, 객체의 고유한 식별자를 만들기 위해 사용됩니다. 이 기능은 객체의 속성 이름이 충돌하는 것을 방지하고, 비...
Meta Keywords: symbol, 객체의, 고유한, const, 일반적인
-->

# TypeScript의 Symbol: 고유한 식별자를 생성하는 방법

## 개요
TypeScript에서 `Symbol`은 고유하고 변경 불가능한 데이터 타입으로, 객체의 고유한 식별자를 만들기 위해 사용됩니다. 이 기능은 객체의 속성 이름이 충돌하는 것을 방지하고, 비공식적인 API를 구현하는 데 유용합니다.

## 문서화
### 목적
`Symbol`은 JavaScript의 기본 데이터 타입 중 하나로, TypeScript에서도 동일하게 사용할 수 있습니다. 주로 객체의 속성 이름으로 사용되며, 각 `Symbol`은 고유한 값을 가지므로, 다른 `Symbol`과 충돌하지 않습니다.

### 사용법
`Symbol`을 생성하는 방법은 `Symbol()` 함수를 호출하여 생성합니다. 선택적으로 설명 문자열을 인자로 제공할 수 있으며, 이는 디버깅 시 유용합니다.

```typescript
const mySymbol = Symbol('description');
```

이렇게 생성된 `mySymbol`은 다른 어떤 `Symbol`과도 동일하지 않은 고유한 값입니다.

### 세부사항
- `Symbol`은 객체 속성의 키로 사용될 수 있으며, 객체의 프로퍼티 접근 시 일반적인 문자열 키와는 다르게 동작합니다.
- `Symbol`은 전역적으로 공유되지는 않지만, 같은 설명 문자열을 가진 `Symbol`을 여러 번 생성해도 각기 다른 값을 생성합니다.
- `Symbol.for()` 메서드를 사용하면 전역 심볼 레지스트리에 접근하여 같은 키를 가진 심볼을 공유할 수 있습니다.

## 예시
```typescript
const sym1 = Symbol('key1');
const sym2 = Symbol('key1');

console.log(sym1 === sym2); // false

const obj = {
  [sym1]: 'value1'
};

console.log(obj[sym1]); // 'value1'
console.log(obj[sym2]); // undefined
```

## 설명
`Symbol`을 사용할 때 주의할 점은 다음과 같습니다:
- `Symbol`은 객체의 속성으로 사용될 때만 고유성을 발휘합니다. 일반적인 변수나 값으로는 고유성이 보장되지 않습니다.
- `Symbol`을 JSON.stringify()로 직렬화할 수 없으므로, 객체를 JSON으로 변환할 때 `Symbol` 속성은 무시됩니다.
- `Symbol`을 사용하여 생성한 객체의 속성은 `for...in` 루프와 같은 일반적인 루프에서 접근할 수 없습니다. 이는 `Symbol`이 일반적인 문자열 키와는 다르게 동작하기 때문입니다.

## 한 줄 요약
TypeScript의 `Symbol`은 고유하고 변경 불가능한 식별자를 생성하여 객체의 속성 이름 충돌을 방지하는 데 유용한 데이터 타입입니다.