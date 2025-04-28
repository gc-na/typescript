<!--
Meta Description: # TypeScript 中的函數：全面指南 ## 概述 在 TypeScript 中，函數是執行特定任務的代碼塊。它們可以接受輸入並返回輸出，並且是構建應用程序邏輯的重要組成部分。 ## 文檔 ### 目的 函數允許開發者將代碼分割成可重用的部分，從而提高代碼的可讀性和可維護性。TypeScrip...
Meta Keywords: typescript, number, function, return, age
-->

# TypeScript 中的函數：全面指南

## 概述
在 TypeScript 中，函數是執行特定任務的代碼塊。它們可以接受輸入並返回輸出，並且是構建應用程序邏輯的重要組成部分。

## 文檔
### 目的
函數允許開發者將代碼分割成可重用的部分，從而提高代碼的可讀性和可維護性。TypeScript 進一步增強了函數的功能，提供靜態類型檢查和更嚴格的語法規則。

### 使用方法
在 TypeScript 中，函數的基本語法如下：

```typescript
function functionName(parameters: Type): ReturnType {
    // 函數體
    return value;
}
```

- **functionName**：函數的名稱。
- **parameters**：輸入參數及其類型。
- **ReturnType**：函數返回值的類型。

### 詳細信息
TypeScript 允許使用可選參數、默認參數以及剩餘參數來擴展函數的靈活性。此外，函數還可以作為另一個函數的參數或返回值（即高階函數）。

#### 可選參數
可選參數在參數名稱後面加上 `?` 符號：

```typescript
function greet(name: string, age?: number): string {
    return `Hello, ${name}${age ? `, age ${age}` : ''}!`;
}
```

#### 默認參數
默認參數可以為參數指定一個默認值：

```typescript
function multiply(x: number, y: number = 1): number {
    return x * y;
}
```

#### 剩餘參數
使用 `...` 語法來定義剩餘參數：

```typescript
function sum(...numbers: number[]): number {
    return numbers.reduce((acc, num) => acc + num, 0);
}
```

## 示例
以下是一些基本的 TypeScript 函數用法示例：

### 示例 1：基本函數
```typescript
function add(a: number, b: number): number {
    return a + b;
}

console.log(add(2, 3)); // 輸出: 5
```

### 示例 2：可選參數
```typescript
function greet(name: string, age?: number): string {
    return `Hello, ${name}${age ? `, age ${age}` : ''}!`;
}

console.log(greet("Alice")); // 輸出: Hello, Alice!
```

### 示例 3：默認參數
```typescript
function power(base: number, exponent: number = 2): number {
    return base ** exponent;
}

console.log(power(3)); // 輸出: 9
```

### 示例 4：剩餘參數
```typescript
function concatenate(...strings: string[]): string {
    return strings.join(' ');
}

console.log(concatenate("Hello", "World", "!")); // 輸出: Hello World !
```

## 解釋
在使用 TypeScript 函數時，開發者需注意以下幾點：

- **類型不匹配**：如果傳遞的參數類型與函數定義不匹配，TypeScript 將會報錯。
- **返回類型**：確保函數的返回類型與定義一致。
- **上下文中的 this**：當函數作為方法使用時，`this` 的上下文可能會改變，需謹慎處理。

## 一句總結
TypeScript 中的函數是靈活且強大的工具，允許開發者高效地編寫可重用的代碼。