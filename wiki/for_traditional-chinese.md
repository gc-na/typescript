<!--
Meta Description: # TypeScript 中的 for 迴圈：語法與應用 ## 摘要 在 TypeScript 中，`for` 迴圈是一種用來重複執行特定代碼塊的基本結構，廣泛用於遍歷數組和對象等可迭代的資料結構。 ## 文件說明 `for` 迴圈的主要目的是提供一種簡單而高效的方式來重複執行代碼。其基本語法如下：...
Meta Keywords: typescript, let, console, log, fruits
-->

# TypeScript 中的 for 迴圈：語法與應用

## 摘要
在 TypeScript 中，`for` 迴圈是一種用來重複執行特定代碼塊的基本結構，廣泛用於遍歷數組和對象等可迭代的資料結構。

## 文件說明
`for` 迴圈的主要目的是提供一種簡單而高效的方式來重複執行代碼。其基本語法如下：

```typescript
for (初始化; 條件; 迭代) {
    // 執行的代碼
}
```

### 語法詳細說明：
- **初始化**：在迴圈開始之前執行的表達式，通常用來定義和初始化計數器變數。
- **條件**：每次迴圈執行前評估的布林表達式。如果為 `true`，則執行迴圈內的代碼；如果為 `false`，則結束迴圈。
- **迭代**：每次執行完迴圈內的代碼後執行的表達式，通常用來更新計數器。

## 範例
以下是幾個使用 `for` 迴圈的基本範例：

### 範例 1：簡單計數
```typescript
for (let i = 0; i < 5; i++) {
    console.log(i);  // 輸出：0, 1, 2, 3, 4
}
```

### 範例 2：遍歷數組
```typescript
const fruits: string[] = ['蘋果', '香蕉', '橘子'];
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);  // 輸出：蘋果, 香蕉, 橘子
}
```

### 範例 3：計算總和
```typescript
const numbers: number[] = [1, 2, 3, 4, 5];
let total: number = 0;
for (let i = 0; i < numbers.length; i++) {
    total += numbers[i];
}
console.log(total);  // 輸出：15
```

## 解釋
在使用 `for` 迴圈時，有幾個常見的注意事項：

1. **不正確的條件**：如果條件永遠為 `true`，將造成無窮迴圈，導致程式無法正常運行。
2. **計數器的範圍**：確保計數器的初始值和更新邏輯正確，以避免訪問數組或集合的無效索引。
3. **變數作用域**：在 TypeScript 中，使用 `let` 定義計數器時，它的作用域僅限於迴圈內部；若使用 `var`，則會在整個函數內有效。

## 一行總結
TypeScript 中的 `for` 迴圈是一種強大的結構，用於重複執行代碼，特別適合遍歷集合和數組。