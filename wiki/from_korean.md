<!--
Meta Description: # TypeScript에서의 "from": 모듈 가져오기 이해하기 ## 개요 TypeScript에서 "from" 키워드는 모듈을 가져오는 데 사용되는 중요한 구문입니다. ES6 모듈 시스템의 일부로, 특정 모듈에서 기능이나 객체를 가져올 수 있게 해줍니다. ## 문서화...
Meta Keywords: from, math, import, 모듈을, typescript
-->

# TypeScript에서의 "from": 모듈 가져오기 이해하기

## 개요
TypeScript에서 "from" 키워드는 모듈을 가져오는 데 사용되는 중요한 구문입니다. ES6 모듈 시스템의 일부로, 특정 모듈에서 기능이나 객체를 가져올 수 있게 해줍니다.

## 문서화
"from" 키워드는 TypeScript에서 ES6 모듈을 가져오는 데 사용되는 구문으로, 주로 import 구문과 함께 사용됩니다. TypeScript는 JavaScript의 상위 집합으로, ES6 모듈 시스템을 완벽하게 지원합니다. 이를 통해 코드의 재사용성을 높이고, 유지보수를 용이하게 할 수 있습니다.

### 사용 목적
- 다른 파일이나 라이브러리에서 정의된 변수, 함수, 클래스 등을 가져와 사용할 수 있게 해줍니다.
- 코드의 모듈화를 촉진하여 더 나은 구조와 가독성을 제공합니다.

### 사용 방법
TypeScript에서 모듈을 가져오기 위해 다음과 같은 형식을 사용합니다:

```typescript
import { 기능명 } from '모듈명';
```

또는 전체 모듈을 가져올 수도 있습니다:

```typescript
import * as 모듈명 from '모듈명';
```

## 예시
1. 특정 함수 가져오기:
```typescript
// math.ts
export function add(a: number, b: number): number {
    return a + b;
}

// main.ts
import { add } from './math';

console.log(add(2, 3)); // 5
```

2. 전체 모듈 가져오기:
```typescript
// math.ts
export const PI = 3.14;
export function area(radius: number): number {
    return PI * radius * radius;
}

// main.ts
import * as math from './math';

console.log(math.PI); // 3.14
console.log(math.area(5)); // 78.5
```

## 설명
"from" 구문을 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **상대 경로**: 모듈 경로를 지정할 때는 파일의 위치에 따라 상대 경로를 정확히 명시해야 합니다.
- **타입 선언**: TypeScript는 타입을 엄격히 검사하므로, 가져온 모듈의 타입이 올바른지 확인해야 합니다.
- **모듈의 기본 내보내기**: 기본 내보내기를 사용할 경우, 다음과 같은 형식을 사용할 수 있습니다:
  ```typescript
  import DefaultExport from './모듈명';
  ```

## 한 줄 요약
TypeScript에서 "from" 키워드는 모듈을 가져오는 데 사용되는 구문으로, 코드의 재사용성과 모듈화를 촉진합니다.