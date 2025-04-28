<!--
Meta Description: # TypeScript 中的 Import 語句：使用指南 ## 簡介 在 TypeScript 中，`import` 語句用於從其他模組引入功能、變數或類別。這使得代碼的組織和重用變得更加簡便，特別是在大型應用程序中。 ## 文檔 `import` 語句是 TypeScript 和 ES6 中的...
Meta Keywords: import, typescript, utils, add, from
-->

# TypeScript 中的 Import 語句：使用指南

## 簡介
在 TypeScript 中，`import` 語句用於從其他模組引入功能、變數或類別。這使得代碼的組織和重用變得更加簡便，特別是在大型應用程序中。

## 文檔
`import` 語句是 TypeScript 和 ES6 中的重要組件。它的主要目的是讓開發者能夠從其他文件或模組中引入代碼。這不僅有助於模組化代碼，還可以提高可維護性和可讀性。

### 使用方法
`import` 語句的基本語法如下：
```typescript
import { 引入的項目 } from '模組路徑';
```

- **引入的項目**：可以是變數、函數、類別等。
- **模組路徑**：可以是相對路徑（如 `./module`）或絕對路徑（如 `module-name`）。

### 詳細信息
- TypeScript 支持多種 import 形式，包括命名導入、默認導入以及整個模組的導入。
- 你也可以使用 `import * as` 來將整個模組引入作為一個命名空間。

## 範例
### 基本用法
```typescript
// 從 utils.ts 引入 add 函數
import { add } from './utils';

console.log(add(2, 3)); // 輸出：5
```

### 默認導入
```typescript
// defaultExport.ts 文件
export default function greet() {
    console.log("Hello, World!");
}

// 在另一個文件中使用
import greet from './defaultExport';

greet(); // 輸出：Hello, World!
```

### 整個模組導入
```typescript
// utils.ts
export function add(x: number, y: number) {
    return x + y;
}

export function subtract(x: number, y: number) {
    return x - y;
}

// 在另一個文件中使用
import * as utils from './utils';

console.log(utils.add(2, 3)); // 輸出：5
console.log(utils.subtract(5, 2)); // 輸出：3
```

## 解釋
### 常見陷阱
- **路徑錯誤**：確保模組路徑正確，尤其是在使用相對路徑時。
- **命名衝突**：如果有多個導入的項目同名，可能會導致衝突。可以使用 `as` 關鍵字重命名導入的項目。
- **Circular Dependencies**：如果模組之間存在循環依賴，可能會導致加載錯誤或未定義錯誤。

### 附加說明
- TypeScript 會在編譯期間檢查導入的類型，這有助於捕捉潛在的錯誤。
- 使用 `import` 時，確保你已經正確安裝和配置了相應的 TypeScript 環境。

## 一句總結
`import` 語句在 TypeScript 中是導入其他模組的核心工具，能夠提高代碼的結構和可重用性。