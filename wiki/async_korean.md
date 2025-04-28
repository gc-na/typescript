<!--
Meta Description: # TypeScript의 async: 비동기 프로그래밍의 핵심 ## 개요 TypeScript에서 `async` 키워드는 비동기 함수를 정의하는 데 사용되며, 프로미스(promise)를 보다 쉽게 사용할 수 있도록 도와줍니다. 이 키워드를 통해 비동기 작업을 동기적으로 ...
Meta Keywords: async, await, error, 비동기, data
-->

# TypeScript의 async: 비동기 프로그래밍의 핵심

## 개요
TypeScript에서 `async` 키워드는 비동기 함수를 정의하는 데 사용되며, 프로미스(promise)를 보다 쉽게 사용할 수 있도록 도와줍니다. 이 키워드를 통해 비동기 작업을 동기적으로 작성할 수 있으며, 가독성을 높이고 오류를 줄이는 데 기여합니다.

## 문서화
### 목적
`async` 함수는 항상 프로미스를 반환합니다. 만약 함수 내에서 다른 값을 반환하면, TypeScript는 자동으로 해당 값을 프로미스로 래핑(wrapping)합니다. 이 기능은 비동기 프로그래밍의 복잡성을 줄이고, 코드의 흐름을 더 명확하게 만들어 줍니다.

### 사용법
`async` 키워드는 함수 선언 앞에 붙여서 사용합니다. 다음은 기본적인 문법 구조입니다.

```typescript
async function 함수명(매개변수들) {
    // 비동기 작업 수행
}
```

이 함수 내에서는 `await` 키워드를 사용하여 프로미스가 해결될 때까지 기다릴 수 있습니다.

### 세부 사항
- `async` 함수는 항상 프로미스를 반환하므로, `.then()` 또는 `await`를 사용하여 결과를 처리할 수 있습니다.
- `await` 키워드는 `async` 함수 내에서만 사용할 수 있으며, 프로미스가 해결될 때까지 코드 실행을 일시 중지합니다.
- 에러 처리는 `try...catch` 블록을 사용하여 수행할 수 있습니다.

## 예제
### 기본 사용 예
아래는 `async`와 `await`를 사용하는 간단한 예제입니다.

```typescript
async function fetchData(url: string): Promise<any> {
    const response = await fetch(url); // 프로미스가 해결될 때까지 대기
    const data = await response.json(); // JSON 데이터로 변환
    return data; // 데이터 반환
}

fetchData('https://api.example.com/data')
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```

### 에러 처리 예
에러 처리를 포함한 예제입니다.

```typescript
async function fetchDataWithErrorHandling(url: string): Promise<any> {
    try {
        const response = await fetch(url);
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Fetch error:', error);
        throw error; // 에러를 다시 던짐
    }
}
```

## 설명
- `async` 함수는 항상 프로미스를 반환하기 때문에, 이를 사용하는 개발자는 함수의 비동기성을 쉽게 이해할 수 있습니다.
- `await`를 사용할 때, 해당 프로미스가 해결될 때까지 함수 실행이 중단되므로, 비동기 코드가 동기적으로 보이게 됩니다.
- 하지만 `await` 사용 시, 프로미스가 거부(rejected)될 경우 에러가 발생할 수 있으므로 적절한 에러 처리가 필요합니다.

## 한 줄 요약
TypeScript의 `async` 키워드는 비동기 함수를 정의하고, `await`를 통해 프로미스를 간편하게 처리할 수 있는 기능을 제공합니다.