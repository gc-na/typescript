<!--
Meta Description: # TypeScript 中的 readonly 修飾符：深入解析與實務應用 ## 概述 `readonly` 是 TypeScript 中的一個修飾符，用於定義只讀屬性，確保對特定對象屬性的不可變性，從而提高代碼的安全性和可維護性。 ## 文檔 `readonly` 修飾符允許開發者在定義介面或類...
Meta Keywords: readonly, typescript, radius, point, number
-->

# TypeScript 中的 readonly 修飾符：深入解析與實務應用

## 概述
`readonly` 是 TypeScript 中的一個修飾符，用於定義只讀屬性，確保對特定對象屬性的不可變性，從而提高代碼的安全性和可維護性。

## 文檔
`readonly` 修飾符允許開發者在定義介面或類別時，設置某些屬性為只讀。這意味著在對象創建之後，這些屬性不能被修改，從而防止意外的數據變更。

### 用途與使用
- **定義只讀屬性**：透過在屬性前加上 `readonly`，開發者可以保證這些屬性在初始化後不會被修改。
- **增強代碼可讀性**：清晰地表達哪些屬性是可變的，哪些是固定的，增強了代碼的可維護性。
- **防範錯誤**：避免因為不小心修改屬性而導致的錯誤。

### 詳細說明
在 TypeScript 中，`readonly` 可以用於介面和類別的屬性聲明中。以下是其基本語法：

```typescript
class Example {
    readonly property: string;

    constructor(value: string) {
        this.property = value;
    }
}
```

在上述範例中，`property` 屬性被標記為 `readonly`，這表示一旦通過構造函數賦值後，無法再更改其值。

## 示例
以下是使用 `readonly` 的基本範例：

### 介面範例
```typescript
interface Point {
    readonly x: number;
    readonly y: number;
}

const point: Point = { x: 10, y: 20 };

// point.x = 30; // 這將導致編譯錯誤
```

### 類別範例
```typescript
class Circle {
    readonly radius: number;

    constructor(radius: number) {
        this.radius = radius;
    }
}

const circle = new Circle(5);

// circle.radius = 10; // 這將導致編譯錯誤
```

## 解釋
使用 `readonly` 時，開發者需注意以下幾點：

- **初始化限制**：只讀屬性必須在構造函數中初始化，否則編譯器將報錯。
- **對象的引用**：如果對象屬性是另一個對象，則使用 `readonly` 只會保護對象的引用，並不會保護嵌套對象的可變性。
- **陣列的只讀性**：在陣列上使用 `readonly` 會使整個陣列成為只讀，但可以訪問元素。要改變元素，需使用不變式的數據結構。

## 一句話總結
`readonly` 修飾符在 TypeScript 中用於定義只讀屬性，確保對象的不可變性，從而提升代碼的安全性與可維護性。