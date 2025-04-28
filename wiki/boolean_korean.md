<!--
Meta Description: # TypeScript에서의 Boolean 타입: 기본 개념 및 사용법 ## 개요 TypeScript에서 Boolean 타입은 true와 false 두 가지 값만을 허용하는 기본 데이터 타입입니다. 이 타입은 조건문, 반복문 등에서 로직을 제어하는 데 필수적인 역할을 ...
Meta Keywords: boolean, 타입은, let, true, console
-->

# TypeScript에서의 Boolean 타입: 기본 개념 및 사용법

## 개요
TypeScript에서 Boolean 타입은 true와 false 두 가지 값만을 허용하는 기본 데이터 타입입니다. 이 타입은 조건문, 반복문 등에서 로직을 제어하는 데 필수적인 역할을 합니다.

## 문서화
Boolean 타입은 프로그래밍에서 가장 기본적인 데이터 타입 중 하나로, 조건을 평가하고 흐름 제어를 가능하게 합니다. TypeScript에서는 Boolean 타입이 명시적으로 정의되며, 이를 통해 코드의 가독성을 높이고 타입 안정성을 제공합니다.

### 목적
Boolean 타입은 다음과 같은 목적으로 사용됩니다:
- 조건문에서의 평가
- 반복문의 제어
- 함수의 반환값으로 사용

### 사용법
Boolean 타입은 다음과 같이 선언할 수 있습니다:
```typescript
let isAvailable: boolean = true;
let isCompleted: boolean = false;
```

## 예시
1. 기본 Boolean 값 사용:
   ```typescript
   let isActive: boolean = true;
   console.log(isActive); // true
   ```

2. 조건문에서의 Boolean 활용:
   ```typescript
   let age: number = 20;
   let isAdult: boolean = age >= 18;

   if (isAdult) {
       console.log("성인입니다.");
   } else {
       console.log("미성년자입니다.");
   }
   ```

3. 함수의 반환값으로 사용:
   ```typescript
   function checkEven(num: number): boolean {
       return num % 2 === 0;
   }

   console.log(checkEven(4)); // true
   console.log(checkEven(5)); // false
   ```

## 설명
Boolean 타입을 사용할 때 주의해야 할 점은 다음과 같습니다:
- 다른 데이터 타입과의 혼돈: TypeScript는 엄격한 타입 검사를 수행하므로, Boolean 값은 다른 타입(예: 숫자, 문자열)과 혼합되지 않아야 합니다.
- 잘못된 초기화: Boolean 변수를 선언할 때 true 또는 false로 직접 초기화하지 않으면, TypeScript는 해당 변수가 어떤 값을 가질지 명확히 알 수 없으므로 오류가 발생할 수 있습니다.

## 한 줄 요약
TypeScript의 Boolean 타입은 true와 false만을 허용하며, 조건문과 흐름 제어에 필수적인 역할을 수행합니다.