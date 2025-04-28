<!--
Meta Description: # TypeScript에서의 Import: 모듈 가져오기 방법 ## 개요 TypeScript에서 `import` 명령은 다른 모듈의 기능이나 변수를 현재 모듈로 가져오는 데 사용됩니다. 이를 통해 코드의 재사용성을 높이고, 모듈 간의 의존성을 관리할 수 있습니다. ##...
Meta Keywords: import, typescript, from, 있습니다, 사용할
-->

# TypeScript에서의 Import: 모듈 가져오기 방법

## 개요
TypeScript에서 `import` 명령은 다른 모듈의 기능이나 변수를 현재 모듈로 가져오는 데 사용됩니다. 이를 통해 코드의 재사용성을 높이고, 모듈 간의 의존성을 관리할 수 있습니다.

## 문서
`import` 구문은 TypeScript에서 모듈을 불러오는 핵심 요소입니다. JavaScript의 ES6 모듈 시스템을 기반으로 하며, TypeScript에서는 타입 정보를 포함하여 더욱 강력하게 활용할 수 있습니다.

### 목적
- 다른 모듈에서 정의된 변수, 함수, 클래스 등을 현재 파일로 가져와 사용할 수 있도록 합니다.
- 코드의 구조를 명확히 하고, 모듈화를 통해 유지보수를 용이하게 합니다.

### 사용법
`import` 구문은 다음과 같은 형식으로 사용됩니다:

```typescript
import { 이름 } from '모듈경로';
```

또는 기본 내보내기를 사용할 경우:

```typescript
import 이름 from '모듈경로';
```

모듈 전체를 가져오려면:

```typescript
import * as 별칭 from '모듈경로';
```

### 세부 사항
- 모듈 경로는 상대 경로나 절대 경로를 사용할 수 있으며, Node.js 환경에서는 npm 패키지의 이름을 사용할 수 있습니다.
- TypeScript는 .ts, .tsx, .d.ts 파일을 자동으로 인식합니다.
- 여러 개의 항목을 동시에 가져올 수도 있습니다:

```typescript
import { 함수1, 함수2 } from '모듈경로';
```

## 예제
다음은 `import` 구문의 기본 사용 예제입니다.

1. 기본 가져오기:
```typescript
// math.ts
export const add = (a: number, b: number): number => a + b;

// main.ts
import { add } from './math';
console.log(add(2, 3)); // 5
```

2. 기본 내보내기 사용:
```typescript
// user.ts
const userName = 'Alice';
export default userName;

// main.ts
import userName from './user';
console.log(userName); // Alice
```

3. 전체 모듈 가져오기:
```typescript
// utils.ts
export const log = (message: string) => console.log(message);
export const error = (message: string) => console.error(message);

// main.ts
import * as utils from './utils';
utils.log('Hello World'); // Hello World
```

## 설명
`import` 구문을 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **경로 문제**: 모듈 경로를 잘못 지정하면 모듈을 찾지 못하는 오류가 발생합니다. 상대 경로 사용 시 `./` 또는 `../`를 올바르게 사용해야 합니다.
- **타입 오류**: TypeScript는 타입 검사를 수행하므로, 가져온 모듈의 타입과 사용하는 코드의 타입이 일치하지 않으면 오류가 발생합니다.
- **동시 가져오기**: 여러 모듈을 동시에 가져올 경우, 중복된 이름이 있는지 확인해야 합니다. 중복된 이름은 충돌을 일으킬 수 있습니다.

## 한 줄 요약
TypeScript에서 `import`는 다른 모듈의 기능과 변수를 현재 모듈로 가져오는 데 사용되는 구문입니다.