<!--
Meta Description: # TypeScript에서 instanceof를 활용하는 방법 ## 개요 `instanceof`는 TypeScript에서 객체가 특정 클래스의 인스턴스인지 확인하는 데 사용되는 연산자입니다. 이 연산자는 객체의 프로토타입 체인을 검사하여 해당 객체가 주어진 생성자의 프...
Meta Keywords: instanceof, animal, dog, console, log
-->

# TypeScript에서 instanceof를 활용하는 방법

## 개요
`instanceof`는 TypeScript에서 객체가 특정 클래스의 인스턴스인지 확인하는 데 사용되는 연산자입니다. 이 연산자는 객체의 프로토타입 체인을 검사하여 해당 객체가 주어진 생성자의 프로토타입을 포함하고 있는지 판단합니다.

## 문서화

### 목적
`instanceof` 연산자는 런타임에 객체의 타입을 확인할 수 있는 유용한 도구입니다. 이를 통해 코드의 안정성을 높이고, 타입 검사를 보다 명확하게 할 수 있습니다.

### 사용법
`instanceof` 연산자는 다음과 같은 구문으로 사용됩니다:

```typescript
object instanceof constructor
```

- **object**: 확인할 객체입니다.
- **constructor**: 객체가 인스턴스인지 확인할 생성자 함수입니다.

이 표현식은 `object`가 `constructor`의 인스턴스일 경우 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.

### 세부 사항
- `instanceof`는 프로토타입 체인을 기반으로 작동하므로, 상속 관계가 있는 클래스 간의 인스턴스 여부도 확인할 수 있습니다.
- `null`이나 `undefined`에 대해 `instanceof`를 사용하면 항상 `false`를 반환합니다.
- 사용자 정의 타입 가드는 `instanceof`와 함께 사용하여 보다 안전한 타입 검사가 가능합니다.

## 예제

### 기본 사용 예제

```typescript
class Animal {}
class Dog extends Animal {}

const dog = new Dog();

console.log(dog instanceof Dog); // true
console.log(dog instanceof Animal); // true
console.log(dog instanceof Object); // true
console.log(dog instanceof String); // false
```

### 사용자 정의 타입 가드 예제

```typescript
class Cat extends Animal {
    meow() {
        console.log("Meow!");
    }
}

function makeSound(animal: Animal) {
    if (animal instanceof Cat) {
        animal.meow();
    } else {
        console.log("Unknown animal sound");
    }
}

const cat = new Cat();
makeSound(cat); // Meow!
```

## 설명
`instanceof`를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **타입 변경**: 객체의 프로토타입이 변경되면 `instanceof`의 결과도 달라질 수 있으므로, 프로토타입을 직접 수정하는 것은 피해야 합니다.
- **클래스 간 관계**: `instanceof`는 상속 관계를 제대로 반영하므로, 부모 클래스와 자식 클래스의 관계를 이해하는 것이 중요합니다.
- **다양한 환경**: 서로 다른 실행 컨텍스트에서 생성된 객체는 `instanceof`를 사용할 때 예상치 못한 결과를 초래할 수 있습니다. 예를 들어, iframe 간의 객체는 서로 다른 글로벌 객체를 가질 수 있습니다.

## 한 줄 요약
`instanceof`는 TypeScript에서 객체가 특정 클래스의 인스턴스인지 확인하는 연산자로, 코드의 안정성을 높이는 데 유용합니다.