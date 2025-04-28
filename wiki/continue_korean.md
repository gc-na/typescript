<!--
Meta Description: # TypeScript의 continue 문: 제어 흐름을 유연하게 관리하기 ## 개요 TypeScript에서 `continue` 문은 반복문 내에서 사용되며, 현재 반복을 중단하고 다음 반복으로 넘어가는 기능을 제공합니다. 이 문은 코드의 가독성을 높이고 불필요한 코...
Meta Keywords: continue, 반복으로, while, typescript, let
-->

# TypeScript의 continue 문: 제어 흐름을 유연하게 관리하기

## 개요
TypeScript에서 `continue` 문은 반복문 내에서 사용되며, 현재 반복을 중단하고 다음 반복으로 넘어가는 기능을 제공합니다. 이 문은 코드의 가독성을 높이고 불필요한 코드를 줄이는 데 유용합니다.

## 문서화
`continue` 문은 주로 `for`, `while`, `do...while` 루프 내에서 사용됩니다. 이 명령은 특정 조건이 충족될 때 현재 반복을 종료하고 즉시 다음 반복으로 이동합니다. 이를 통해 불필요한 코드 실행을 방지할 수 있으며, 조건에 따라 반복 흐름을 유연하게 제어할 수 있습니다.

### 사용법
`continue` 문은 다음과 같이 사용됩니다:

```typescript
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) {
        continue; // 짝수인 경우 다음 반복으로 넘어감
    }
    console.log(i); // 홀수만 출력됨
}
```

## 예제
1. **기본 예제**: 짝수 건너뛰기
   ```typescript
   for (let i = 0; i < 10; i++) {
       if (i % 2 === 0) {
           continue;
       }
       console.log(i); // 1, 3, 5, 7, 9 출력
   }
   ```

2. **while 루프에서의 사용**:
   ```typescript
   let i = 0;
   while (i < 10) {
       i++;
       if (i % 2 === 0) {
           continue; // 짝수인 경우 다음 반복으로 넘어감
       }
       console.log(i); // 홀수만 출력
   }
   ```

3. **do...while 루프에서의 사용**:
   ```typescript
   let j = 0;
   do {
       j++;
       if (j % 3 === 0) {
           continue; // 3의 배수인 경우 다음 반복으로 넘어감
       }
       console.log(j); // 1, 2, 4, 5, 7, 8, 10 출력
   } while (j < 10);
   ```

## 설명
`continue` 문은 코드 흐름을 제어하는 데 매우 유용하지만, 몇 가지 주의사항이 있습니다:

- **무한 루프 주의**: `continue` 문을 잘못 사용하면 무한 루프에 빠질 수 있습니다. 조건을 적절히 설정하여 이러한 상황을 방지해야 합니다.
- **가독성**: 지나치게 많은 `continue` 문은 코드의 가독성을 떨어뜨릴 수 있으므로, 적절하게 사용하는 것이 중요합니다.
- **중첩 루프의 경우**: 중첩된 반복문에서 `continue` 문을 사용할 경우, 현재 루프에만 적용되므로 주의해야 합니다. 외부 루프에 영향을 주지 않습니다.

## 한 줄 요약
TypeScript의 `continue` 문은 반복문 내에서 조건을 충족할 때 현재 반복을 건너뛰고 다음 반복으로 이동하는 기능을 제공합니다.