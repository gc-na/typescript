<!--
Meta Description: # TypeScript의 "of"에 대한 완벽한 가이드: 배열과 객체의 이해 ## 개요 TypeScript에서 "of"는 주로 `for...of` 루프에서 사용되며, 이 루프는 이터러블(iterable) 객체(예: 배열, 문자열)의 요소를 반복하는 데 유용합니다. 이 ...
Meta Keywords: const, 객체의, 이터러블, 요소를, typescript
-->

# TypeScript의 "of"에 대한 완벽한 가이드: 배열과 객체의 이해

## 개요
TypeScript에서 "of"는 주로 `for...of` 루프에서 사용되며, 이 루프는 이터러블(iterable) 객체(예: 배열, 문자열)의 요소를 반복하는 데 유용합니다. 이 문법은 코드의 가독성을 높이고, 이터러블 객체의 요소를 쉽게 접근할 수 있게 해줍니다.

## 문서화
### 목적
`for...of` 문은 이터러블 객체의 각 요소를 순회하는 데 사용됩니다. 주로 배열, 문자열, 맵, 세트 등의 컬렉션에 사용됩니다.

### 사용법
`for...of` 문법의 기본 구조는 다음과 같습니다:

```typescript
for (const element of iterable) {
    // element에 대한 작업 수행
}
```
여기서 `iterable`은 이터러블 객체이며, `element`는 해당 객체의 각 요소를 나타냅니다.

### 세부 사항
- `for...of`는 이터레이터 프로토콜을 따르는 객체와 함께 작동합니다.
- 이 문법은 배열, 문자열, 맵 객체 및 세트와 같은 다양한 데이터 구조에서 사용할 수 있습니다.
- `for...of` 루프는 인덱스에 의존하지 않으므로, 요소의 순서를 보장합니다.

## 예제
### 배열의 사용 예

```typescript
const numbers = [1, 2, 3, 4, 5];

for (const number of numbers) {
    console.log(number); // 1, 2, 3, 4, 5 출력
}
```

### 문자열의 사용 예

```typescript
const greeting = "안녕하세요";

for (const char of greeting) {
    console.log(char); // '안', '녕', '하', '세', '요' 출력
}
```

### 세트의 사용 예

```typescript
const uniqueNumbers = new Set([1, 2, 3, 4, 5]);

for (const num of uniqueNumbers) {
    console.log(num); // 1, 2, 3, 4, 5 출력
}
```

## 설명
`for...of` 문은 간단하고 직관적인 문법으로, 이터러블 객체의 요소를 순회하는 데 매우 유용합니다. 하지만 몇 가지 주의할 점이 있습니다:

- **객체**: 일반 객체는 이터러블이 아니므로 `for...of` 문에서 사용할 수 없습니다. 이 경우 `for...in`을 사용해야 합니다.
- **성능**: 대규모 배열이나 복잡한 데이터 구조를 반복할 때는 성능 문제를 고려해야 합니다. `for...of`는 매우 편리하지만, 필요에 따라 적절한 반복 방식을 선택하는 것이 중요합니다.

## 한 줄 요약
TypeScript에서 `for...of` 문은 이터러블 객체의 각 요소를 순회하는 간편한 방법입니다.