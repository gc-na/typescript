<!--
Meta Description: # TypeScript 中的 "of" 關鍵字使用詳解 ## 簡介 在 TypeScript 中，"of" 是一個用於遍歷集合的關鍵字，特別是在 `for...of` 循環中。這個語法能夠讓開發者更加簡潔地遍歷數組、字串、集合和其他可迭代對象。 ## 文檔 ### 目的 `for...of` 循環...
Meta Keywords: typescript, const, map, element, console
-->

# TypeScript 中的 "of" 關鍵字使用詳解

## 簡介
在 TypeScript 中，"of" 是一個用於遍歷集合的關鍵字，特別是在 `for...of` 循環中。這個語法能夠讓開發者更加簡潔地遍歷數組、字串、集合和其他可迭代對象。

## 文檔
### 目的
`for...of` 循環提供了一種簡單的方式來迭代可迭代對象，例如數組、字串、Map 和 Set。與傳統的 `for` 循環相比，`for...of` 可以讓代碼更加清晰且易於閱讀。

### 使用方式
基本語法如下：
```typescript
for (const element of iterable) {
    // 處理 element
}
```
- `element` 是每次迭代時可迭代對象中的當前項。
- `iterable` 是任何實現了可迭代協定的對象，例如數組或字串。

### 詳細說明
`for...of` 循環的使用方式非常靈活，適用於各種可迭代對象。這使得它在處理數據時非常方便，特別是在需要對每個元素進行操作的情況下。

## 示例
以下是 `for...of` 的基本使用示例：

### 示例 1：遍歷數組
```typescript
const numbers = [1, 2, 3, 4, 5];
for (const num of numbers) {
    console.log(num); // 輸出 1, 2, 3, 4, 5
}
```

### 示例 2：遍歷字串
```typescript
const greeting = "Hello";
for (const char of greeting) {
    console.log(char); // 輸出 H, e, l, l, o
}
```

### 示例 3：遍歷 Map
```typescript
const map = new Map([
    ['a', 1],
    ['b', 2],
    ['c', 3]
]);
for (const [key, value] of map) {
    console.log(`${key}: ${value}`); // 輸出 a: 1, b: 2, c: 3
}
```

## 解釋
在使用 `for...of` 時，需要注意以下幾點：
- `for...of` 只能用於可迭代對象，若嘗試用於非可迭代對象，將會拋出錯誤。
- 與 `for...in` 不同，`for...of` 是用於獲取值而不是索引。
- 在處理大型數據集時，`for...of` 可能會比傳統的 `for` 循環略慢，因為它需要創建迭代器。

## 一行總結
`for...of` 是 TypeScript 中用於簡單遍歷可迭代對象的強大工具。