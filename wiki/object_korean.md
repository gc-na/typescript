<!--
Meta Description: # TypeScript의 객체(Object) 이해하기: 정의, 사용법 및 예제 ## 개요 TypeScript에서 객체는 속성과 메소드를 포함할 수 있는 데이터 구조로, JavaScript의 객체 개념을 기반으로 하여 정적 타입 검사를 지원합니다. TypeScript는 ...
Meta Keywords: person, number, 있습니다, name, typescript의
-->

# TypeScript의 객체(Object) 이해하기: 정의, 사용법 및 예제

## 개요
TypeScript에서 객체는 속성과 메소드를 포함할 수 있는 데이터 구조로, JavaScript의 객체 개념을 기반으로 하여 정적 타입 검사를 지원합니다. TypeScript는 객체를 정의하고 사용할 수 있는 다양한 방법을 제공합니다.

## 문서화

### 목적
TypeScript의 객체는 데이터와 기능을 결합하여 더 복잡한 구조를 형성하는 데 사용됩니다. 객체는 클래스의 인스턴스, 배열, 함수 등 다양한 형태로 표현될 수 있습니다.

### 사용법
TypeScript에서 객체를 정의하는 방법은 여러 가지가 있습니다. 가장 기본적인 형태는 객체 리터럴을 사용하는 것입니다.

```typescript
let person: { name: string; age: number } = {
    name: "홍길동",
    age: 30
};
```

또한, 인터페이스를 사용하여 객체의 구조를 정의할 수도 있습니다.

```typescript
interface Person {
    name: string;
    age: number;
}

let person: Person = {
    name: "홍길동",
    age: 30
};
```

### 세부사항
TypeScript의 객체는 다음과 같은 특징을 가집니다:
- **정적 타입 검사**: TypeScript는 객체의 타입을 명시함으로써 컴파일 시 타입 오류를 발견할 수 있습니다.
- **선택적 프로퍼티**: 객체의 속성은 선택적으로 정의할 수 있으며, 이를 통해 유연한 구조를 만들 수 있습니다.

```typescript
interface Person {
    name: string;
    age?: number; // 선택적 속성
}

let person: Person = {
    name: "홍길동"
};
```

## 예제

### 기본 사용법
```typescript
let car: { make: string; model: string; year: number } = {
    make: "현대",
    model: "아반떼",
    year: 2021
};

console.log(car.make); // "현대"
```

### 메소드 포함
```typescript
interface Rectangle {
    width: number;
    height: number;
    area: () => number;
}

let rectangle: Rectangle = {
    width: 10,
    height: 20,
    area: function() {
        return this.width * this.height;
    }
};

console.log(rectangle.area()); // 200
```

## 설명
TypeScript의 객체를 사용할 때 주의해야 할 점은 다음과 같습니다:
- **타입 불일치**: 객체의 프로퍼티에 잘못된 타입을 할당하면 컴파일 오류가 발생합니다.
- **선택적 프로퍼티**: 선택적 프로퍼티를 사용할 때, 해당 프로퍼티가 존재하지 않을 수 있으므로 이를 처리하는 로직이 필요합니다.

## 한 줄 요약
TypeScript의 객체는 속성과 메소드를 포함하는 데이터 구조로, 정적 타입 검사를 통해 안전하게 사용할 수 있습니다.