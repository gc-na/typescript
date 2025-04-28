<!--
Meta Description: # TypeScript 字串 (String) 的詳細介紹 ## 概要 在 TypeScript 中，字串（String）是用來表示文本數據的基本數據類型。字串是不可變的，這意味著一旦創建，字串的值無法更改。 ## 文檔 字串是 TypeScript 中的基本數據類型之一，類似於 JavaScri...
Meta Keywords: string, typescript, let, greeting, console
-->

# TypeScript 字串 (String) 的詳細介紹

## 概要
在 TypeScript 中，字串（String）是用來表示文本數據的基本數據類型。字串是不可變的，這意味著一旦創建，字串的值無法更改。

## 文檔
字串是 TypeScript 中的基本數據類型之一，類似於 JavaScript。它們可以用單引號 (`'`)、雙引號 (`"`)、或反引號 (`` ` ``) 來創建。反引號允許多行字串和內嵌表達式，這使得字串的操作更加靈活。

### 用法
在 TypeScript 中聲明字串的基本語法如下：

```typescript
let greeting: string = "你好，世界！";
```

TypeScript 會自動推斷字串類型，除非明確指定。可以使用字串的多種方法，例如：

- `.length` 獲取字串長度
- `.toUpperCase()` 和 `.toLowerCase()` 進行大小寫轉換
- `.trim()` 去除字串前後的空格

### 詳細說明
字串可以通過字串連接（使用 `+` 符號）來合併，並且可以使用模板字串來更方便地插入變量。例如：

```typescript
let name: string = "小明";
let message: string = `你好，${name}！`;
```

這樣的方式使得字串的拼接和插入變量更加直觀。

## 示例
以下是一些基本的字串操作範例：

```typescript
// 基本字串聲明
let greeting: string = "你好！";

// 字串長度
console.log(greeting.length);  // 輸出: 6

// 字串轉換
let lowerCaseGreeting: string = greeting.toLowerCase();
console.log(lowerCaseGreeting); // 輸出: 你好！

// 字串連接
let welcomeMessage: string = greeting + "歡迎你的到來！";
console.log(welcomeMessage); // 輸出: 你好！歡迎你的到來！

// 使用模板字串
let userName: string = "小明";
let userGreeting: string = `你好，${userName}！`;
console.log(userGreeting); // 輸出: 你好，小明！
```

## 解釋
使用字串時，開發者需注意以下幾點：

- 字串是不可變的，這意味著對字串的任何操作都將返回一個新的字串，而不會改變原有的字串。
- 當使用模板字串時，必須使用反引號包裹，否則將無法插入變量。
- 在字串拼接時，注意性能問題，因為大量字串的連接可能會導致性能下降。對於大量的字串操作，考慮使用陣列來收集字串，然後再使用 `.join()` 方法進行合併。

## 一句總結
TypeScript 的字串數據類型提供了強大的文本處理功能，支持多種操作和靈活的插值方式。