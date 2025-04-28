<!--
Meta Description: # TypeScript 中的 "of" 關鍵字 ## 簡介 在 TypeScript 中，"of" 關鍵字主要出現在 `for...of` 迴圈中，用於遍歷可迭代對象，如數組和字串。這個特性可以讓開發者更加簡潔地進行迭代操作。 ## 文檔 ### 目的 `for...of` 迴圈的主要目的是提供一...
Meta Keywords: typescript, const, map, iterable, console
-->

# TypeScript 中的 "of" 關鍵字

## 簡介
在 TypeScript 中，"of" 關鍵字主要出現在 `for...of` 迴圈中，用於遍歷可迭代對象，如數組和字串。這個特性可以讓開發者更加簡潔地進行迭代操作。

## 文檔
### 目的
`for...of` 迴圈的主要目的是提供一種簡單的方式來遍歷可迭代對象的元素。這使得代碼更具可讀性，減少了錯誤的可能性。

### 用法
`for...of` 的基本語法如下：

```typescript
for (const element of iterable) {
    // 對每個元素進行操作
}
```

其中，`iterable` 是任何可迭代對象，例如數組、字串、Map 或 Set，`element` 是當前迭代的元素。

### 詳情
- `for...of` 迴圈可以用於處理任何實現了 `Iterable` 接口的對象。
- 它會自動處理索引和邊界條件，避免了使用傳統 `for` 迴圈時可能出現的錯誤。
- 這種迴圈的性能相對較好，特別是在處理大型數據結構時。

## 範例
以下是一些基本用法的示例：

### 示例 1：遍歷數組
```typescript
const numbers = [1, 2, 3, 4, 5];
for (const num of numbers) {
    console.log(num); // 輸出：1 2 3 4 5
}
```

### 示例 2：遍歷字串
```typescript
const greeting = "Hello";
for (const char of greeting) {
    console.log(char); // 輸出：H e l l o
}
```

### 示例 3：遍歷 Map
```typescript
const map = new Map([
    ['a', 1],
    ['b', 2],
]);

for (const [key, value] of map) {
    console.log(`${key}: ${value}`); // 輸出：a: 1, b: 2
}
```

## 說明
- **常見陷阱**：`for...of` 不能用於普通對象（Object），因為普通對象不是可迭代對象。使用 `for...in` 迴圈來遍歷對象的屬性會更合適。
- **注意**：對於大型數據結構，`for...of` 迴圈的性能雖然好，但仍需考慮對性能的影響，特別是在深度嵌套的情況下。

## 一句總結
`for...of` 迴圈為 TypeScript 提供了一種簡潔且高效的方式來遍歷可迭代對象。