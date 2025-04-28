<!--
Meta Description: # TypeScript 中的 Set：全面指南與使用示例 ## 概覽 `Set` 是一種內建的集合數據結構，允許你儲存唯一的值。它在 TypeScript 和 JavaScript 中被廣泛應用，適合用來儲存不重複的數據。 ## 文檔 在 TypeScript 中，`Set` 是一個類似於陣列的數...
Meta Keywords: set, myset, has, console, log
-->

# TypeScript 中的 Set：全面指南與使用示例

## 概覽
`Set` 是一種內建的集合數據結構，允許你儲存唯一的值。它在 TypeScript 和 JavaScript 中被廣泛應用，適合用來儲存不重複的數據。

## 文檔
在 TypeScript 中，`Set` 是一個類似於陣列的數據結構，但不同的是，`Set` 只允許儲存唯一的值。這意味著，如果你嘗試加入一個已經存在的值，這個值不會被重複添加。`Set` 主要用於需要確保數據唯一性的場景。

### 目的
使用 `Set` 的目的在於保持數據的唯一性，並提供高效的查找和操作性能。

### 使用法
要使用 `Set`，你需要先創建一個新的 `Set` 實例，然後可以使用 `add` 方法添加元素，使用 `has` 方法檢查元素是否存在，使用 `delete` 方法刪除元素，還有其他相關方法。

```typescript
const mySet = new Set<number>();

// 添加元素
mySet.add(1);
mySet.add(2);
mySet.add(2); // 不會被添加

// 檢查元素
console.log(mySet.has(1)); // true
console.log(mySet.has(3)); // false

// 刪除元素
mySet.delete(1);
console.log(mySet.has(1)); // false
```

### 詳細
- **初始化**：可以使用 `new Set()` 創建一個空的集合，或是傳遞一個可迭代的對象來初始化。
- **方法**：
  - `add(value)`：向集合中添加一個新元素。
  - `delete(value)`：刪除指定的元素。
  - `has(value)`：檢查集合中是否存在該元素。
  - `clear()`：清空集合。
  - `size`：屬性，返回集合中的元素數量。

## 示例
以下是一些基本的使用示例：

```typescript
// 創建一個 Set 並添加數字
const numberSet = new Set<number>([1, 2, 3, 4, 5]);

// 添加重複元素
numberSet.add(3); // 3 不會被重新添加

// 輸出 Set 的大小
console.log(numberSet.size); // 5

// 檢查是否存在元素
console.log(numberSet.has(2)); // true
console.log(numberSet.has(6)); // false

// 刪除元素
numberSet.delete(4);
console.log(numberSet.size); // 4
```

## 解釋
常見的陷阱包括：
- 如果你添加的值是對象或陣列，`Set` 會根據引用進行比較，這可能造成意想不到的行為。
- `Set` 的元素是無序的，這意味著你不能依賴元素的插入順序。
- 使用 `Set` 時，記得檢查是否已經存在元素，以避免不必要的操作。

## 一句總結
`Set` 是 TypeScript 中用來儲存唯一元素的高效數據結構，適合用於需要保持數據唯一性的場景。