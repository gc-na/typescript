<!--
Meta Description: # TypeScript의 else 문: 조건문 제어 ## 개요 TypeScript에서 `else` 문은 조건문(`if`)과 함께 사용되어 특정 조건이 거짓일 때 실행될 코드를 정의하는 데 사용됩니다. 이를 통해 코드의 흐름을 제어하고, 다양한 상황에 대한 처리를 보다 ...
Meta Keywords: else, 조건이, 실행될, score, console
-->

# TypeScript의 else 문: 조건문 제어

## 개요
TypeScript에서 `else` 문은 조건문(`if`)과 함께 사용되어 특정 조건이 거짓일 때 실행될 코드를 정의하는 데 사용됩니다. 이를 통해 코드의 흐름을 제어하고, 다양한 상황에 대한 처리를 보다 유연하게 수행할 수 있습니다.

## 문서화
`else` 문은 `if` 문과 함께 사용되며, 주어진 조건이 거짓일 경우 실행될 대체 경로를 제공합니다. 기본적인 사용 형식은 다음과 같습니다:

```typescript
if (조건) {
    // 조건이 참일 때 실행될 코드
} else {
    // 조건이 거짓일 때 실행될 코드
}
```

### 용도
- `else` 문은 조건이 충족되지 않았을 때 어떤 작업을 수행할지를 정의합니다.
- 여러 조건을 평가할 때 `if...else if...else` 구문을 통해 다양한 경우에 대한 처리가 가능합니다.

### 세부 사항
- TypeScript는 JavaScript의 슈퍼셋이므로, `else` 문은 JavaScript와 동일한 방식으로 작동합니다.
- 조건문 내에서 여러 개의 `else if`를 사용할 수 있으며, 이는 코드의 가독성을 높이고 복잡한 로직을 간단하게 처리하는 데 유용합니다.

## 예제
### 기본 사용법
```typescript
let score: number = 85;

if (score >= 90) {
    console.log("A");
} else {
    console.log("B");
}
```

### 여러 조건 처리
```typescript
let score: number = 75;

if (score >= 90) {
    console.log("A");
} else if (score >= 80) {
    console.log("B");
} else {
    console.log("C");
}
```

## 설명
- **일반적인 실수**: `else` 문은 항상 `if` 문과 함께 사용되어야 하며, 단독으로 사용할 수 없습니다.
- **중첩된 조건**: `else` 문은 다른 조건문과 중첩될 수 있지만, 이 경우 가독성이 떨어질 수 있으므로 주의해야 합니다.
- **타입스크립트의 타입 검사**: TypeScript의 타입 검사를 활용하여 `if` 문 내 조건이 특정 타입인지 확인함으로써, 코드의 안정성을 높일 수 있습니다. 

## 한 줄 요약
TypeScript의 `else` 문은 조건이 거짓일 때 실행될 코드 블록을 정의하여 프로그램의 흐름을 제어하는 데 사용됩니다.