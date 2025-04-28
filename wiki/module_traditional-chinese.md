<!--
Meta Description: # TypeScript 模組：深入了解 TypeScript 的模組系統 ## 摘要 TypeScript 的模組系統允許開發者將程式碼分割成可重用且獨立的區塊，提高代碼的組織性和可維護性。透過模組，開發者可以更有效地管理依賴關係，讓大型應用程式的開發變得更加簡單。 ## 文件 TypeScrip...
Meta Keywords: typescript, export, import, math, add
-->

# TypeScript 模組：深入了解 TypeScript 的模組系統

## 摘要
TypeScript 的模組系統允許開發者將程式碼分割成可重用且獨立的區塊，提高代碼的組織性和可維護性。透過模組，開發者可以更有效地管理依賴關係，讓大型應用程式的開發變得更加簡單。

## 文件
TypeScript 中的模組是一種封裝代碼的機制，使其能夠在不同的檔案之間進行匯入和匯出。模組可以是任何 JavaScript 檔案，其內部可以包含變數、函數、類別等。當你將 TypeScript 檔案設為模組時，這個檔案會被視為一個獨立的作用域，並且不會與全局作用域的變數或函數發生衝突。

### 使用方式
要使用模組，你只需要在檔案中使用 `export` 關鍵字來匯出變數、函數或類別，同時在其他檔案中使用 `import` 關鍵字來引入這些內容。TypeScript 支援 ES6 模組語法，也支持 CommonJS 和 AMD 等模組系統。

### 詳細說明
- **匯出**：你可以使用 `export` 關鍵字來匯出單一的變數、函數或類別，也可以使用 `export default` 來匯出一個預設的項目。
- **匯入**：使用 `import` 關鍵字來引入外部模組，你可以選擇性地引入某些內容或整個模組。
- **模組解析**：TypeScript 會根據 `tsconfig.json` 中的配置來解析模組，例如 `module` 和 `target` 等選項。
  
## 範例
### 基本範例
以下是一個簡單的模組範例：

**math.ts**
```typescript
// 匯出一個函數
export function add(x: number, y: number): number {
    return x + y;
}
```

**app.ts**
```typescript
// 匯入 math 模組
import { add } from './math';

console.log(add(5, 3)); // 輸出 8
```

### 預設匯出範例
**greeting.ts**
```typescript
// 預設匯出一個函數
export default function greet(name: string): string {
    return `Hello, ${name}!`;
}
```

**main.ts**
```typescript
// 匯入預設模組
import greet from './greeting';

console.log(greet('World')); // 輸出 Hello, World!
```

## 解釋
- **常見陷阱**：當使用模組時，確保檔案的路徑正確，並且注意大小寫，因為某些操作系統對檔案名稱的大小寫敏感。
- **模組解析**：不同的模組解析策略可能會影響你的匯入語句，確保你在 `tsconfig.json` 中正確配置 `moduleResolution` 參數。
- **全局變數**：記住，模組內的變數不會自動加入全局作用域，必須明確匯出才能在其他模組中使用。

## 一句總結
TypeScript 的模組系統提供了一種高效的方式來組織和重用代碼，並促進了大型應用的可維護性。