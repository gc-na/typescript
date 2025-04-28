<!--
Meta Description: # TypeScript의 keyof: 타입 안전성을 높이는 강력한 도구 ## 개요 `keyof`는 TypeScript에서 객체 타입의 키를 추출할 수 있는 유용한 연산자입니다. 이를 통해 객체의 속성 이름을 타입으로 사용할 수 있어, 코드의 타입 안전성을 높이고 오류를...
Meta Keywords: keyof, type, person, car, 객체의
-->

# TypeScript의 keyof: 타입 안전성을 높이는 강력한 도구

## 개요
`keyof`는 TypeScript에서 객체 타입의 키를 추출할 수 있는 유용한 연산자입니다. 이를 통해 객체의 속성 이름을 타입으로 사용할 수 있어, 코드의 타입 안전성을 높이고 오류를 줄이는 데 기여합니다.

## 문서화
`keyof` 연산자는 특정 객체 타입의 모든 키를 유니온 타입으로 반환합니다. 이 연산자는 일반적으로 타입 안전성을 유지하면서 객체의 속성을 다루고자 할 때 사용됩니다. `keyof`는 다음과 같은 상황에서 유용합니다:

- 객체의 속성을 동적으로 접근할 때, 해당 속성이 실제로 존재하는지 확인할 수 있습니다.
- 객체의 키를 타입으로 사용하여, 함수에서 해당 키를 안전하게 다룰 수 있습니다.

### 사용법
`keyof` 연산자의 기본 문법은 다음과 같습니다:

```typescript
type ObjectType = {
  key1: string;
  key2: number;
};

type Keys = keyof ObjectType; // "key1" | "key2"
```

여기서 `Keys`는 `ObjectType`의 모든 키인 `"key1"`과 `"key2"`를 타입으로 가지게 됩니다.

## 예제
### 기본 사용 예제
```typescript
type Person = {
  name: string;
  age: number;
};

type PersonKeys = keyof Person; // "name" | "age"

function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const person: Person = { name: "Alice", age: 30 };
const name = getProperty(person, "name"); // "Alice"
const age = getProperty(person, "age"); // 30
```

### 객체와 함께 사용하기
```typescript
type Car = {
  make: string;
  model: string;
  year: number;
};

type CarKeys = keyof Car; // "make" | "model" | "year"

function logCarProperty(car: Car, key: CarKeys) {
  console.log(car[key]);
}

const myCar: Car = { make: "Toyota", model: "Corolla", year: 2020 };
logCarProperty(myCar, "make"); // "Toyota"
```

## 설명
`keyof`를 사용할 때 몇 가지 주의해야 할 점이 있습니다:

1. **인덱스 서브스크립션**: `keyof`는 객체 타입의 모든 키를 유니온으로 반환하므로, 잘못된 키를 사용하여 인덱스 서브스크립션을 시도하면 타입 오류가 발생합니다.
   
2. **제네릭과의 조합**: `keyof`는 제네릭 타입과 함께 사용될 때 특히 강력합니다. 제네릭을 통해 다양한 객체 타입에서 키를 안전하게 추출할 수 있습니다.

3. **필수 속성만 포함**: `keyof`는 객체의 필수 속성만을 고려합니다. 선택적 속성은 결과에 포함되지 않습니다.

## 한 줄 요약
`keyof`는 TypeScript에서 객체 타입의 모든 키를 유니온 타입으로 추출하여 타입 안전성을 높이는 유용한 연산자입니다.