<!--
Meta Description: # TypeScript 中的 return 關鍵字：用途、範例與注意事項 ## 簡介 `return` 是 TypeScript 和 JavaScript 中用於結束函數執行並返回值的關鍵字。它是函數的重要組成部分，讓開發者能夠傳遞數據回調用該函數的地方。 ## 文檔 ### 目的 `return...
Meta Keywords: return, typescript, number, name, function
-->

# TypeScript 中的 return 關鍵字：用途、範例與注意事項

## 簡介
`return` 是 TypeScript 和 JavaScript 中用於結束函數執行並返回值的關鍵字。它是函數的重要組成部分，讓開發者能夠傳遞數據回調用該函數的地方。

## 文檔
### 目的
`return` 主要用來結束函數的執行並返回一個值。當函數執行到 `return` 語句時，函數會立即停止，並將指定的值返回給調用者。

### 用法
在 TypeScript 中，`return` 語句通常用在函數的最後，並可以返回任何類型的數據，包括基本類型（如數字、字符串、布爾值）和複雜類型（如對象、數組、類型別名等）。

### 詳細說明
- **基本語法**：
  ```typescript
  function functionName(parameters): returnType {
      // 函數邏輯
      return value;
  }
  ```
- **返回類型**：在 TypeScript 中，可以通過函數的返回類型來明確指定函數返回的數據類型。例如：
  ```typescript
  function add(a: number, b: number): number {
      return a + b;
  }
  ```

## 範例
### 基本範例
```typescript
function greet(name: string): string {
    return `Hello, ${name}!`;
}

console.log(greet("Alice")); // 輸出: Hello, Alice!
```

### 返回數字
```typescript
function square(num: number): number {
    return num * num;
}

console.log(square(4)); // 輸出: 16
```

### 返回對象
```typescript
function createUser(name: string, age: number): { name: string; age: number } {
    return { name, age };
}

const user = createUser("Bob", 30);
console.log(user); // 輸出: { name: 'Bob', age: 30 }
```

## 解釋
- **常見問題**：在函數中如果沒有使用 `return`，則函數將默認返回 `undefined`。
- **多次返回**：可以在函數中使用多個 `return` 語句，但一旦執行到某個 `return`，函數將終止，因此後面的 `return` 語句將不會被執行。
- **返回類型不匹配**：如果函數的返回值類型與函數定義的返回類型不一致，TypeScript 將會報錯。例如，定義返回數字的函數卻返回字符串將會導致編譯錯誤。

## 一行摘要
`return` 是 TypeScript 中用於結束函數並返回值的關鍵字，對於數據傳遞至關重要。