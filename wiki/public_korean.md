<!--
Meta Description: # TypeScript의 "public" 접근 제어자 ## 개요 TypeScript에서 "public"은 클래스의 속성이나 메서드가 외부에서 접근 가능함을 나타내는 접근 제어자입니다. 기본적으로 모든 클래스 멤버는 "public"으로 설정되어 있으므로, 명시적으로 사용...
Meta Keywords: public, 클래스, 외부에서, property, name
-->

# TypeScript의 "public" 접근 제어자

## 개요
TypeScript에서 "public"은 클래스의 속성이나 메서드가 외부에서 접근 가능함을 나타내는 접근 제어자입니다. 기본적으로 모든 클래스 멤버는 "public"으로 설정되어 있으므로, 명시적으로 사용하지 않아도 됩니다.

## 문서화
"public" 접근 제어자는 TypeScript의 객체 지향 프로그래밍에서 중요한 역할을 합니다. 이 제어자는 클래스의 속성이나 메서드가 클래스 외부에서 자유롭게 접근, 수정, 호출될 수 있음을 정의합니다. 이는 API 설계 시 유용하게 활용됩니다.

### 목적
- 클래스 외부에서 멤버 접근 허용
- 객체 지향 프로그래밍 원칙에 따라 캡슐화 지원

### 사용법
"public"은 클래스 정의 내에서 속성 또는 메서드 앞에 명시하여 사용합니다. 기본적으로 모든 클래스 멤버는 "public"으로 간주됩니다.

```typescript
class Example {
    public property: string;

    constructor(property: string) {
        this.property = property;
    }

    public method(): void {
        console.log(this.property);
    }
}
```

## 예제
1. 기본적인 "public" 속성 사용 예제:

```typescript
class Person {
    public name: string;

    constructor(name: string) {
        this.name = name;
    }
}

const person = new Person("홍길동");
console.log(person.name); // 출력: 홍길동
```

2. "public" 메서드 사용 예제:

```typescript
class Calculator {
    public add(a: number, b: number): number {
        return a + b;
    }
}

const calculator = new Calculator();
console.log(calculator.add(5, 3)); // 출력: 8
```

## 설명
"public" 접근 제어자를 사용할 때 주의할 점은, 모든 속성과 메서드가 외부에서 접근 가능하다는 것입니다. 이는 보안 측면에서 문제가 될 수 있으므로, 필요한 경우 "private" 또는 "protected"와 같은 다른 접근 제어자를 사용하는 것이 좋습니다. 

또한, "public"으로 설정된 멤버는 서브클래스에서도 접근이 가능하므로, 클래스 상속을 고려할 때 이를 염두에 두어야 합니다. 

## 한 줄 요약
TypeScript의 "public"은 클래스의 속성과 메서드가 외부에서 접근 가능하도록 설정하는 접근 제어자입니다.