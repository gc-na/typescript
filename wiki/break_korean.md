<!--
Meta Description: # TypeScript의 break 문: 제어 흐름을 중단하는 방법 ## 개요 TypeScript에서 `break` 문은 반복문이나 switch 문 내에서 실행 흐름을 중단하고, 해당 블록의 바깥으로 빠져나갈 수 있도록 해줍니다. 이 문은 프로그램의 흐름을 제어하는 데...
Meta Keywords: break, switch, console, log, let
-->

# TypeScript의 break 문: 제어 흐름을 중단하는 방법

## 개요
TypeScript에서 `break` 문은 반복문이나 switch 문 내에서 실행 흐름을 중단하고, 해당 블록의 바깥으로 빠져나갈 수 있도록 해줍니다. 이 문은 프로그램의 흐름을 제어하는 데 중요한 역할을 하며, 특정 조건을 만족했을 때 반복문을 종료하고자 할 때 주로 사용됩니다.

## 문서화
`break` 문은 TypeScript뿐만 아니라 JavaScript에서도 사용되며, 다음과 같은 목적과 사용법을 가지고 있습니다.

### 목적
- 반복문(for, while 등)이나 switch 문에서 즉시 탈출하고자 할 때 사용합니다.
- 특정 조건을 만족했을 때 더 이상의 반복을 방지하여 프로그램의 효율성을 높입니다.

### 사용법
`break` 문은 반복문이나 switch 문 내부에서 사용되며, 해당 블록 내에서 실행이 종료되고 다음 코드로 이동합니다. 사용법은 다음과 같습니다:

```typescript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break; // i가 5일 때 반복문 종료
    }
    console.log(i);
}
```

위 예제에서는 `i`가 5에 도달했을 때 반복문을 종료합니다.

## 예제
### 기본 사용 예제
```typescript
// 반복문에서 break 사용 예제
for (let i = 0; i < 10; i++) {
    if (i === 3) {
        break; // 3일 때 반복문 종료
    }
    console.log(i); // 0, 1, 2 출력
}

// switch 문에서 break 사용 예제
let fruit = "apple";
switch (fruit) {
    case "banana":
        console.log("바나나입니다");
        break;
    case "apple":
        console.log("사과입니다"); // 출력됨
        break;
    default:
        console.log("알 수 없는 과일입니다");
}
```

## 설명
`break` 문은 매우 유용하지만 몇 가지 주의해야 할 점이 있습니다:

- **중첩 반복문에서의 사용**: 중첩된 반복문에서 `break`를 사용할 경우, 가장 안쪽의 반복문만 종료됩니다. 바깥쪽 반복문을 종료하려면 레이블을 사용해야 합니다.
  
  ```typescript
  outerLoop: for (let i = 0; i < 3; i++) {
      for (let j = 0; j < 3; j++) {
          if (i === 1 && j === 1) {
              break outerLoop; // 바깥쪽 반복문 종료
          }
          console.log(`i: ${i}, j: ${j}`);
      }
  }
  ```

- **switch 문에서의 break**: switch 문에서 `break`가 없으면 다음 case로 계속 진행됩니다. 이를 통해 의도치 않은 결과를 초래할 수 있으므로 항상 필요한 경우 `break`를 추가해야 합니다.

- **가독성**: `break` 문을 남용하면 코드의 가독성이 떨어질 수 있으므로, 명확한 조건 아래에서만 사용하는 것이 좋습니다.

## 한 줄 요약
TypeScript의 `break` 문은 반복문이나 switch 문 내에서 즉시 흐름을 중단할 수 있게 해주는 제어문입니다.