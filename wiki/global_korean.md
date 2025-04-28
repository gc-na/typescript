<!--
Meta Description: # TypeScript의 전역(global) 이해하기: 전역 변수 및 타입의 사용 ## 개요 TypeScript에서 "global"은 전역 변수와 타입을 정의하고 사용할 수 있는 기능을 의미합니다. 이는 코드의 모듈성과 재사용성을 높이며, 전역 공간에서 공유되는 타입과...
Meta Keywords: global, 타입을, 사용할, 변수를, declare
-->

# TypeScript의 전역(global) 이해하기: 전역 변수 및 타입의 사용

## 개요
TypeScript에서 "global"은 전역 변수와 타입을 정의하고 사용할 수 있는 기능을 의미합니다. 이는 코드의 모듈성과 재사용성을 높이며, 전역 공간에서 공유되는 타입과 변수에 접근할 수 있도록 합니다.

## 문서화
전역(global) 키워드는 TypeScript에서 전역 변수 및 타입을 정의하는 데 사용됩니다. TypeScript는 기본적으로 모듈 기반으로 설계되었지만, 전역 스코프에서 변수와 타입을 사용하고 싶을 때 global 키워드를 사용할 수 있습니다. 

### 목적
- **전역 변수 및 타입 정의**: 특정 변수를 전역적으로 사용하고 싶을 때 정의합니다.
- **모듈 간 데이터 공유**: 여러 모듈에서 동일한 타입이나 변수에 접근할 수 있게 합니다.

### 사용법
전역 변수를 정의하려면 `declare global` 구문을 사용하여 전역 스코프에 추가할 수 있습니다. 전역 타입은 다른 모듈에서 직접 사용할 수 있습니다.

```typescript
// global.d.ts 파일
declare global {
  var myGlobalVar: string;
  interface MyGlobalInterface {
    prop1: string;
    prop2: number;
  }
}

// 다른 파일에서 사용하기
myGlobalVar = "Hello, World!";
const obj: MyGlobalInterface = {
  prop1: "TypeScript",
  prop2: 42,
};
```

## 예제
1. 전역 변수 사용 예:
```typescript
// global.d.ts
declare global {
  var apiKey: string;
}

// app.ts
apiKey = "12345";
console.log(apiKey); // 출력: "12345"
```

2. 전역 인터페이스 사용 예:
```typescript
// global.d.ts
declare global {
  interface Window {
    myCustomProperty: string;
  }
}

// index.ts
window.myCustomProperty = "Custom Value";
console.log(window.myCustomProperty); // 출력: "Custom Value"
```

## 설명
전역 변수나 타입을 정의할 때 주의할 점은 다음과 같습니다:
- **이름 충돌**: 다른 라이브러리나 코드와 이름이 충돌할 수 있으므로, 고유한 이름을 사용하는 것이 좋습니다.
- **모듈화 고려**: 가능하면 전역 변수를 피하고, 모듈을 사용하는 것이 유지보수성과 가독성을 높입니다.
- **타입 안전성**: 전역 변수를 사용할 경우, 타입 안전성을 보장하기 위해 적절한 타입 정의를 해야 합니다.

## 한 줄 요약
TypeScript에서 "global"은 전역 변수 및 타입을 정의하고 사용하여 모듈 간의 데이터 공유를 가능하게 하는 기능입니다.