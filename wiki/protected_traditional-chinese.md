<!--
Meta Description: # TypeScript 中的 "protected" 關鍵字 ## 摘要 在 TypeScript 中，`protected` 關鍵字用於定義類別屬性和方法的可見性，允許在類別內部或子類別中訪問，但在類別外部不可見。 ## 文檔 `protected` 是 TypeScript 中的一個訪問修飾符...
Meta Keywords: protected, typescript, string, sound, class
-->

# TypeScript 中的 "protected" 關鍵字

## 摘要
在 TypeScript 中，`protected` 關鍵字用於定義類別屬性和方法的可見性，允許在類別內部或子類別中訪問，但在類別外部不可見。

## 文檔
`protected` 是 TypeScript 中的一個訪問修飾符，主要用於控制類別成員的可見性。與 `private` 不同，`protected` 成員可以在類別及其子類別中被訪問，而無法從類別的外部直接訪問。

### 目的
使用 `protected` 可以讓開發者在設計類別時，將某些屬性和方法隱藏起來，僅允許子類別進行訪問，這樣有助於維護封裝性和繼承結構。

### 用法
在 TypeScript 中，使用 `protected` 訪問修飾符非常簡單，只需在屬性或方法前添加 `protected` 關鍵字：

```typescript
class Base {
    protected property: string;

    constructor(value: string) {
        this.property = value;
    }

    protected method(): void {
        console.log("Base method");
    }
}

class Derived extends Base {
    constructor(value: string) {
        super(value);
    }

    public accessProperty(): string {
        return this.property; // 可以訪問 protected 屬性
    }

    public callMethod(): void {
        this.method(); // 可以調用 protected 方法
    }
}
```

## 範例
以下是使用 `protected` 的基本範例：

```typescript
class Animal {
    protected sound: string;

    constructor(sound: string) {
        this.sound = sound;
    }

    protected makeSound(): void {
        console.log(this.sound);
    }
}

class Dog extends Animal {
    constructor() {
        super("Woof");
    }

    public bark(): void {
        this.makeSound(); // 可以調用 protected 方法
    }
}

const dog = new Dog();
dog.bark(); // 輸出: Woof
```

## 解釋
使用 `protected` 時，需要注意以下幾點：

1. **子類別訪問**：只有子類別能夠訪問 `protected` 成員，這意味著如果你想在類別外部訪問這些成員，將無法直接訪問。
2. **初始化**：在子類別的構造函數中，可以使用 `super()` 來初始化 `protected` 屬性。
3. **封裝性**：`protected` 有助於保持類別的封裝性和內部實現的靈活性，防止外部代碼直接干預。

## 一句總結
在 TypeScript 中，`protected` 關鍵字用於限制類別成員的訪問範圍，使其僅可在類別及其子類別中使用。