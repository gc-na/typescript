<!--
Meta Description: # TypeScript 中的 "public" 關鍵字：用法與示例 ## 簡介 在 TypeScript 中，`public` 是一個修飾符，用於指定類成員的可訪問性。使用 `public` 修飾符，可以讓類的屬性和方法在任何地方被訪問。 ## 文檔 ### 目的 `public` 修飾符的主要目...
Meta Keywords: public, name, typescript, person, string
-->

# TypeScript 中的 "public" 關鍵字：用法與示例

## 簡介
在 TypeScript 中，`public` 是一個修飾符，用於指定類成員的可訪問性。使用 `public` 修飾符，可以讓類的屬性和方法在任何地方被訪問。

## 文檔
### 目的
`public` 修飾符的主要目的是明確標示類成員的可訪問性。它是 TypeScript 中的三種可訪問性修飾符之一，其他兩種是 `private` 和 `protected`。

### 用法
在 TypeScript 中，當一個屬性或方法被標記為 `public` 時，它可以被類的實例及其子類或其他任何代碼訪問。這意味著 `public` 是默認的可訪問性修飾符，因此即使不明確指定，類成員也是 `public`。

### 詳細說明
- **定義**：使用 `public` 修飾符時，開發者可以確保類的某些成員在外部可用，這對於需要直接訪問的屬性和方法非常有用。
- **默認行為**：如果未指定修飾符，TypeScript 將自動將其視為 `public`。
- **範例**：以下是簡單的示例，展示了如何使用 `public` 修飾符來定義類的屬性和方法。

## 示例
```typescript
class Person {
    public name: string;  // public 屬性

    constructor(name: string) {
        this.name = name;
    }

    public greet(): string {  // public 方法
        return `Hello, my name is ${this.name}`;
    }
}

const person = new Person("Alice");
console.log(person.greet()); // 輸出: Hello, my name is Alice
```

在這個示例中，`name` 屬性和 `greet` 方法都是 `public`，因此可以從 `Person` 類的實例直接訪問。

## 解釋
- **常見陷阱**：雖然 `public` 是默認修飾符，但初學者可能會在使用時感到混淆，因此建議在需要時明確標示，以增強代碼的可讀性。
- **作用域**：`public` 成員可以被其他類、子類及任何代碼自由訪問，這意味著它們不受限制。在設計 API 時需要謹慎使用，避免不必要的公開接口。
- **與其他修飾符的比較**：相對於 `private` 和 `protected`，`public` 提供了最寬鬆的訪問權限，適用於需要在外部可訪問的情況。

## 一句話總結
`public` 在 TypeScript 中用於標記類的屬性和方法為可訪問的，並且是默認的可訪問性修飾符。