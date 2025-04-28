<!--
Meta Description: # TypeScript 模組 (Module) 的完整指南 ## 概述 TypeScript 模組是一種組織和管理程式碼的方式，允許開發者將程式碼分成不同的檔案，以提高可維護性和可重用性。 ## 文件說明 模組是 TypeScript 中一個重要的概念，旨在幫助開發者管理大型應用程式的結構。透過模...
Meta Keywords: typescript, export, number, import, function
-->

# TypeScript 模組 (Module) 的完整指南

## 概述
TypeScript 模組是一種組織和管理程式碼的方式，允許開發者將程式碼分成不同的檔案，以提高可維護性和可重用性。

## 文件說明
模組是 TypeScript 中一個重要的概念，旨在幫助開發者管理大型應用程式的結構。透過模組，開發者可以將程式碼分成不同的檔案，每一個檔案都可以定義自己的變數、函數、類別等，並可以選擇性地導出（export）或導入（import）這些成員。

### 目的
模組的主要目的是提高程式碼的可讀性和可維護性。透過明確的結構，開發者能夠更容易地理解和修改代碼。同時，模組化的設計還可以促進代碼的重用。

### 使用方式
在 TypeScript 中，您可以通過 `export` 關鍵字導出成員，並使用 `import` 關鍵字導入其他模組的成員。以下是基本的用法：

- **導出成員：**
  ```typescript
  // 這是一個模組，名為 myModule.ts
  export const greeting = "Hello, World!";
  export function sayHello(name: string) {
      return `${greeting} I'm ${name}.`;
  }
  ```

- **導入成員：**
  ```typescript
  // 這是另一個模組，名為 app.ts
  import { greeting, sayHello } from './myModule';

  console.log(sayHello("Alice")); // 輸出: Hello, World! I'm Alice.
  ```

## 例子
以下是 TypeScript 模組的簡單範例：

### 1. 基本模組
```typescript
// math.ts
export function add(a: number, b: number): number {
    return a + b;
}

export function subtract(a: number, b: number): number {
    return a - b;
}

// app.ts
import { add, subtract } from './math';

console.log(add(5, 3)); // 輸出: 8
console.log(subtract(5, 3)); // 輸出: 2
```

### 2. 整體導入
```typescript
// utilities.ts
export const PI = 3.14;
export function calculateCircumference(radius: number): number {
    return 2 * PI * radius;
}

// app.ts
import * as utils from './utilities';

console.log(utils.calculateCircumference(5)); // 輸出: 31.400000000000002
```

## 解釋
在使用 TypeScript 模組時，開發者需要注意以下幾點：

- **循環依賴：** 如果兩個模組相互導入，可能會導致循環依賴問題。要小心設計模組的依賴關係。
- **命名衝突：** 當導入多個模組時，若有相同名稱的成員，需使用別名（alias）來避免衝突。
- **編譯和運行環境：** 確保編譯器的設定支持模組（例如，使用 `module` 選項設置為 `commonjs` 或 `es6`）以正確地執行模組化代碼。

## 一句總結
TypeScript 模組提供了一種有效的方式來組織和管理應用程式的程式碼，提高其可維護性和可重用性。