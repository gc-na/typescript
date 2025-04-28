<!--
Meta Description: # TypeScript 中的 "var" 變數宣告 ## 概述 在 TypeScript 中，`var` 是一種用來宣告變數的關鍵字。它的作用類似於 JavaScript，但在 TypeScript 的靜態類型系統中，`var` 的使用有其特定的注意事項。 ## 文檔 ### 目的 `var` 用...
Meta Keywords: var, typescript, hello, localvar, console
-->

# TypeScript 中的 "var" 變數宣告

## 概述
在 TypeScript 中，`var` 是一種用來宣告變數的關鍵字。它的作用類似於 JavaScript，但在 TypeScript 的靜態類型系統中，`var` 的使用有其特定的注意事項。

## 文檔
### 目的
`var` 用於宣告變數，這些變數可以在函數內或全域範圍內使用。雖然 TypeScript 推薦使用 `let` 和 `const` 來進行變數宣告，但 `var` 仍然可以使用，尤其是在需要向後兼容 JavaScript 的情況下。

### 使用方式
`var` 可以在任何地方宣告變數，並且無論在函數內或全域都可以訪問。變數的作用域是函數作用域，這意味著在函數內宣告的 `var` 變數在函數外不可用。

### 詳細說明
1. **作用域**: `var` 的作用域是函數內部。如果在函數外部宣告，則變數會成為全域變數。
2. **提升**: 使用 `var` 宣告的變數會被提升至其作用域的頂部，這意味著可以在宣告之前使用該變數。
3. **重複宣告**: 使用 `var` 宣告的變數可以在同一作用域中被重複宣告，而不會產生錯誤。

## 例子
```typescript
// 宣告全域變數
var globalVar = "Hello, World!";

function exampleFunction() {
    // 宣告函數內變數
    var localVar = "Hello from function!";
    console.log(localVar); // 輸出: Hello from function!
}

exampleFunction();
console.log(globalVar); // 輸出: Hello, World!
// console.log(localVar); // 錯誤: localVar 不在作用範圍內
```

## 解釋
- **常見陷阱**: `var` 的提升特性可能會導致意想不到的錯誤，特別是當你在宣告變數之前使用它時。例如，`console.log(varName);` 在變數宣告之前會顯示 `undefined`，而不是拋出錯誤。
- **使用建議**: 儘管 `var` 在 TypeScript 中是有效的，但建議使用 `let` 和 `const` 來避免作用域和提升問題。這樣能提高程式碼的可讀性和可維護性。

## 單句總結
在 TypeScript 中，`var` 用於宣告變數，但由於其作用域和提升特性，建議使用 `let` 和 `const` 以提高程式碼的可讀性和安全性。