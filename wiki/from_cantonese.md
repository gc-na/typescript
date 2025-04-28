<!--
Meta Description: # TypeScript中的「from」關鍵字：全面指南 ## 概述 在TypeScript中，「from」關鍵字主要用於模組導入，允許開發者從其他模組引入特定的功能或變量。這是現代JavaScript和TypeScript中模組系統的一部分，促進了代碼的組織性和可重用性。 ## 文檔 ### 目的...
Meta Keywords: from, module, import, typescript, number
-->

# TypeScript中的「from」關鍵字：全面指南

## 概述
在TypeScript中，「from」關鍵字主要用於模組導入，允許開發者從其他模組引入特定的功能或變量。這是現代JavaScript和TypeScript中模組系統的一部分，促進了代碼的組織性和可重用性。

## 文檔
### 目的
「from」關鍵字是ES6模組系統的一部分，用於指定從哪個模組導入特定的功能。透過使用「from」關鍵字，開發者可以將代碼組織在不同的檔案中，從而提高可維護性與可讀性。

### 使用方法
在TypeScript中，使用「import」語句搭配「from」關鍵字來導入模組。語法如下：

```typescript
import { ExportedFunction } from './module';
```

這裡的`ExportedFunction`是從指定的模組（`module`）中導入的功能。模組路徑可以是相對路徑或絕對路徑，並需要加上檔案的副檔名（如`.ts`或`.js`）。

### 詳細資訊
- **模組導入**：可以導入函數、類別、變數等。
- **多重導入**：可以同時導入多個功能，語法如下：
  ```typescript
  import { FunctionA, FunctionB } from './module';
  ```
- **重新命名**：可以使用`as`關鍵字對導入的功能進行重新命名：
  ```typescript
  import { OriginalName as NewName } from './module';
  ```
- **默認導入**：如果模組有默認導出，則可以使用以下語法：
  ```typescript
  import DefaultExport from './module';
  ```

## 範例
### 範例 1：基本導入
```typescript
// module.ts
export function greet() {
    console.log("Hello, World!");
}

// main.ts
import { greet } from './module';
greet(); // 輸出: Hello, World!
```

### 範例 2：多重導入
```typescript
// module.ts
export function add(a: number, b: number) {
    return a + b;
}

export function subtract(a: number, b: number) {
    return a - b;
}

// main.ts
import { add, subtract } from './module';
console.log(add(5, 3)); // 輸出: 8
console.log(subtract(5, 3)); // 輸出: 2
```

### 範例 3：重新命名導入
```typescript
// module.ts
export function calculateArea(radius: number) {
    return Math.PI * radius * radius;
}

// main.ts
import { calculateArea as area } from './module';
console.log(area(5)); // 輸出: 78.53981633974483
```

## 解釋
在使用「from」關鍵字時，開發者應注意以下幾點：
- **相對路徑與絕對路徑**：確保正確使用檔案路徑，錯誤的路徑會導致編譯錯誤。
- **命名衝突**：在導入多個功能時，可能會出現名稱衝突，使用`as`進行重新命名可以避免此問題。
- **模組化設計**：良好的模組化設計可以提高代碼的可讀性和可維護性，合理地使用導入可以有效組織代碼。

## 一句總結
在TypeScript中，「from」關鍵字用於從其他模組導入功能，促進代碼的模組化和重用性。