<!--
Meta Description: # TypeScript 中的物件（Object）詳解 ## 簡介 物件（Object）是 TypeScript 中一種重要的資料類型，表示一組鍵值對的集合。它在 TypeScript 中用於創建結構化的資料模型，並提供靜態類型檢查的能力。 ## 文件說明 在 TypeScript 中，物件資料類型...
Meta Keywords: typescript, string, age, number, make
-->

# TypeScript 中的物件（Object）詳解

## 簡介
物件（Object）是 TypeScript 中一種重要的資料類型，表示一組鍵值對的集合。它在 TypeScript 中用於創建結構化的資料模型，並提供靜態類型檢查的能力。

## 文件說明
在 TypeScript 中，物件資料類型用於描述一組具有特定屬性和方法的複雜資料結構。物件可以包含基本類型（如字串、數字、布林值等）或其他物件。使用物件可以提高程式碼的可讀性和可維護性。

### 用途
- 組織資料：物件可以將相關的資料捆綁在一起，便於管理和使用。
- 提供類型安全：TypeScript 的靜態類型檢查可以提前捕捉錯誤，減少運行時錯誤。
- 支持面向物件編程：物件是面向物件編程（OOP）的核心，支持封裝、繼承和多態性。

### 使用方式
在 TypeScript 中，可以使用字面量語法或類別來定義物件。例如：

```typescript
// 使用字面量定義物件
let person: { name: string; age: number } = {
    name: "張三",
    age: 30
};

// 使用類別定義物件
class Car {
    make: string;
    model: string;

    constructor(make: string, model: string) {
        this.make = make;
        this.model = model;
    }
}

let myCar = new Car("Toyota", "Corolla");
```

## 範例
以下是一些使用物件的基本範例：

```typescript
// 定義一個有屬性的物件
let book: { title: string; author: string; pages: number } = {
    title: "學習 TypeScript",
    author: "李四",
    pages: 250
};

// 訪問物件屬性
console.log(book.title); // 輸出: 學習 TypeScript

// 更新物件屬性
book.pages = 300;
console.log(book.pages); // 輸出: 300
```

## 解釋
使用物件時需要注意以下幾點：

- **屬性定義**：必須確保物件的屬性與定義一致，否則 TypeScript 會報錯。
- **可選屬性**：可以使用 `?` 定義可選屬性，例如 `{ name: string; age?: number }`，這表示 `age` 可能不存在。
- **索引簽名**：若物件屬性不確定，可以使用索引簽名，例如 `{ [key: string]: number }`，表示該物件可以有任意數量的字串鍵，且值必須是數字。

### 常見錯誤
- 忘記初始化物件屬性，可能導致 `undefined` 錯誤。
- 錯誤使用物件類型，會導致類型不匹配的錯誤。

## 總結
物件是 TypeScript 中不可或缺的資料類型，能夠幫助開發者組織和管理資料，並提高程式碼的可讀性和維護性。