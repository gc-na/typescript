<!--
Meta Description: # TypeScript의 switch 문: 조건에 따른 분기 처리 ## 개요 TypeScript에서 `switch` 문은 여러 개의 분기 중 하나를 선택하여 실행할 수 있는 제어 구조입니다. 이는 `if`-`else` 문보다 가독성이 좋고, 여러 조건을 처리할 때 유용...
Meta Keywords: case, break, switch, console, log
-->

# TypeScript의 switch 문: 조건에 따른 분기 처리

## 개요
TypeScript에서 `switch` 문은 여러 개의 분기 중 하나를 선택하여 실행할 수 있는 제어 구조입니다. 이는 `if`-`else` 문보다 가독성이 좋고, 여러 조건을 처리할 때 유용합니다.

## 문서화
`switch` 문은 지정된 표현식의 값을 평가하고, 해당 값과 일치하는 첫 번째 `case` 블록을 실행합니다. 만약 어떤 `case`에도 일치하지 않는다면, 선택적으로 `default` 블록이 실행됩니다.

### 용도
`switch` 문은 주로 여러 조건을 비교해야 할 때 사용됩니다. 복잡한 조건문을 간결하게 작성할 수 있어 코드의 가독성을 향상시킵니다.

### 사용법
TypeScript에서 `switch` 문의 기본 구문은 다음과 같습니다:

```typescript
switch (expression) {
    case value1:
        // value1과 일치할 때 실행할 코드
        break;
    case value2:
        // value2와 일치할 때 실행할 코드
        break;
    default:
        // 모든 case와 일치하지 않을 때 실행할 코드
        break;
}
```

## 예제
### 기본 사용 예제
```typescript
let fruit: string = "apple";

switch (fruit) {
    case "banana":
        console.log("바나나입니다.");
        break;
    case "apple":
        console.log("사과입니다.");
        break;
    default:
        console.log("모르는 과일입니다.");
}
```
위의 예제에서는 `fruit`이 `"apple"`인 경우 "사과입니다."가 출력됩니다.

### 숫자와 함께 사용하는 예제
```typescript
let number: number = 2;

switch (number) {
    case 1:
        console.log("하나입니다.");
        break;
    case 2:
        console.log("둘입니다.");
        break;
    case 3:
        console.log("셋입니다.");
        break;
    default:
        console.log("그 외의 숫자입니다.");
}
```
이 경우 `number`가 2이므로 "둘입니다."가 출력됩니다.

## 설명
`switch` 문을 사용할 때 주의할 점은 각 `case` 블록 끝에 `break` 문을 반드시 포함해야 한다는 것입니다. `break` 문이 없으면 다음 `case`로 계속 실행되며, 이는 의도하지 않은 결과를 초래할 수 있습니다. 또한, `case` 값은 문자열, 숫자, 또는 타입이 동일한 다른 값들일 수 있으며, 객체나 배열과 같은 복잡한 타입에 대해서는 사용할 수 없습니다.

### 일반적인 실수
1. **break 문 누락**: `break` 문을 빼먹으면 다음 `case`가 실행됩니다.
2. **타입 불일치**: `case`의 값이 `switch` 표현식의 타입과 일치하지 않으면 해당 블록은 실행되지 않습니다.
3. **default 누락**: 모든 경우의 수를 처리하지 않을 경우, `default` 블록을 추가하여 예외 상황을 처리하는 것이 좋습니다.

## 한 줄 요약
TypeScript의 `switch` 문은 다양한 조건을 비교하여 분기 처리를 간결하게 할 수 있는 제어 구조입니다.