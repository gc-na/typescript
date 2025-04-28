<!--
Meta Description: # TypeScript의 "default": 기본 내보내기 및 가져오기 ## 개요 TypeScript에서 "default"는 모듈 시스템의 일부로, 기본 내보내기(default export) 및 기본 가져오기(default import)를 통해 코드의 재사용성을 높이고...
Meta Keywords: default, typescript, example, 내보내기, 가져오기
-->

# TypeScript의 "default": 기본 내보내기 및 가져오기

## 개요
TypeScript에서 "default"는 모듈 시스템의 일부로, 기본 내보내기(default export) 및 기본 가져오기(default import)를 통해 코드의 재사용성을 높이고 모듈화된 구조를 지원합니다.

## 문서화

### 목적
"기본 내보내기"는 모듈에서 하나의 값을 기본으로 내보내고, "기본 가져오기"는 해당 모듈을 사용할 때 그 값을 간편하게 가져오는 방법을 제공합니다. 이를 통해 코드의 가독성을 높이고, 다른 파일에서 쉽게 사용할 수 있습니다.

### 사용법
기본 내보내기를 사용하려면 `export default` 키워드를 사용하여 함수를, 클래스 또는 변수를 내보냅니다. 가져올 때는 중괄호 없이 해당 모듈의 이름을 사용하여 가져옵니다.

```typescript
// example.ts
class Example {
    sayHello() {
        console.log("Hello, TypeScript!");
    }
}

export default Example;
```

```typescript
// main.ts
import Example from './example';

const exampleInstance = new Example();
exampleInstance.sayHello(); // "Hello, TypeScript!" 출력
```

## 예제

### 기본 내보내기
```typescript
// math.ts
const add = (a: number, b: number): number => a + b;
export default add;
```

### 기본 가져오기
```typescript
// main.ts
import add from './math';

console.log(add(2, 3)); // 5 출력
```

## 설명
기본 내보내기를 사용할 때 주의해야 할 점은 각 모듈에서 오직 하나의 기본 내보내기만 가능하다는 것입니다. 여러 개의 기본 내보내기를 시도하면 오류가 발생합니다. 또한, 기본 가져오기에서는 중괄호를 사용하지 않아야 하며, 모듈 이름을 그대로 사용해야 합니다. 이러한 규칙을 준수하지 않으면 불필요한 오류가 발생할 수 있습니다.

### 일반적인 함정
- **여러 기본 내보내기**: 한 파일에서 여러 개의 `export default`를 정의하면 오류가 발생합니다.
- **가져오기 구문**: 기본 가져오기에서는 중괄호를 사용하지 않도록 주의해야 합니다.
- **타입스크립트와 자바스크립트의 차이**: TypeScript의 모듈 시스템은 ES6 모듈을 기반으로 하며, 이에 따라 JS 파일에서도 동일하게 작동합니다.

## 한 줄 요약
TypeScript의 "default"는 모듈에서 하나의 기본 값을 내보내고 간편하게 가져오는 기능으로, 코드 모듈화에 중요한 역할을 합니다.