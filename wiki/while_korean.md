<!--
Meta Description: # TypeScript의 while 문: 반복문 사용법과 예제 ## 개요 TypeScript에서 `while` 문은 특정 조건이 참일 때까지 코드 블록을 반복 실행하는 제어 구조입니다. 이 문은 루프를 사용하여 코드의 흐름을 효과적으로 제어할 수 있게 해줍니다. ## ...
Meta Keywords: while, 조건이, userinput, count, typescript
-->

# TypeScript의 while 문: 반복문 사용법과 예제

## 개요
TypeScript에서 `while` 문은 특정 조건이 참일 때까지 코드 블록을 반복 실행하는 제어 구조입니다. 이 문은 루프를 사용하여 코드의 흐름을 효과적으로 제어할 수 있게 해줍니다.

## 문서화
### 목적
`while` 문은 조건이 참인 동안 블록 내의 코드를 반복 실행합니다. 이를 통해 반복적 작업을 수행하거나 대기 상태를 만들 수 있습니다.

### 사용법
TypeScript에서 `while` 문은 다음과 같은 형식을 가집니다:

```typescript
while (조건) {
    // 반복할 코드
}
```

- **조건**: 참(True) 또는 거짓(False)으로 평가되는 표현식으로, 조건이 참인 동안 루프가 계속 실행됩니다.
- **코드 블록**: 조건이 참인 동안 반복 실행될 코드입니다.

### 세부사항
- `while` 문은 조건이 처음 평가될 때만 검사합니다. 따라서 조건이 처음부터 거짓일 경우, 코드 블록은 한 번도 실행되지 않습니다.
- 무한 루프에 주의해야 합니다. 종료 조건이 없거나 잘못 설정된 경우, 프로그램이 종료되지 않을 수 있습니다.

## 예제
### 기본 사용 예제

1. 카운터를 이용한 간단한 루프:

```typescript
let count = 0;

while (count < 5) {
    console.log(count);
    count++;
}
```

이 코드는 0부터 4까지의 숫자를 출력합니다.

2. 사용자 입력을 통한 반복:

```typescript
let userInput: string;
let isInputValid = false;

while (!isInputValid) {
    userInput = prompt("값을 입력하세요:");
    isInputValid = userInput !== null && userInput.trim() !== "";
}
console.log(`입력한 값: ${userInput}`);
```

이 예제는 사용자가 유효한 입력을 할 때까지 반복합니다.

## 설명
- **무한 루프**: 조건이 항상 참인 경우(예: `while (true)`)는 프로그램이 종료되지 않게 됩니다. 이러한 경우 반드시 종료 조건을 설정해야 합니다.
- **조건 검사**: `while` 문은 조건을 반복하기 전에 항상 검사하므로, 초기 조건이 거짓일 경우 코드 블록이 실행되지 않습니다.
- **중첩 while 문**: 여러 개의 `while` 문을 중첩해서 사용할 수 있지만, 이 경우 각 루프의 종료 조건을 명확히 설정해야 합니다.

## 한 줄 요약
TypeScript의 `while` 문은 지정된 조건이 참인 동안 코드 블록을 반복 실행하는 제어 구조입니다.