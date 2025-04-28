<!--
Meta Description: # TypeScript의 await: 비동기 프로그래밍을 위한 필수 키워드 ## 개요 `await`는 TypeScript에서 비동기 함수의 실행을 일시 중지하고 Promise가 해결될 때까지 기다리는 데 사용되는 키워드입니다. 이 키워드는 비동기 프로그래밍을 보다 직관...
Meta Keywords: await, const, 비동기, async, promise가
-->

# TypeScript의 await: 비동기 프로그래밍을 위한 필수 키워드

## 개요
`await`는 TypeScript에서 비동기 함수의 실행을 일시 중지하고 Promise가 해결될 때까지 기다리는 데 사용되는 키워드입니다. 이 키워드는 비동기 프로그래밍을 보다 직관적으로 만들고 코드의 가독성을 향상시킵니다.

## 문서화

### 목적
`await`는 비동기 코드에서 Promise의 결과를 쉽게 처리할 수 있도록 돕습니다. 이를 통해 복잡한 콜백 지옥을 피하고, 직관적인 순차적 코드를 작성할 수 있습니다.

### 사용법
`await`는 반드시 `async` 함수 내에서 사용되어야 하며, Promise를 반환하는 표현식 앞에 위치해야 합니다. 예를 들어:

```typescript
async function fetchData() {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    return data;
}
```

이 예제에서 `fetchData` 함수는 비동기적으로 데이터를 가져오고, `await`를 사용하여 응답이 올 때까지 기다립니다.

### 세부사항
- `await`는 Promise가 해결될 때까지 함수의 실행을 중단합니다.
- `await`는 `async` 함수 내에서만 사용할 수 있으며, 그렇지 않은 경우 구문 오류가 발생합니다.
- 여러 개의 `await`를 사용할 경우, 병렬로 수행되지 않고 순차적으로 실행됩니다. 이는 성능에 영향을 줄 수 있습니다.

## 예제

### 기본 사용 예

1. 비동기 데이터 가져오기:

```typescript
async function getUser() {
    const user = await fetch('https://api.example.com/user');
    const userData = await user.json();
    console.log(userData);
}
```

2. 여러 Promise 처리하기:

```typescript
async function fetchMultiple() {
    const [result1, result2] = await Promise.all([
        fetch('https://api.example.com/data1'),
        fetch('https://api.example.com/data2')
    ]);

    const data1 = await result1.json();
    const data2 = await result2.json();
    
    console.log(data1, data2);
}
```

## 설명

### 일반적인 함정 및 주의사항
- `await`를 사용할 때, Promise가 거부(reject)될 경우 예외가 발생합니다. 이를 처리하기 위해서는 `try-catch` 블록을 사용하는 것이 좋습니다.
- `await` 앞에 사용된 Promise가 해결될 때까지 코드 실행이 중단되므로, 불필요한 `await` 사용은 성능 저하를 일으킬 수 있습니다.
- `await`는 명시적으로 반환값을 가지지 않으므로, 반환값을 처리하고자 할 때는 반드시 `return` 문을 사용해야 합니다.

## 한 문장 요약
`await`는 TypeScript에서 비동기 함수의 실행을 일시 중지하고 Promise의 결과를 기다리는 데 사용되는 키워드입니다.