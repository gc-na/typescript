<!--
Meta Description: # TypeScript의 생성자(constructor) 사용법 및 개념 ## 개요 TypeScript에서 생성자(constructor)는 클래스의 인스턴스가 생성될 때 호출되는 특별한 메서드입니다. 객체 지향 프로그래밍에서 클래스의 초기화 방법을 제공하며, 인스턴스가 ...
Meta Keywords: constructor, name, string, 클래스의, 생성자는
-->

# TypeScript의 생성자(constructor) 사용법 및 개념

## 개요
TypeScript에서 생성자(constructor)는 클래스의 인스턴스가 생성될 때 호출되는 특별한 메서드입니다. 객체 지향 프로그래밍에서 클래스의 초기화 방법을 제공하며, 인스턴스가 필요한 초기 상태를 설정하는 데 사용됩니다.

## 문서화
생성자는 클래스 정의 내에서 `constructor` 키워드를 사용하여 정의합니다. 생성자는 인스턴스가 생성될 때 자동으로 호출되며, 주로 객체의 속성을 초기화하고, 필요한 경우 매개변수를 통해 값을 전달받습니다.

### 목적
생성자의 주요 목적은 다음과 같습니다:
- 클래스의 인스턴스가 생성될 때 필요한 초기 설정을 수행합니다.
- 매개변수를 통해 클래스의 속성을 초기화할 수 있습니다.

### 사용법
생성자는 다음과 같은 형식으로 선언됩니다:

```typescript
class ClassName {
    constructor(parameters) {
        // 초기화 코드
    }
}
```

## 예제
다음은 TypeScript에서 생성자를 사용한 기본적인 예제입니다.

```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    introduce(): string {
        return `안녕하세요, 제 이름은 ${this.name}이고, 나이는 ${this.age}세입니다.`;
    }
}

const person1 = new Person("홍길동", 30);
console.log(person1.introduce()); // 출력: 안녕하세요, 제 이름은 홍길동이고, 나이는 30세입니다.
```

## 설명
생성자를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

1. **매개변수 접근 제한자**: TypeScript에서는 생성자의 매개변수를 클래스의 속성으로 자동으로 초기화할 수 있도록 하는 접근 제한자(public, private, protected)를 사용할 수 있습니다.

   ```typescript
   class User {
       constructor(public username: string, private password: string) {}
   }
   ```

2. **기본 생성자**: 매개변수가 없는 기본 생성자는 TypeScript에서 자동으로 제공됩니다. 하지만 매개변수가 있는 생성자를 정의하면 기본 생성자는 제공되지 않습니다.

3. **상속**: 부모 클래스의 생성자를 호출하려면 `super()`를 사용해야 합니다.

   ```typescript
   class Animal {
       constructor(public name: string) {}
   }

   class Dog extends Animal {
       constructor(name: string, public breed: string) {
           super(name);
       }
   }
   ```

4. **생성자 내에서 초기화**: 생성자 내에서 직접 속성의 값을 초기화하는 것이 일반적입니다. 그러나 초기화가 복잡할 경우 별도의 메서드를 사용하는 것이 좋습니다.

## 한 줄 요약
TypeScript에서 생성자는 클래스의 인스턴스가 생성될 때 호출되어 객체의 속성을 초기화하는 특별한 메서드입니다.