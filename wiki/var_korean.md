<!--
Meta Description: # TypeScript에서의 var: 변수 선언의 기초 ## 개요 TypeScript에서 `var` 키워드는 변수를 선언하는 데 사용됩니다. 이 키워드는 JavaScript에서 유래되었으며, 함수 범위(function scope)를 가지는 변수를 생성합니다. TypeS...
Meta Keywords: var, 변수를, console, log, 키워드는
-->

# TypeScript에서의 var: 변수 선언의 기초

## 개요
TypeScript에서 `var` 키워드는 변수를 선언하는 데 사용됩니다. 이 키워드는 JavaScript에서 유래되었으며, 함수 범위(function scope)를 가지는 변수를 생성합니다. TypeScript는 JavaScript의 상위 집합이기 때문에 `var`는 TypeScript에서도 그대로 사용할 수 있습니다.

## 문서화

### 목적
`var` 키워드는 변수를 선언하기 위해 사용되며, 이 변수가 함수 내에서 유효하도록 합니다. TypeScript는 정적 타입을 지원하므로, `var`로 선언된 변수를 사용할 때 타입을 명시할 수 있습니다.

### 사용법
`var` 키워드는 다음과 같은 형식으로 사용됩니다:

```typescript
var 변수명: 타입 = 초기값;
```

### 세부사항
- `var`로 선언된 변수는 함수 내부에서만 유효하며, 함수 외부에서는 접근할 수 없습니다.
- 같은 스코프 내에서 동일한 이름의 변수를 여러 번 선언할 수 있으며, 마지막으로 선언된 값이 유효합니다.
- `var`는 호이스팅(hoisting) 개념이 적용되어, 선언이 코드의 최상단으로 끌어올려집니다.

## 예제

### 기본 사용 예제

```typescript
function exampleFunction() {
    var x: number = 10;
    console.log(x); // 출력: 10
    
    if (true) {
        var y: number = 20; // 같은 스코프에서 선언
        console.log(y); // 출력: 20
    }

    console.log(y); // 출력: 20 (y는 여전히 유효)
}

exampleFunction();
```

### 호이스팅 예제

```typescript
function hoistingExample() {
    console.log(a); // 출력: undefined
    var a: number = 5;
    console.log(a); // 출력: 5
}

hoistingExample();
```

## 설명
- `var`를 사용할 때의 일반적인 함정 중 하나는 변수의 스코프를 잘못 이해하는 것입니다. `var`는 블록 스코프가 아닌 함수 스코프를 가지므로, 블록 내부에서 선언된 변수도 블록 외부에서 접근할 수 있습니다.
- `var` 대신에 `let`이나 `const`를 사용하는 것이 더 안전하며, 블록 스코프를 제공하여 오류를 줄일 수 있습니다. TypeScript에서는 `let`과 `const` 사용을 권장합니다.

## 한 줄 요약
TypeScript에서 `var`는 함수 범위 변수를 선언하는 데 사용되며, 호이스팅의 영향을 받습니다.