<!--
Meta Description: # TypeScript의 "this" 키워드 이해하기: 컨텍스트와 활용 ## 개요 TypeScript에서 "this"는 객체의 메서드가 호출될 때 그 메서드가 속한 객체를 참조하는 중요한 키워드입니다. "this"는 JavaScript의 기본 개념을 따르며, TypeS...
Meta Keywords: 메서드가, name, model, 화살표, person
-->

# TypeScript의 "this" 키워드 이해하기: 컨텍스트와 활용

## 개요
TypeScript에서 "this"는 객체의 메서드가 호출될 때 그 메서드가 속한 객체를 참조하는 중요한 키워드입니다. "this"는 JavaScript의 기본 개념을 따르며, TypeScript에서도 동일하게 작동합니다.

## 문서화
### 목적
"this" 키워드는 메서드가 어떤 객체에 의해 호출되었는지를 나타내며, 해당 객체의 속성과 메서드에 접근할 수 있도록 도와줍니다. TypeScript에서는 "this"를 사용하여 코드의 가독성을 높이고, 타입 안전성을 유지할 수 있습니다.

### 사용법
"this"는 클래스 메서드나 객체 메서드 내에서 주로 사용됩니다. "this"의 타입은 해당 메서드가 호출되는 컨텍스트에 따라 결정됩니다. TypeScript에서는 "this"의 타입을 명시적으로 지정할 수 있어, 더욱 안전한 코드를 작성할 수 있습니다.

```typescript
class Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    greet() {
        console.log(`안녕하세요, 제 이름은 ${this.name}입니다.`);
    }
}

const person = new Person("홍길동");
person.greet(); // 출력: 안녕하세요, 제 이름은 홍길동입니다.
```

## 예제
다음은 "this" 키워드의 기본 사용 예시입니다.

### 클래스 메서드에서의 사용
```typescript
class Car {
    model: string;

    constructor(model: string) {
        this.model = model;
    }

    displayModel() {
        console.log(`차량 모델: ${this.model}`);
    }
}

const myCar = new Car("소나타");
myCar.displayModel(); // 출력: 차량 모델: 소나타
```

### 화살표 함수와의 조합
화살표 함수는 "this"의 컨텍스트를 lexically 바인딩하므로, 전통적인 함수와는 다르게 동작합니다.
```typescript
class Counter {
    count: number;

    constructor() {
        this.count = 0;
    }

    increment() {
        setTimeout(() => {
            this.count++;
            console.log(this.count);
        }, 1000);
    }
}

const counter = new Counter();
counter.increment(); // 1초 후에 1 출력
```

## 설명
"this" 키워드를 사용할 때 주의해야 할 점은 "this"의 바인딩이 함수의 호출 방식에 따라 달라진다는 것입니다. 특히, 전통적인 함수와 화살표 함수는 "this"를 다르게 처리합니다. 전통적인 함수에서는 "this"가 호출된 객체를 참조하지만, 화살표 함수에서는 "this"를 선언된 위치에서 가져옵니다.

또한, 메서드가 객체의 속성으로 할당되거나 콜백으로 사용될 때 "this"가 예기치 않게 동작할 수 있습니다. 이를 해결하기 위해 `.bind(this)`를 사용하거나, 화살표 함수를 사용하는 것이 좋습니다.

## 한 줄 요약
TypeScript의 "this" 키워드는 메서드가 호출된 객체를 참조하며, 컨텍스트에 따라 동적으로 바인딩됩니다.