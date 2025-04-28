<!--
Meta Description: # TypeScript 中的 `return` 關鍵字 ## 概述 `return` 是 TypeScript 中用於從函數返回值的關鍵字。它對於控制函數的執行流程和傳遞結果至關重要。 ## 文檔 在 TypeScript 中，`return` 用於結束函數的執行並返回一個值。當函數被調用時，`r...
Meta Keywords: typescript, return, function, number, hello
-->

# TypeScript 中的 `return` 關鍵字

## 概述
`return` 是 TypeScript 中用於從函數返回值的關鍵字。它對於控制函數的執行流程和傳遞結果至關重要。

## 文檔
在 TypeScript 中，`return` 用於結束函數的執行並返回一個值。當函數被調用時，`return` 關鍵字後面可以跟隨一個表達式，這個表達式的計算結果將成為函數的返回值。如果函數沒有明確指定返回值，則默認返回 `undefined`。

### 用法
- **基本語法**：
  ```typescript
  function functionName(parameters): returnType {
      // 函數邏輯
      return value;
  }
  ```

- **返回類型**：
  在 TypeScript 中，可以通過函數的返回類型來限制返回的值。例如：
  ```typescript
  function add(a: number, b: number): number {
      return a + b;
  }
  ```

- **無返回值的函數**：
  如果函數不需要返回值，可以使用 `void` 作為返回類型：
  ```typescript
  function log(message: string): void {
      console.log(message);
      return; // 可選的
  }
  ```

## 示例
以下是一些基本的使用示例：

1. 返回數字的函數：
   ```typescript
   function multiply(x: number, y: number): number {
       return x * y;
   }

   const result = multiply(4, 5); // result 為 20
   ```

2. 返回字串的函數：
   ```typescript
   function greet(name: string): string {
       return `Hello, ${name}!`;
   }

   const greeting = greet('Alice'); // greeting 為 "Hello, Alice!"
   ```

3. 不返回值的函數：
   ```typescript
   function sayHello(): void {
       console.log("Hello!");
   }

   sayHello(); // 在控制台輸出 "Hello!"
   ```

## 解釋
- **常見陷阱**：
  1. **未返回值的情況**：如果函數聲明了返回類型，但沒有使用 `return` 返回值，TypeScript 會報告錯誤。
  2. **返回不匹配的類型**：如果返回的值類型與函數聲明的返回類型不匹配，TypeScript 會顯示類型錯誤。
  
- **注意事項**：
  - 使用 `return` 時，函數的執行會直接終止，並返回指定的值。
  - 在某些情況下，可能會有多個 `return` 陳述，這會使函數更具可讀性。

## 一句總結
在 TypeScript 中，`return` 關鍵字用於結束函數執行並返回一個指定的值。