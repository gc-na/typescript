<!--
Meta Description: # TypeScript 모듈: 효율적인 코드 관리 및 재사용 ## 개요 TypeScript 모듈은 코드의 구조화와 재사용성을 높이기 위해 사용되는 기능입니다. 모듈을 통해 개발자는 코드의 각 부분을 독립적인 단위로 나누고, 이를 다른 파일이나 프로젝트에서 쉽게 사용할 ...
Meta Keywords: typescript, 있습니다, 코드의, export, import
-->

# TypeScript 모듈: 효율적인 코드 관리 및 재사용

## 개요
TypeScript 모듈은 코드의 구조화와 재사용성을 높이기 위해 사용되는 기능입니다. 모듈을 통해 개발자는 코드의 각 부분을 독립적인 단위로 나누고, 이를 다른 파일이나 프로젝트에서 쉽게 사용할 수 있습니다. TypeScript의 모듈 시스템은 ES6(ECMAScript 2015) 모듈 시스템을 기반으로 하며, 이를 통해 의존성을 관리하고 코드의 가독성을 향상시킬 수 있습니다.

## 문서화

### 목적
TypeScript 모듈은 코드의 모듈화를 통해 복잡성을 줄이고, 코드의 재사용성을 높이기 위해 설계되었습니다. 모듈을 사용함으로써, 개발자는 특정 기능을 별도의 파일에 정의하고, 필요한 곳에서 이를 가져와 사용할 수 있습니다.

### 사용법
TypeScript에서 모듈을 사용하려면 두 가지 주요 구성 요소가 있습니다: `export`와 `import`.

- **export**: 모듈 내에서 다른 파일에서 사용할 수 있도록 특정 변수, 함수 또는 클래스를 내보내기 위해 사용됩니다.
- **import**: 다른 모듈에서 내보낸 요소를 현재 모듈로 가져오기 위해 사용됩니다.

### 세부사항
TypeScript 모듈은 기본적으로 다음과 같은 방식으로 구성됩니다:

1. **모듈 정의**: 모듈은 일반적으로 하나의 파일에 정의됩니다. 파일 이름은 보통 `.ts` 확장자를 가집니다.
2. **내보내기**: `export` 키워드를 사용하여 내보낼 요소를 지정합니다.
3. **가져오기**: `import` 키워드를 사용하여 다른 모듈에서 내보낸 요소를 가져옵니다.

```typescript
// 파일: math.ts
export function add(a: number, b: number): number {
    return a + b;
}

// 파일: app.ts
import { add } from './math';

console.log(add(2, 3)); // 출력: 5
```

## 예제

### 기본 사용 예
모듈을 사용하여 간단한 수학 함수를 정의하고 사용하는 방법을 보여줍니다.

**math.ts**
```typescript
export function multiply(a: number, b: number): number {
    return a * b;
}
```

**app.ts**
```typescript
import { multiply } from './math';

console.log(multiply(4, 5)); // 출력: 20
```

### 기본 클래스 모듈
클래스를 모듈로 정의하고 사용하는 예제입니다.

**Person.ts**
```typescript
export class Person {
    constructor(public name: string) {}
    greet() {
        return `안녕하세요, ${this.name}님!`;
    }
}
```

**app.ts**
```typescript
import { Person } from './Person';

const person = new Person('홍길동');
console.log(person.greet()); // 출력: 안녕하세요, 홍길동님!
```

## 설명
TypeScript 모듈을 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **순환 의존성**: 두 모듈이 서로를 참조할 경우 순환 의존성이 발생할 수 있습니다. 이는 프로그램이 올바르게 작동하지 않게 만들 수 있습니다.
- **모듈 로딩**: TypeScript는 기본적으로 CommonJS 또는 ES6 모듈 형식을 지원합니다. 이를 통해 Node.js 및 브라우저 환경에서 모듈을 사용할 수 있습니다.
- **타입 정의**: 모듈에서 내보낸 요소에 대해 타입을 명시적으로 정의하면, 코드의 가독성과 유지보수성이 향상됩니다.

## 한 줄 요약
TypeScript 모듈은 코드의 구조화와 재사용성을 높이는 강력한 도구로, `export`와 `import` 키워드를 통해 독립적인 코드 단위를 정의하고 사용할 수 있게 해줍니다.