<!--
Meta Description: # TypeScript에서의 "new" 키워드: 객체 인스턴스화의 기초 ## 개요 TypeScript에서 "new" 키워드는 클래스나 생성자 함수를 사용하여 객체의 새 인스턴스를 생성하는 데 사용됩니다. 이 키워드는 객체 지향 프로그래밍의 중요한 부분으로, 코드의 재사...
Meta Keywords: new, 생성자, 키워드는, 객체를, 있습니다
-->

# TypeScript에서의 "new" 키워드: 객체 인스턴스화의 기초

## 개요
TypeScript에서 "new" 키워드는 클래스나 생성자 함수를 사용하여 객체의 새 인스턴스를 생성하는 데 사용됩니다. 이 키워드는 객체 지향 프로그래밍의 중요한 부분으로, 코드의 재사용성과 조직을 높이는 데 기여합니다.

## 문서화
"new" 키워드는 TypeScript 및 JavaScript에서 객체를 생성하는 데 필수적인 요소입니다. 이를 통해 사용자는 클래스 또는 생성자 함수의 프로토타입을 기반으로 한 새로운 객체를 생성할 수 있습니다.

### 목적
- 새로운 객체를 생성하여 클래스의 인스턴스를 만들 수 있습니다.
- 생성자 함수에 인수를 전달하여 초기화를 수행할 수 있습니다.

### 사용법
"new" 키워드는 다음과 같은 형식으로 사용됩니다:

```typescript
let objectInstance = new ClassName(arguments);
```

여기서 `ClassName`은 사용자 정의 클래스의 이름이며, `arguments`는 생성자 함수에 전달되는 인수입니다.

### 세부사항
- "new" 키워드를 사용하면 자동으로 `this`가 새 객체에 바인딩됩니다.
- 생성자 함수가 명시적으로 반환하는 경우를 제외하고는 항상 새 객체가 반환됩니다.
- 클래스는 JavaScript의 프로토타입 기반 상속을 통해 동작하며, "new" 키워드는 이를 기반으로 한 객체를 생성합니다.

## 예제
### 기본 사용 예제

```typescript
class Person {
    name: string;
    constructor(name: string) {
        this.name = name;
    }
}

let john = new Person("John");
console.log(john.name); // 출력: John
```

### 인수 전달 예제

```typescript
class Car {
    model: string;
    year: number;
    
    constructor(model: string, year: number) {
        this.model = model;
        this.year = year;
    }
}

let myCar = new Car("Toyota", 2020);
console.log(myCar.model); // 출력: Toyota
console.log(myCar.year); // 출력: 2020
```

## 설명
"new" 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **생성자 함수의 반환**: 생성자 함수가 객체를 반환하지 않는 경우, "new" 키워드는 항상 새 객체를 반환합니다. 그러나 생성자 함수가 다른 객체를 반환하면 그 객체가 반환됩니다.
- **ES6 클래스**: TypeScript는 ES6의 클래스 문법을 지원하므로, "new" 키워드는 ES6 클래스에서도 동일한 방식으로 작동합니다.
- **this의 바인딩**: "new" 키워드를 사용하여 생성된 객체는 해당 생성자 함수의 `this`를 가리킵니다. 따라서 생성자 내에서 `this`를 사용하여 객체의 속성을 초기화할 수 있습니다.

## 한 줄 요약
TypeScript에서 "new" 키워드는 클래스의 새 인스턴스를 생성하고, 객체 지향 프로그래밍의 기본 개념을 지원하는 중요한 키워드입니다.