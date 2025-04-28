<!--
Meta Description: # TypeScript에서 extends 키워드의 사용법 ## 개요 TypeScript에서 `extends` 키워드는 클래스와 인터페이스의 상속(또는 확장)을 정의하는 데 사용됩니다. 이는 코드의 재사용성과 구조화를 개선하며, 객체 지향 프로그래밍의 기본 개념인 상속을...
Meta Keywords: extends, dog, typescript에서, 클래스의, animal
-->

# TypeScript에서 extends 키워드의 사용법

## 개요
TypeScript에서 `extends` 키워드는 클래스와 인터페이스의 상속(또는 확장)을 정의하는 데 사용됩니다. 이는 코드의 재사용성과 구조화를 개선하며, 객체 지향 프로그래밍의 기본 개념인 상속을 TypeScript에서 구현할 수 있게 해줍니다.

## 문서화
`extends` 키워드는 다음과 같은 목적과 사용을 가지고 있습니다:

### 목적
- 클래스 및 인터페이스를 다른 클래스나 인터페이스로부터 파생시켜, 기존의 기능을 확장하거나 재사용할 수 있도록 합니다.

### 사용법
- **클래스 상속**: 한 클래스가 다른 클래스를 상속받을 때 사용합니다.
- **인터페이스 확장**: 한 인터페이스가 다른 인터페이스를 확장할 때 사용합니다.

### 세부 사항
- 클래스가 다른 클래스를 `extends` 할 경우, 부모 클래스의 모든 속성과 메소드를 자식 클래스가 상속받습니다.
- 인터페이스가 다른 인터페이스를 `extends` 할 경우, 부모 인터페이스의 모든 속성을 자식 인터페이스가 상속받습니다.
- `extends`는 제네릭 타입에서도 사용될 수 있어, 특정 타입이 다른 타입을 확장하는지 확인하는 데 사용됩니다.

## 예제
### 클래스 상속 예제
```typescript
class Animal {
    move(distanceInMeters: number) {
        console.log(`Animal moved ${distanceInMeters}m.`);
    }
}

class Dog extends Animal {
    bark() {
        console.log("Woof! Woof!");
    }
}

const dog = new Dog();
dog.move(10); // Animal moved 10m.
dog.bark();   // Woof! Woof!
```

### 인터페이스 확장 예제
```typescript
interface Person {
    name: string;
    age: number;
}

interface Employee extends Person {
    employeeId: number;
}

const employee: Employee = {
    name: "John Doe",
    age: 30,
    employeeId: 12345
};
```

## 설명
`extends` 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **다중 상속**: TypeScript는 클래스의 다중 상속을 지원하지 않습니다. 그러나 인터페이스는 여러 개를 `extends` 할 수 있습니다.
- **초기화**: 부모 클래스의 생성자를 호출하려면 자식 클래스에서 `super()`를 호출해야 합니다.
- **접근 수정자**: 자식 클래스에서는 부모 클래스의 `public` 및 `protected` 속성에 접근할 수 있지만, `private` 속성은 접근할 수 없습니다.

## 한 줄 요약
TypeScript에서 `extends`는 클래스와 인터페이스의 상속을 통해 코드의 재사용성과 구조화를 가능하게 해주는 키워드입니다.