<!--
Meta Description: # TypeScript의 export: 모듈 시스템에서의 활용 ## 개요 TypeScript의 `export`는 코드의 모듈화를 가능하게 하는 중요한 기능으로, 다른 파일에서 변수, 함수, 클래스 등을 사용할 수 있도록 내보내는 역할을 합니다. 이를 통해 코드의 재사용...
Meta Keywords: export, 있습니다, myclass, 사용할, named
-->

# TypeScript의 export: 모듈 시스템에서의 활용

## 개요
TypeScript의 `export`는 코드의 모듈화를 가능하게 하는 중요한 기능으로, 다른 파일에서 변수, 함수, 클래스 등을 사용할 수 있도록 내보내는 역할을 합니다. 이를 통해 코드의 재사용성과 유지 보수성을 높일 수 있습니다.

## 문서화

### 목적
`export`는 TypeScript와 JavaScript의 모듈 시스템에서 사용되며, 특정 코드 조각을 외부에서 접근할 수 있도록 합니다. 이를 통해 개발자는 여러 파일 간에 의존성을 관리하고, 구조화된 코드를 작성할 수 있습니다.

### 사용법
`export`는 두 가지 형태로 사용될 수 있습니다:

1. **Named Export**: 특정 이름으로 여러 개의 변수를 내보낼 수 있습니다.
   ```typescript
   export const myVariable = 42;
   export function myFunction() {
       console.log('Hello from myFunction!');
   }
   ```

2. **Default Export**: 모듈당 하나의 기본 내보내기를 할 수 있습니다. 주로 클래스나 주요 함수를 내보낼 때 사용됩니다.
   ```typescript
   export default class MyClass {
       constructor() {
           console.log('MyClass instance created!');
       }
   }
   ```

내보낸 요소는 다른 파일에서 `import` 문을 통해 사용할 수 있습니다.

## 예제

### Named Export 예제
```typescript
// myModule.ts
export const greeting = "안녕하세요";
export function greet() {
    console.log(greeting);
}

// main.ts
import { greeting, greet } from './myModule';
console.log(greeting); // "안녕하세요"
greet(); // "안녕하세요"
```

### Default Export 예제
```typescript
// myClass.ts
export default class MyClass {
    sayHello() {
        console.log('안녕하세요');
    }
}

// main.ts
import MyClass from './myClass';
const myInstance = new MyClass();
myInstance.sayHello(); // "안녕하세요"
```

## 설명
`export`를 사용할 때 몇 가지 유의해야 할 점이 있습니다:

- **이름 충돌**: Named Export를 사용할 때는 동일한 이름의 변수를 내보내면 충돌이 발생할 수 있습니다. 이를 피하기 위해 유일한 이름을 사용하는 것이 좋습니다.
  
- **파일 구조**: 모듈을 설계할 때, 각 파일에 필요한 요소만 내보내는 것이 관리와 유지 보수를 쉽게 합니다. 불필요한 함수를 내보내지 않도록 주의하세요.

- **Default와 Named Export 혼합**: 하나의 모듈에서 Default Export와 Named Export를 혼합하여 사용할 수 있지만, 사용 시 일관성을 유지하는 것이 좋습니다.

## 한 줄 요약
TypeScript의 `export`는 모듈 간 코드 공유를 가능하게 하여 재사용성과 유지 보수성을 향상시키는 기능입니다.