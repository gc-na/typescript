<!--
Meta Description: # TypeScript에서의 require: 모듈 가져오기 방법 ## 개요 `require`는 TypeScript 및 JavaScript에서 외부 모듈을 가져오는 데 사용되는 함수입니다. Node.js 환경에서 주로 사용되며, 코드의 모듈화를 통해 재사용성과 유지보수성...
Meta Keywords: require, 모듈을, 있습니다, 사용할, const
-->

# TypeScript에서의 require: 모듈 가져오기 방법

## 개요
`require`는 TypeScript 및 JavaScript에서 외부 모듈을 가져오는 데 사용되는 함수입니다. Node.js 환경에서 주로 사용되며, 코드의 모듈화를 통해 재사용성과 유지보수성을 향상시키는 데 도움을 줍니다.

## 문서화
### 목적
`require`는 코드에서 다른 파일이나 패키지를 포함하여 사용할 수 있게 해주는 메서드입니다. 이를 통해 개발자는 다양한 기능을 가진 모듈을 손쉽게 가져올 수 있습니다.

### 사용법
`require`는 다음과 같은 형식으로 사용됩니다:

```typescript
const 모듈명 = require('모듈경로');
```

- **모듈명**: 가져온 모듈을 참조할 변수의 이름입니다.
- **모듈경로**: 가져올 모듈의 경로로, 상대경로 또는 절대경로를 사용할 수 있습니다.

TypeScript에서는 JavaScript와 달리 타입을 정의하여 보다 안전한 코드를 작성할 수 있습니다. 이를 위해 타입 정의 파일(`.d.ts`)을 사용하여 모듈에 대한 타입을 명시할 수 있습니다.

### 세부사항
- `require`는 CommonJS 모듈 시스템을 기반으로 하며, Node.js에서 주로 사용됩니다.
- TypeScript의 경우 ES 모듈 방식인 `import` 구문을 사용하는 것이 권장되지만, 기존의 CommonJS 모듈을 사용할 때 `require`를 사용할 수 있습니다.
- 모듈을 동적으로 가져올 수 있는 기능을 제공하여 조건부로 모듈을 로드할 수 있습니다.

## 예제
### 기본 사용 예
```typescript
// math.ts 파일
export function add(a: number, b: number): number {
    return a + b;
}

// main.ts 파일
const math = require('./math');

const sum = math.add(5, 10);
console.log(sum); // 출력: 15
```

### 동적 가져오기 예
```typescript
const moduleName = 'fs';
const fs = require(moduleName);

fs.readFile('./example.txt', 'utf8', (err, data) => {
    if (err) throw err;
    console.log(data);
});
```

## 설명
- `require`를 사용할 때, 모듈 경로를 잘못 지정하면 `MODULE_NOT_FOUND` 오류가 발생합니다. 항상 경로를 정확히 확인해야 합니다.
- TypeScript에서 `require`를 사용할 경우, 모듈의 타입을 정의해야 할 수 있으며, 이를 위해 `@types` 패키지를 설치하여 추가적인 타입 정보를 가져오는 것이 좋습니다.
- `require`는 코드의 실행 시점에 모듈을 가져오므로, 성능에 영향을 미칠 수 있습니다. 필요한 경우에만 사용하도록 합니다.

## 한 줄 요약
TypeScript에서 `require`는 외부 모듈을 가져오는 함수로, Node.js 환경에서 주로 사용되어 코드의 모듈화를 촉진합니다.