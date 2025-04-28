<!--
Meta Description: # TypeScript의 "private" 접근 제어자: 비공식적인 데이터 은닉을 위한 가이드 ## 개요 TypeScript에서 "private" 키워드는 클래스 내부에서만 접근할 수 있는 속성이나 메서드를 정의하는 데 사용됩니다. 이는 데이터 은닉을 통해 객체 지향 ...
Meta Keywords: private, model, 클래스, person, 클래스의
-->

# TypeScript의 "private" 접근 제어자: 비공식적인 데이터 은닉을 위한 가이드

## 개요
TypeScript에서 "private" 키워드는 클래스 내부에서만 접근할 수 있는 속성이나 메서드를 정의하는 데 사용됩니다. 이는 데이터 은닉을 통해 객체 지향 프로그래밍의 캡슐화를 지원합니다.

## 문서화
TypeScript의 "private" 접근 제어자는 클래스의 속성이나 메서드 앞에 위치하여 해당 요소에 대한 접근을 제한합니다. "private"으로 선언된 멤버는 클래스 외부에서 직접 접근할 수 없으며, 오직 클래스 내부에서만 사용 가능합니다. 이를 통해 객체의 상태를 보호하고, 외부에서의 의도치 않은 변경을 방지할 수 있습니다.

### 사용법
"private" 접근 제어자를 사용하려면 클래스 내에서 속성이나 메서드를 선언할 때 "private" 키워드를 앞에 붙이면 됩니다. 다음은 기본적인 사용 예입니다.

```typescript
class Person {
    private name: string;

    constructor(name: string) {
        this.name = name;
    }

    private greet() {
        return `안녕하세요, ${this.name}님!`;
    }

    public introduce() {
        return this.greet();
    }
}

const person = new Person("철수");
console.log(person.introduce()); // "안녕하세요, 철수님!"
// console.log(person.greet()); // 오류: greet은 'Person' 클래스의 private 속성입니다.
```

## 예제
### 기본 사용 예
```typescript
class Car {
    private model: string;

    constructor(model: string) {
        this.model = model;
    }

    public getModel(): string {
        return this.model;
    }
}

const myCar = new Car("소나타");
console.log(myCar.getModel()); // "소나타"
// console.log(myCar.model); // 오류: 'model'은 'Car' 클래스의 private 속성입니다.
```

### 메서드에 대한 접근 제한
```typescript
class BankAccount {
    private balance: number;

    constructor(initialBalance: number) {
        this.balance = initialBalance;
    }

    private updateBalance(amount: number) {
        this.balance += amount;
    }

    public deposit(amount: number) {
        this.updateBalance(amount);
    }

    public getBalance(): number {
        return this.balance;
    }
}

const account = new BankAccount(1000);
account.deposit(500);
console.log(account.getBalance()); // 1500
// account.updateBalance(-100); // 오류: 'updateBalance'는 'BankAccount' 클래스의 private 속성입니다.
```

## 설명
TypeScript에서 "private" 접근 제어자를 사용할 때 주의할 점은 다음과 같습니다:

- **상속**: "private" 멤버는 해당 클래스를 상속하는 자식 클래스에서도 접근할 수 없습니다. 자식 클래스에서 부모 클래스의 private 멤버에 접근하려고 하면 오류가 발생합니다.
- **테스트**: private 멤버는 테스트하기 어려운 경우가 많습니다. 필요에 따라 public 메서드를 통해 간접적으로 접근해야 할 수 있습니다.
- **타입 안전성**: private 멤버는 클래스 내부에서만 접근 가능하므로, 코드의 타입 안정성을 높이는 데 기여합니다.

## 한 줄 요약
TypeScript의 "private" 접근 제어자는 클래스 내부에서만 접근할 수 있는 속성과 메서드를 정의하여 데이터 은닉을 지원합니다.