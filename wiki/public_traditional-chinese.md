<!--
Meta Description: # TypeScript 中的 "public" 修飾符：使用與範例 ## 摘要 在 TypeScript 中，`public` 修飾符用於定義類別成員的可訪問性，預設情況下所有成員都是公共的，這意味著它們可以被類別外部的代碼訪問。 ## 文檔 `public` 是 TypeScript 中的一種訪...
Meta Keywords: public, typescript, brand, string, property
-->

# TypeScript 中的 "public" 修飾符：使用與範例

## 摘要
在 TypeScript 中，`public` 修飾符用於定義類別成員的可訪問性，預設情況下所有成員都是公共的，這意味著它們可以被類別外部的代碼訪問。

## 文檔
`public` 是 TypeScript 中的一種訪問修飾符，用於控制類別成員（屬性和方法）的可見性。當成員被標記為 `public` 時，這些成員可以被任何其他代碼訪問，而不僅僅是該類別的內部代碼。這對於需要在類外部使用類的功能的情況非常有用。

### 目的
- 提供對類別成員的公開訪問。
- 增強代碼的可維護性和可理解性，因為開發者可以輕易識別哪些成員是對外可用的。

### 使用
當定義一個類別時，可以在成員前使用 `public` 關鍵字來顯式指定其訪問權限。例如：

```typescript
class Example {
    public property: string;

    constructor(value: string) {
        this.property = value;
    }

    public method(): string {
        return this.property;
    }
}
```

在這個例子中，`property` 屬性和 `method` 方法都是公有的，這意味著它們可以被實例化的對象外部訪問。

## 範例
以下是如何在 TypeScript 中使用 `public` 的基本範例：

```typescript
class Car {
    public brand: string;

    constructor(brand: string) {
        this.brand = brand;
    }

    public displayBrand(): string {
        return `This car brand is ${this.brand}.`;
    }
}

const myCar = new Car("Toyota");
console.log(myCar.displayBrand()); // 輸出: This car brand is Toyota.
```

在這個範例中，`brand` 和 `displayBrand` 都是公共成員，允許在類的外部通過 `myCar` 對象訪問。

## 解釋
雖然 `public` 是 TypeScript 類別成員的預設訪問修飾符，但明確使用它可以提高代碼的可讀性。此外，開發者在使用該修飾符時應注意以下幾點：

- **易混淆的默認行為**：由於所有成員默認為公共，開發者可能會忽略顯式標記，這可能導致代碼可讀性下降。
- **隱私問題**：在某些情況下，開發者可能希望限制對某些成員的訪問，這時應考慮使用 `private` 或 `protected` 修飾符。

## 一句話總結
`public` 修飾符在 TypeScript 中用於定義可被外部代碼訪問的類別成員，是增強代碼可讀性的重要工具。