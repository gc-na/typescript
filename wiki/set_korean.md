<!--
Meta Description: # TypeScript에서의 Set: 데이터 구조와 활용 ## 개요 TypeScript의 `Set` 객체는 고유한 값을 저장하는 데이터 구조로, 중복을 허용하지 않으며 순서가 있는 값의 집합을 관리하는 데 유용합니다. 이 자료구조는 특히 데이터의 유일성을 보장하고, 집...
Meta Keywords: set, numbers, type, add, console
-->

# TypeScript에서의 Set: 데이터 구조와 활용

## 개요
TypeScript의 `Set` 객체는 고유한 값을 저장하는 데이터 구조로, 중복을 허용하지 않으며 순서가 있는 값의 집합을 관리하는 데 유용합니다. 이 자료구조는 특히 데이터의 유일성을 보장하고, 집합 연산을 수행할 때 유용합니다.

## 문서화
### 목적
`Set`은 중복된 값을 허용하지 않고, 데이터의 유일성을 보장하는 자료구조입니다. 이는 특히 데이터베이스에서 중복 데이터를 처리할 필요가 있을 때 유용합니다.

### 사용법
TypeScript에서 `Set`을 사용하려면 먼저 `Set` 객체를 생성합니다. 기본적인 사용법은 다음과 같습니다:

```typescript
const mySet = new Set<Type>([iterable]);
```

여기서 `Type`은 저장할 값의 유형을 지정하며, `iterable`은 초기 값을 담고 있는 배열이나 유사 배열입니다.

### 주요 메서드
- `add(value: Type)`: 집합에 값을 추가합니다.
- `delete(value: Type)`: 집합에서 값을 제거합니다.
- `has(value: Type)`: 집합에 값이 존재하는지 확인합니다.
- `clear()`: 집합의 모든 값을 제거합니다.
- `size`: 집합에 저장된 값의 개수를 반환합니다.

## 예제
다음은 `Set` 객체를 사용하는 기본적인 예제입니다.

```typescript
// Set 객체 생성
const numbers = new Set<number>();

// 값 추가
numbers.add(1);
numbers.add(2);
numbers.add(3);
numbers.add(2); // 중복 값은 무시됨

console.log(numbers); // Set { 1, 2, 3 }

// 값 존재 여부 확인
console.log(numbers.has(2)); // true
console.log(numbers.has(5)); // false

// 값 삭제
numbers.delete(2);
console.log(numbers); // Set { 1, 3 }

// 전체 값 제거
numbers.clear();
console.log(numbers); // Set {}
```

## 설명
`Set` 객체를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

1. **중복 처리**: `Set`은 중복된 값을 자동으로 무시합니다. 따라서 추가한 값이 이미 존재할 경우, 아무런 변화가 없습니다.
   
2. **참조 타입**: 객체나 배열 같은 참조 타입의 경우, 값이 동일하더라도 서로 다른 인스턴스라면 중복으로 취급됩니다.

3. **순서 보장**: `Set`은 입력된 순서를 유지하므로, 순차적으로 값을 처리할 수 있습니다.

4. **이터러블 지원**: `Set`은 배열, 문자열 등의 이터러블을 수용할 수 있으며, 이를 통해 초기화할 수 있습니다.

## 한 줄 요약
TypeScript의 `Set`은 중복을 허용하지 않는 값의 집합을 관리하는 데이터 구조로, 유일성을 보장하고 집합 연산을 수행하는 데 유용합니다.