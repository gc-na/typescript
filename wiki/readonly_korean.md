<!--
Meta Description: # TypeScript의 readonly 속성: 안전한 데이터 구조를 위한 필수 기능 ## 개요 TypeScript의 `readonly` 속성은 객체의 속성을 읽기 전용으로 설정하여, 객체의 불변성을 유지하는 데 사용됩니다. 이는 코드의 안전성을 높이고, 의도하지 않은...
Meta Keywords: readonly, 속성은, 객체의, 있습니다, number
-->

# TypeScript의 readonly 속성: 안전한 데이터 구조를 위한 필수 기능

## 개요
TypeScript의 `readonly` 속성은 객체의 속성을 읽기 전용으로 설정하여, 객체의 불변성을 유지하는 데 사용됩니다. 이는 코드의 안전성을 높이고, 의도하지 않은 변경을 방지하는 데 도움을 줍니다.

## 문서화

### 목적
`readonly`는 객체의 속성이 초기화 이후 변경될 수 없도록 보호합니다. 이 속성을 사용하면, 다양한 상황에서 데이터의 일관성을 유지할 수 있습니다. 

### 사용법
`readonly`는 클래스, 인터페이스, 배열의 요소 등에 적용할 수 있습니다. 다음은 기본적인 사용 방법입니다:

- 클래스 속성에 사용
- 인터페이스 속성에 사용
- 배열 요소에 사용

### 세부사항
- `readonly`를 지정한 속성은 객체를 생성한 후에 값을 변경할 수 없습니다.
- `readonly` 속성은 객체의 타입을 정의할 때 유용하게 사용됩니다.
- 배열에서 `readonly`를 사용하면, 배열의 요소가 읽기 전용이 됩니다.

## 예제

### 클래스에서의 사용
```typescript
class User {
    readonly id: number;
    readonly name: string;

    constructor(id: number, name: string) {
        this.id = id;
        this.name = name;
    }
}

const user = new User(1, "Alice");
// user.id = 2; // 오류: 'id'는 읽기 전용입니다.
```

### 인터페이스에서의 사용
```typescript
interface Point {
    readonly x: number;
    readonly y: number;
}

const point: Point = { x: 10, y: 20 };
// point.x = 15; // 오류: 'x'는 읽기 전용입니다.
```

### 배열에서의 사용
```typescript
const numbers: readonly number[] = [1, 2, 3];
// numbers.push(4); // 오류: 'readonly' 배열에 요소를 추가할 수 없습니다.
```

## 설명
`readonly` 속성을 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- `readonly`는 얕은 복사(shallow copy)를 적용합니다. 객체 내부의 속성이나 배열 요소가 객체일 경우, 해당 속성의 내용은 변경 가능하다는 점을 기억해야 합니다.
- `readonly` 속성은 기본적으로 `public`으로 설정됩니다. 접근 제어자를 별도로 지정하지 않으면 외부에서 접근할 수 있습니다.
- `readonly` 속성이 있는 객체를 다른 객체에 할당할 때, 타입이 호환되지 않으면 오류가 발생할 수 있습니다.

## 한 줄 요약
TypeScript의 `readonly` 속성은 객체의 불변성을 보장하여 의도치 않은 데이터 변경을 방지하는 데 필수적인 기능입니다.