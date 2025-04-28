<!--
Meta Description: # TypeScript의 문자열(string) 데이터 타입 ## 개요 TypeScript에서 문자열(string)은 텍스트 데이터를 나타내는 기본 데이터 타입으로, 다양한 문자열 조작 기능을 제공하여 개발자가 효율적으로 코드를 작성할 수 있도록 돕습니다. ## 문서화 ...
Meta Keywords: string, 문자열, let, typescript, 문자열은
-->

# TypeScript의 문자열(string) 데이터 타입

## 개요
TypeScript에서 문자열(string)은 텍스트 데이터를 나타내는 기본 데이터 타입으로, 다양한 문자열 조작 기능을 제공하여 개발자가 효율적으로 코드를 작성할 수 있도록 돕습니다.

## 문서화
TypeScript에서 문자열은 `string` 키워드를 사용하여 정의됩니다. 문자열은 작은따옴표(`'`), 큰따옴표(`"`), 또는 백틱(``` ` ```)을 사용하여 생성할 수 있으며, 각 방식은 특정한 기능을 제공합니다.

### 목적
문자열은 주로 텍스트를 저장하고 조작하는 데 사용됩니다. TypeScript는 정적 타입 시스템을 통해 문자열과 관련된 오류를 컴파일 시점에 발견할 수 있도록 도와줍니다.

### 사용법
문자열은 다음과 같이 선언할 수 있습니다:

```typescript
let singleQuote: string = 'Hello, World!';
let doubleQuote: string = "Hello, TypeScript!";
let templateLiteral: string = `Hello, ${singleQuote}`;
```

- **단일 따옴표**와 **이중 따옴표**: 기본적인 문자열 생성에 사용됩니다.
- **템플릿 리터럴**: 문자열 내에 변수를 삽입하거나 여러 줄 문자열을 작성하는 데 유용합니다.

## 예제
### 기본 문자열 예제
```typescript
let greeting: string = "안녕하세요!";
console.log(greeting); // 출력: 안녕하세요!
```

### 템플릿 리터럴 사용 예제
```typescript
let name: string = "홍길동";
let welcomeMessage: string = `환영합니다, ${name}님!`;
console.log(welcomeMessage); // 출력: 환영합니다, 홍길동님!
```

### 문자열 메서드 예제
```typescript
let original: string = "TypeScript";
let upperCase: string = original.toUpperCase();
console.log(upperCase); // 출력: TYPESCRIPT
```

## 설명
문자열을 사용할 때 흔히 발생하는 몇 가지 주의사항은 다음과 같습니다:

1. **타입 불일치**: 문자열을 숫자와 혼합하여 사용하려고 할 때 오류가 발생할 수 있습니다. 항상 문자열 타입을 확인해야 합니다.
   
   ```typescript
   let value: string = "100";
   let total: number = value + 100; // 잘못된 사용
   ```

2. **템플릿 리터럴의 사용**: 템플릿 리터럴은 문자열 내에 변수를 쉽게 삽입할 수 있는 강력한 기능을 제공하지만, 백틱(``` ` ```)을 사용해야 하며, 일반 따옴표와 혼동하지 않도록 주의해야 합니다.

3. **불변성**: 문자열은 불변(immutable) 타입입니다. 문자열을 수정하고자 할 경우, 새로운 문자열을 생성해야 합니다.

## 한 줄 요약
TypeScript에서 문자열(string)은 텍스트 데이터를 표현하고 조작하는 기본 데이터 타입으로, 다양한 기능과 메서드를 제공합니다.