<!--
Meta Description: # TypeScript의 추상 클래스(abstract) 완벽 가이드 ## 개요 TypeScript의 추상 클래스는 객체 지향 프로그래밍에서 코드 재사용성을 높이고, 기본 클래스에서 공통적인 속성과 메서드를 정의하여 하위 클래스에서 이를 상속받아 사용할 수 있도록 하는 ...
Meta Keywords: abstract, car, 클래스를, class, void
-->

# TypeScript의 추상 클래스(abstract) 완벽 가이드

## 개요
TypeScript의 추상 클래스는 객체 지향 프로그래밍에서 코드 재사용성을 높이고, 기본 클래스에서 공통적인 속성과 메서드를 정의하여 하위 클래스에서 이를 상속받아 사용할 수 있도록 하는 기능입니다.

## 문서화

### 목적
추상 클래스는 인스턴스를 생성할 수 없는 클래스입니다. 대신, 다른 클래스들이 이 클래스를 상속받아 구체적인 구현을 제공하도록 강제합니다. 이를 통해 코드의 일관성을 유지하고, 공통된 인터페이스를 제공할 수 있습니다.

### 사용법
`abstract` 키워드를 사용하여 클래스를 정의합니다. 추상 클래스 내에는 추상 메서드와 일반 메서드를 포함할 수 있으며, 추상 메서드는 반드시 하위 클래스에서 구현되어야 합니다.

```typescript
abstract class Animal {
    abstract makeSound(): void; // 추상 메서드

    move(): void {
        console.log("Animal moves");
    }
}

class Dog extends Animal {
    makeSound(): void {
        console.log("Woof!");
    }
}

const dog = new Dog();
dog.makeSound(); // "Woof!"
dog.move();      // "Animal moves"
```

## 예제
아래는 추상 클래스를 이용한 간단한 예제입니다.

### 예제 1: 기본적인 추상 클래스
```typescript
abstract class Shape {
    abstract area(): number; // 추상 메서드
}

class Circle extends Shape {
    constructor(private radius: number) {
        super();
    }

    area(): number {
        return Math.PI * this.radius * this.radius; // 원의 넓이 계산
    }
}

const circle = new Circle(5);
console.log(circle.area()); // 78.53981633974483
```

### 예제 2: 일반 메서드와 추상 메서드 혼합
```typescript
abstract class Vehicle {
    abstract start(): void; // 추상 메서드

    honk(): void {
        console.log("Beep!");
    }
}

class Car extends Vehicle {
    start(): void {
        console.log("Car started.");
    }
}

const car = new Car();
car.start(); // "Car started."
car.honk();  // "Beep!"
```

## 설명
추상 클래스를 사용할 때 주의해야 할 몇 가지 사항이 있습니다.

1. **인스턴스화 불가**: 추상 클래스로 직접 인스턴스를 생성할 수 없습니다. 항상 하위 클래스를 통해 인스턴스를 생성해야 합니다.
  
2. **추상 메서드 구현 필수**: 하위 클래스에서 추상 메서드를 반드시 구현해야 하며, 이를 구현하지 않을 경우 컴파일 오류가 발생합니다.

3. **다중 상속 불가**: TypeScript는 클래스의 다중 상속을 지원하지 않지만, 인터페이스를 통해 다중 계약을 구현할 수 있습니다.

4. **일관성 유지**: 추상 클래스를 사용하면 코드의 일관성을 유지하고, 코드의 가독성을 높일 수 있습니다.

## 한 줄 요약
TypeScript의 추상 클래스는 하위 클래스에서 구현하도록 강제하는 메서드를 포함하여 코드의 재사용성과 일관성을 높이는 데 유용합니다.