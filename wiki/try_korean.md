<!--
Meta Description: # TypeScript의 try 문: 오류 처리의 기초 ## 개요 TypeScript에서 `try` 문은 오류를 처리하는 기본적인 방법으로, 코드 실행 중 발생할 수 있는 예외를 관리하여 프로그램의 안정성을 높이는 데 사용됩니다. ## 문서화 `try` 문은 JavaS...
Meta Keywords: try, catch, error, 있습니다, finally
-->

# TypeScript의 try 문: 오류 처리의 기초

## 개요
TypeScript에서 `try` 문은 오류를 처리하는 기본적인 방법으로, 코드 실행 중 발생할 수 있는 예외를 관리하여 프로그램의 안정성을 높이는 데 사용됩니다.

## 문서화
`try` 문은 JavaScript와 TypeScript에서 예외를 처리하기 위한 구조입니다. 오류가 발생할 가능성이 있는 코드를 `try` 블록 내에 작성하고, 오류 발생 시 이를 처리하기 위한 코드를 `catch` 블록에 작성합니다. 이를 통해 프로그램의 흐름을 중단하지 않고, 예외를 우아하게 처리할 수 있습니다.

### 사용법
기본적인 `try-catch` 문법은 다음과 같습니다:

```typescript
try {
    // 오류가 발생할 수 있는 코드
} catch (error) {
    // 오류 처리 코드
}
```

### 세부사항
- `try` 블록: 오류가 발생할 수 있는 코드를 포함합니다. 이 블록 내에서 오류가 발생하면, 즉시 `catch` 블록으로 제어가 넘어갑니다.
- `catch` 블록: 발생한 오류를 처리하는 코드가 위치합니다. 이 블록에서는 오류 정보를 사용할 수 있으며, 이를 통해 사용자에게 오류 메시지를 제공하거나 로그를 기록할 수 있습니다.
- 선택적으로 `finally` 블록을 추가하여, 오류 발생 여부와 관계없이 항상 실행되는 코드를 작성할 수 있습니다.

```typescript
try {
    // 잠재적인 오류 발생 코드
} catch (error) {
    // 오류 처리
} finally {
    // 항상 실행되는 코드
}
```

## 예제
### 기본 사용 예
```typescript
function divide(a: number, b: number): number {
    try {
        return a / b;
    } catch (error) {
        console.error("오류 발생:", error);
        return 0; // 기본값 반환
    }
}

console.log(divide(10, 0)); // 0
```

### `finally` 블록 사용 예
```typescript
function readFile(filePath: string): string {
    let fileContent: string;

    try {
        // 파일 읽기 시도
        fileContent = "파일 내용"; // 가정
    } catch (error) {
        console.error("파일 읽기 오류:", error);
        return "오류 발생";
    } finally {
        console.log("파일 읽기 시도 완료");
    }

    return fileContent;
}
```

## 설명
`try` 문을 사용할 때 주의해야 할 점은 다음과 같습니다:
- `try` 블록 내에서 발생하는 모든 종류의 오류를 처리할 수 있지만, 비동기 코드에서 발생하는 오류는 별도로 처리해야 합니다. 비동기 작업에서는 `async/await` 패턴과 함께 `try-catch`를 사용하는 것이 일반적입니다.
- `catch` 블록에서 오류를 처리할 때, 적절한 오류 메시지를 제공하는 것이 중요합니다. 이를 통해 디버깅이 용이해집니다.
- `finally` 블록은 자원 해제와 같은 클린업 작업에 유용하게 사용할 수 있습니다. 예를 들어, 파일 핸들러나 데이터베이스 연결을 종료하는 데 사용될 수 있습니다.

## 한 줄 요약
TypeScript에서 `try` 문은 예외 처리의 핵심 요소로, 오류 발생 시 프로그램의 흐름을 안전하게 관리합니다.