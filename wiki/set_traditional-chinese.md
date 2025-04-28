<!--
Meta Description: # TypeScript 中的 Set：資料結構與應用 ## 摘要 在 TypeScript 中，`Set` 是一種用於儲存唯一值的資料結構，提供高效的插入、刪除及查詢操作。`Set` 支援各種資料類型，使其成為處理集合數據的理想選擇。 ## 文檔 `Set` 是 ES6 引入的資料結構，允許儲存不...
Meta Keywords: set, numbers, typescript, add, console
-->

# TypeScript 中的 Set：資料結構與應用

## 摘要
在 TypeScript 中，`Set` 是一種用於儲存唯一值的資料結構，提供高效的插入、刪除及查詢操作。`Set` 支援各種資料類型，使其成為處理集合數據的理想選擇。

## 文檔
`Set` 是 ES6 引入的資料結構，允許儲存不重複的值。與陣列不同，`Set` 的每個值都是唯一的，並且無法重複。這使得 `Set` 成為處理需要確保唯一性資料的理想選擇，如用戶 ID、標籤或其他獨特標識。

### 目的
`Set` 的主要目的是提供一個可儲存唯一值的集合，便於高效地進行資料存取、查詢及操作。

### 使用方式
在 TypeScript 中，我們可以使用 `Set` 來創建一個集合，並利用其內建的方法來操作資料。其基本語法如下：

```typescript
const mySet = new Set<Type>();
```

### 方法
- **add(value)**：將新元素添加到 `Set` 中。
- **delete(value)**：從 `Set` 中刪除指定元素。
- **has(value)**：檢查 `Set` 是否包含指定元素，返回布林值。
- **clear()**：清空 `Set` 中的所有元素。
- **size**：獲取 `Set` 中元素的數量。

## 範例
以下是幾個使用 `Set` 的基本範例：

```typescript
// 創建一個 Set
const numbers = new Set<number>();

// 添加元素
numbers.add(1);
numbers.add(2);
numbers.add(3);
numbers.add(2); // 不會被添加，因為 2 已存在

console.log(numbers.size); // 輸出：3

// 檢查元素是否存在
console.log(numbers.has(2)); // 輸出：true
console.log(numbers.has(4)); // 輸出：false

// 刪除元素
numbers.delete(2);
console.log(numbers.has(2)); // 輸出：false

// 清空 Set
numbers.clear();
console.log(numbers.size); // 輸出：0
```

## 解釋
在使用 `Set` 時，有幾個常見的陷阱和注意事項：

1. **類型一致性**：`Set` 可以儲存任何資料型別，但在 TypeScript 中，確保添加到 `Set` 的值類型一致很重要，以避免類型錯誤。
   
2. **引用類型**：對於物件和陣列，`Set` 是基於引用比較的，這意味著兩個擁有相同內容的物件仍然被視為不同元素。

3. **性能**：`Set` 的查詢性能通常優於陣列，特別是在處理大資料集時。

4. **迭代**：`Set` 支援迭代，可以使用 `forEach` 或 `for...of` 進行遍歷。

## 一句總結
TypeScript 中的 `Set` 是一種高效的資料結構，用於儲存唯一值並提供便捷的操作方法。