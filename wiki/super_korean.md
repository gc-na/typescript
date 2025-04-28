<!--
Meta Description: # TypeScript에서 "super" 키워드 이해하기 ## 개요 TypeScript에서 `super` 키워드는 클래스 상속에서 부모 클래스의 메서드와 속성에 접근할 때 사용됩니다. 이 키워드는 객체 지향 프로그래밍의 기본 개념인 상속을 지원하며, 코드의 재사용성과 ...
Meta Keywords: super, 클래스의, 있습니다, 생성자, name
-->

# TypeScript에서 "super" 키워드 이해하기

## 개요
TypeScript에서 `super` 키워드는 클래스 상속에서 부모 클래스의 메서드와 속성에 접근할 때 사용됩니다. 이 키워드는 객체 지향 프로그래밍의 기본 개념인 상속을 지원하며, 코드의 재사용성과 구조적 유지를 용이하게 합니다.

## 문서화
`super` 키워드는 하위 클래스에서 부모 클래스의 메서드나 생성자를 호출할 때 사용됩니다. TypeScript는 JavaScript의 상속 구조를 기반으로 하므로, `super`는 타입 안정성을 제공하면서도 효율적인 상속을 가능하게 합니다.

### 목적
- 부모 클래스의 메서드 호출: `super`를 사용하면 부모 클래스의 메서드를 손쉽게 호출할 수 있습니다.
- 부모 클래스의 생성자 호출: 하위 클래스의 생성자에서 `super()`를 호출하여 부모 클래스의 초기화 작업을 수행할 수 있습니다.

### 사용법
- `super()`는 생성자 내에서만 사용할 수 있으며, 부모 클래스의 생성자를 호출합니다.
- `super.methodName()` 형식으로 부모 클래스의 메서드를 호출할 수 있습니다.

## 예제
### 기본적인 사용 예
```typescript
class Animal {
    constructor(public name: string) {}

    makeSound() {
        console.log(`${this.name} makes a sound.`);
    }
}

class Dog extends Animal {
    constructor(name: string) {
        super(name); // 부모 클래스의 생성자 호출
    }

    makeSound() {
        super.makeSound(); // 부모 클래스의 메서드 호출
        console.log(`${this.name} barks.`);
    }
}

const myDog = new Dog("Buddy");
myDog.makeSound();
// 출력:
// Buddy makes a sound.
// Buddy barks.
```

## 설명
`super` 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

1. **상속 관계**: `super`는 반드시 상속 관계에서만 사용해야 하며, 클래스 내에서만 의미가 있습니다.
2. **생성자 초기화**: 하위 클래스의 생성자에서 `super()`를 호출하기 전에 `this`를 사용할 수 없습니다. 따라서 생성자 내에서 `this`를 참조하기 전에 반드시 `super()`를 호출해야 합니다.
3. **메서드 오버라이딩**: 상속된 메서드를 오버라이드할 때 `super.methodName()`을 호출하여 부모 클래스의 기능을 추가하거나 확장할 수 있습니다.

## 한 줄 요약
TypeScript에서 `super` 키워드는 클래스 상속을 통해 부모 클래스의 메서드와 생성자에 접근하는 데 사용됩니다.