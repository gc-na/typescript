<!--
Meta Description: # TypeScript에서의 static 키워드: 정적 멤버 및 메서드 ## 개요 TypeScript에서 `static` 키워드는 클래스의 정적 멤버와 메서드를 정의하는 데 사용됩니다. 정적 멤버는 인스턴스가 아닌 클래스 자체에 속하며, 클래스의 모든 인스턴스가 공유할...
Meta Keywords: static, 클래스의, number, 메서드, 클래스
-->

# TypeScript에서의 static 키워드: 정적 멤버 및 메서드

## 개요
TypeScript에서 `static` 키워드는 클래스의 정적 멤버와 메서드를 정의하는 데 사용됩니다. 정적 멤버는 인스턴스가 아닌 클래스 자체에 속하며, 클래스의 모든 인스턴스가 공유할 수 있는 데이터를 제공합니다.

## 문서화
### 목적
`static` 키워드는 클래스 내부에서 인스턴스가 아닌 클래스 자체에 속하는 멤버와 메서드를 정의하는 데 사용됩니다. 이를 통해 객체의 인스턴스와는 독립적으로 공유 가능한 속성과 기능을 제공할 수 있습니다.

### 사용법
`static` 키워드는 클래스의 속성 또는 메서드 앞에 선언하여 사용합니다. 정적 멤버는 클래스 이름을 통해 접근할 수 있으며, 인스턴스를 생성하지 않고도 사용할 수 있습니다.

```typescript
class MyClass {
    static staticProperty: number = 42;

    static staticMethod(): string {
        return 'This is a static method.';
    }
}

// 정적 속성 사용
console.log(MyClass.staticProperty); // 42

// 정적 메서드 사용
console.log(MyClass.staticMethod()); // This is a static method.
```

### 세부사항
1. **정적 속성**: 정적 속성은 클래스의 모든 인스턴스가 공유하는 데이터를 저장합니다.
2. **정적 메서드**: 정적 메서드는 클래스의 인스턴스 없이 호출할 수 있는 메서드로, 클래스와 관련된 기능을 제공합니다.
3. **정적 멤버 접근**: 정적 멤버는 클래스 이름을 통해 직접 접근 가능하며, 인스턴스 생성이 필요 없습니다.

## 예제
### 정적 속성과 메서드 예시

```typescript
class Calculator {
    static add(x: number, y: number): number {
        return x + y;
    }

    static subtract(x: number, y: number): number {
        return x - y;
    }
}

// 정적 메서드 호출
console.log(Calculator.add(5, 3)); // 8
console.log(Calculator.subtract(5, 3)); // 2
```

### 정적 속성 사용 예시

```typescript
class Counter {
    static count: number = 0;

    static increment() {
        this.count++;
    }
}

// 정적 메서드 호출 및 정적 속성 접근
Counter.increment();
console.log(Counter.count); // 1
Counter.increment();
console.log(Counter.count); // 2
```

## 설명
- **정적 멤버의 범위**: 정적 멤버는 클래스의 인스턴스와는 별개로 존재하며, 인스턴스의 속성과 메서드에 접근할 수 없습니다. 따라서, 정적 멤버는 클래스의 상태를 유지하기 위한 용도로 적합합니다.
- **정적 메서드의 제약**: 정적 메서드는 클래스 인스턴스의 속성에 접근할 수 없기 때문에, 인스턴스 관련 데이터나 메서드에 접근할 필요가 없는 경우에만 사용해야 합니다.
- **OOP 원칙**: 정적 멤버는 객체 지향 프로그래밍(OOP) 원칙을 위반하지 않도록 주의해야 하며, 필요한 경우에만 사용해야 합니다.

## 한 줄 요약
TypeScript의 `static` 키워드는 클래스의 정적 멤버와 메서드를 정의하여 인스턴스와 관계없이 클래스 자체에서 데이터와 기능을 공유할 수 있도록 합니다.