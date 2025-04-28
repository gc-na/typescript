<!--
Meta Description: # TypeScript에서 protected 접근 제어자 이해하기 ## 개요 TypeScript의 `protected` 접근 제어자는 클래스 멤버(속성 및 메서드)에 대한 접근을 제어하는 데 사용됩니다. 이 키워드는 해당 멤버가 클래스 내부 및 그 클래스를 상속한 자식...
Meta Keywords: protected, string, member, lastname, class
-->

# TypeScript에서 protected 접근 제어자 이해하기

## 개요
TypeScript의 `protected` 접근 제어자는 클래스 멤버(속성 및 메서드)에 대한 접근을 제어하는 데 사용됩니다. 이 키워드는 해당 멤버가 클래스 내부 및 그 클래스를 상속한 자식 클래스에서만 접근 가능하도록 설정합니다.

## 문서화

### 목적
`protected` 접근 제어자는 클래스의 내부 구현을 보호하면서, 상속을 통해 자식 클래스에서 해당 멤버에 접근할 수 있게 허용합니다. 이는 캡슐화 원칙을 준수하며, 코드의 재사용성을 높입니다.

### 사용법
`protected` 키워드는 클래스의 속성이나 메서드 앞에 사용합니다. 다음은 기본적인 문법입니다:

```typescript
class Base {
    protected member: string;

    constructor(member: string) {
        this.member = member;
    }

    protected displayMember(): void {
        console.log(this.member);
    }
}

class Derived extends Base {
    constructor(member: string) {
        super(member);
    }

    public show(): void {
        this.displayMember(); // 자식 클래스에서 protected 메서드 호출 가능
    }
}
```

## 예제

### 기본 사용 예제

```typescript
class Animal {
    protected name: string;

    constructor(name: string) {
        this.name = name;
    }

    protected speak(): void {
        console.log(`${this.name}가 소리를 냅니다.`);
    }
}

class Dog extends Animal {
    public bark(): void {
        this.speak(); // protected 메서드 접근 가능
    }
}

const dog = new Dog("강아지");
dog.bark(); // "강아지가 소리를 냅니다."
```

### protected와 public 비교

```typescript
class Person {
    public firstName: string;
    protected lastName: string;

    constructor(firstName: string, lastName: string) {
        this.firstName = firstName;
        this.lastName = lastName;
    }
}

class Employee extends Person {
    public display(): void {
        console.log(`${this.firstName} ${this.lastName}`); // lastName 접근 가능
    }
}

const employee = new Employee("홍길동", "개발자");
console.log(employee.firstName); // "홍길동"
// console.log(employee.lastName); // 오류: protected 멤버에 접근할 수 없음
```

## 설명
`protected` 접근 제어자를 사용할 때는 다음과 같은 일반적인 주의 사항이 있습니다:

1. **상속 관계**: `protected` 멤버는 오직 해당 클래스를 상속한 자식 클래스에서만 접근할 수 있습니다. 인스턴스화된 객체에서는 접근할 수 없습니다.
   
2. **캡슐화**: `protected`를 사용하면 외부에서 해당 멤버에 대한 직접적인 접근을 차단하여 데이터 보호 및 캡슐화를 강화할 수 있습니다.

3. **다중 상속**: TypeScript는 다중 상속을 지원하지 않으므로, `protected` 멤버를 상속받는 자식 클래스는 단일 부모 클래스에서만 접근할 수 있습니다.

## 한 줄 요약
TypeScript의 `protected` 접근 제어자는 클래스 내부와 그 자식 클래스에서만 사용할 수 있는 멤버를 정의하는 데 사용됩니다.