<!--
Meta Description: # TypeScript 中的 "implements" 關鍵字：全面指南 ## 概述 在 TypeScript 中，`implements` 關鍵字用於類別實現介面，確保類別符合特定的結構和行為規範。這有助於提高代碼的可維護性和可讀性。 ## 文檔 `implements` 關鍵字的主要目的在於強...
Meta Keywords: implements, void, typescript, name, age
-->

# TypeScript 中的 "implements" 關鍵字：全面指南

## 概述
在 TypeScript 中，`implements` 關鍵字用於類別實現介面，確保類別符合特定的結構和行為規範。這有助於提高代碼的可維護性和可讀性。

## 文檔
`implements` 關鍵字的主要目的在於強制類別遵循指定的介面。介面定義了屬性和方法的簽名，而使用 `implements` 的類別必須實現這些屬性和方法。

### 使用方法
當一個類別實現介面時，必須提供該介面中定義的所有屬性和方法的實現。例如：

```typescript
interface Person {
    name: string;
    age: number;
    greet(): void;
}

class Student implements Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    greet(): void {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}
```

在此範例中，`Student` 類別實現了 `Person` 介面，並提供了所需的屬性和方法的具體實現。

## 範例
以下是幾個 `implements` 的基本使用範例：

### 範例 1：簡單介面實現
```typescript
interface Animal {
    species: string;
    sound(): void;
}

class Dog implements Animal {
    species: string;

    constructor() {
        this.species = "Dog";
    }

    sound(): void {
        console.log("Woof!");
    }
}
```

### 範例 2：多重介面實現
```typescript
interface Flyer {
    fly(): void;
}

interface Swimmer {
    swim(): void;
}

class Duck implements Flyer, Swimmer {
    fly(): void {
        console.log("The duck is flying.");
    }

    swim(): void {
        console.log("The duck is swimming.");
    }
}
```

## 解釋
使用 `implements` 時需注意以下常見陷阱：

1. **未實現所有方法**：如果類別未實現介面中的所有屬性和方法，TypeScript 將報錯。
2. **屬性類型不匹配**：類別屬性必須符合介面中對應屬性的類型定義，否則將引發編譯錯誤。
3. **介面可擴展性**：可以使用繼承擴展介面，類別可以實現多個介面，但需確保所有方法的實現都正確。

## 一句總結
`implements` 關鍵字在 TypeScript 中用於類別實現介面，確保類別符合預定的結構和行為規範。