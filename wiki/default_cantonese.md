<!--
Meta Description: # TypeScript 中的 "default" 關鍵字概述 ## 概要 在 TypeScript 中，"default" 關鍵字主要用於模塊導出，允許開發者導出單一實體，從而簡化模塊的導入方式。 ## 文檔 "Default" 在 TypeScript 中的主要用途是進行默認導出（default...
Meta Keywords: default, typescript, person, export, function
-->

# TypeScript 中的 "default" 關鍵字概述

## 概要
在 TypeScript 中，"default" 關鍵字主要用於模塊導出，允許開發者導出單一實體，從而簡化模塊的導入方式。

## 文檔
"Default" 在 TypeScript 中的主要用途是進行默認導出（default export）。這意味著當一個模塊只需要導出一個主要功能或類別時，可以使用 "default" 來指定這個導出。這樣，其他模塊在導入時可以使用自己選擇的名稱來引用這個導出。

### 目的
使用 "default" 導出可以使模塊的導入更加靈活，開發者不需要記住導出的具體名稱，只需使用任意名稱來引用。

### 用法
當你在模塊中使用 "default" 進行導出時，可以這樣寫：

```typescript
// 導出一個默認函數
export default function greet(name: string): string {
    return `Hello, ${name}!`;
}
```

在導入這個模塊時，可以這樣使用：

```typescript
import greet from './greet';

console.log(greet('Alice')); // 輸出: Hello, Alice!
```

## 範例
以下是使用 "default" 導出的基本範例：

### 範例 1：默認函數導出
```typescript
// myFunction.ts
export default function myFunction(x: number, y: number): number {
    return x + y;
}

// main.ts
import add from './myFunction';

console.log(add(5, 3)); // 輸出: 8
```

### 範例 2：默認類別導出
```typescript
// Person.ts
export default class Person {
    constructor(public name: string) {}
}

// main.ts
import Person from './Person';

const person = new Person('Bob');
console.log(person.name); // 輸出: Bob
```

## 解釋
使用 "default" 導出時，有一些常見的注意事項：

- **只能有一個默認導出**：每個模塊只能有一個默認導出，這使得導入時不會產生混淆。
- **導入名稱自由**：導入的名稱不必與導出的名稱相同，這為開發者提供了靈活性。
- **與具名導出相結合**：可以在同一模塊中同時使用默認導出和具名導出，但要注意導入時的語法。

例如：

```typescript
// myModule.ts
export default function defaultFunction() {}
export function namedFunction() {}
```

在導入時：

```typescript
import defaultFunc, { namedFunction } from './myModule';
```

## 總結
在 TypeScript 中，"default" 關鍵字用於簡化模塊的導出和導入，使開發者能夠輕鬆使用默認導出來提高代碼的可讀性和靈活性。