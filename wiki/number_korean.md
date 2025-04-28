<!--
Meta Description: # TypeScript에서의 숫자 타입 (number) 완벽 가이드 ## 개요 TypeScript에서의 `number` 타입은 정수와 부동 소수점 숫자를 모두 포함하는 숫자 데이터 타입입니다. JavaScript의 숫자 처리 방식을 기반으로 하며, 다양한 수치 연산을 ...
Meta Keywords: number, let, typescript, 있습니다, 타입은
-->

# TypeScript에서의 숫자 타입 (number) 완벽 가이드

## 개요
TypeScript에서의 `number` 타입은 정수와 부동 소수점 숫자를 모두 포함하는 숫자 데이터 타입입니다. JavaScript의 숫자 처리 방식을 기반으로 하며, 다양한 수치 연산을 지원합니다.

## 문서화
`number` 타입은 TypeScript에서 숫자를 표현하고 조작하는 데 사용됩니다. JavaScript와 마찬가지로, TypeScript의 `number`는 IEEE 754 표준의 배정밀도 부동 소수점 숫자를 사용하여 숫자를 표현하며, 정수 및 소수 모두를 포함합니다. 

### 목적
- 숫자 데이터를 유형 안전하게 다루기 위해 사용됩니다.
- 수치 연산, 비교, 조건문 등에서 활용됩니다.

### 사용법
`number` 타입은 변수 선언 시 다음과 같이 사용됩니다:

```typescript
let age: number = 30;
let temperature: number = -12.5;
```

`number` 타입의 변수는 일반적인 수치 연산에 사용될 수 있습니다:

```typescript
let a: number = 10;
let b: number = 20;
let sum: number = a + b;  // 30
```

## 예제
아래는 TypeScript에서 `number` 타입을 사용하는 몇 가지 기본 예제입니다.

### 정수 사용 예

```typescript
let count: number = 100;
console.log(count); // 100
```

### 부동 소수점 숫자 사용 예

```typescript
let price: number = 19.99;
console.log(price); // 19.99
```

### 수치 연산 예

```typescript
let x: number = 5;
let y: number = 2;
let result: number = x * y; // 10
console.log(result); // 10
```

## 설명
`number` 타입을 사용할 때 주의해야 할 몇 가지 사항이 있습니다.

### 일반적인 함정
1. **정밀도 문제**: 부동 소수점 숫자는 정밀도가 제한적이므로, 소수 계산 시 예기치 못한 결과가 나올 수 있습니다. 예를 들어, `0.1 + 0.2`는 `0.30000000000000004`로 계산됩니다.
   
2. **NaN과 Infinity**: 연산 중 0으로 나누거나 잘못된 수치 연산을 수행하면 `NaN` (Not-a-Number)이나 `Infinity`가 발생할 수 있습니다.

3. **타입 검사**: TypeScript의 타입 검사는 런타임이 아닌 컴파일 타임에 이루어지므로, 숫자 연산 시 타입 오류를 사전에 방지할 수 있습니다.

## 한 줄 요약
TypeScript의 `number` 타입은 정수 및 부동 소수점을 포함하는 숫자 데이터 타입으로, 다양한 수치 연산을 안전하게 수행할 수 있게 해줍니다.