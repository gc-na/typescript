<!--
Meta Description: # TypeScript 中的 require：使用與最佳實踐 ## 摘要 `require` 是 Node.js 中的一個函數，用於導入模塊到 TypeScript 應用程序中。它使得代碼的模組化變得簡單，並促進了代碼重用和組織。 ## 文檔 在 TypeScript 中，`require` 函數...
Meta Keywords: require, typescript, math, commonjs, const
-->

# TypeScript 中的 require：使用與最佳實踐

## 摘要
`require` 是 Node.js 中的一個函數，用於導入模塊到 TypeScript 應用程序中。它使得代碼的模組化變得簡單，並促進了代碼重用和組織。

## 文檔
在 TypeScript 中，`require` 函數主要用於加載 CommonJS 模塊。它允許開發者在代碼中引入其他 JavaScript 或 TypeScript 文件，以便使用它們定義的功能或變量。這種模組系統是 Node.js 環境的核心部分，使得代碼結構更為清晰。

### 用法
使用 `require` 的基本語法如下：

```typescript
const 模塊名稱 = require('模塊路徑');
```

- **模塊名稱**：變量名，用於存儲導入的模塊。
- **模塊路徑**：可為內置模塊名或相對於當前文件的路徑。

### 詳細信息
在 TypeScript 中，使用 `require` 導入模塊時，確保正確配置 TypeScript 編譯器的 `tsconfig.json` 文件，特別是 `module` 和 `target` 屬性。若使用 ES6 模塊，建議使用 `import` 語句，但 `require` 在 CommonJS 環境中仍然很常見。

## 示例
以下是使用 `require` 的一些基本示例：

### 導入內置模塊
```typescript
const fs = require('fs');
```

### 導入第三方模塊
```typescript
const express = require('express');
```

### 導入自定義模塊
假設有一個名為 `math.ts` 的檔案，其中定義了一個 `add` 函數：
```typescript
// math.ts
export function add(a: number, b: number): number {
    return a + b;
}
```
可以這樣導入：
```typescript
const math = require('./math');
console.log(math.add(5, 3)); // 輸出：8
```

## 解釋
在使用 `require` 時，有一些常見的陷阱和注意事項：
- **類型定義**：在 TypeScript 中，導入的模塊若沒有適當的類型定義，可能會導致編譯錯誤。可以使用 `@types` 包來獲取類型支持。
- **模塊加載順序**：`require` 是同步操作，模塊的加載順序可能會影響到代碼的執行。如果使用循環依賴，需謹慎處理。
- **CommonJS 與 ES 模塊**：在 TypeScript 中，`require` 和 `import` 語法不應混用。選擇一種模塊系統並始終使用相同的語法。

## 一句總結
`require` 是 TypeScript 中用於導入 CommonJS 模塊的函數，使代碼模組化與重用變得更加簡單。