<!--
Meta Description: # TypeScript 中的 "unique" 類型概念解析 ## 簡介 在 TypeScript 中，"unique" 類型是一個重要的特性，用來確保某個值在特定上下文中是唯一的，這對於維護資料的一致性和安全性至關重要。 ## 文檔 ### 目的 "unique" 類型在 TypeScript ...
Meta Keywords: unique, symbol, typescript, userid, const
-->

# TypeScript 中的 "unique" 類型概念解析

## 簡介
在 TypeScript 中，"unique" 類型是一個重要的特性，用來確保某個值在特定上下文中是唯一的，這對於維護資料的一致性和安全性至關重要。

## 文檔
### 目的
"unique" 類型在 TypeScript 中的主要目的是提供一種方法來標記某些類型的變數，使其在類型層面上具有唯一性，從而避免混淆和錯誤。

### 用法
在 TypeScript 中，可以通過使用 **`unique symbol`** 來創建唯一的標識符。這是一種特殊的符號類型，只能通過專門的聲明來創建，並且每次創建的 `unique symbol` 都是獨一無二的。

### 詳細信息
- **聲明**: 使用 `const` 關鍵字來聲明一個 `unique symbol`，例如：
  ```typescript
  const uniqueId: unique symbol = Symbol("uniqueId");
  ```
- **類型檢查**: 使用 `unique` 類型可以幫助 TypeScript 在編譯階段進行類型檢查，確保在不同的上下文中不會混淆相同名稱的標識符。

## 範例
以下是使用 `unique symbol` 的基本範例：

```typescript
const userId: unique symbol = Symbol("userId");

function getUserById(id: typeof userId) {
    // 這裡的 id 只能是 userId
    console.log(`Fetching user with ID: ${id.toString()}`);
}

getUserById(userId); // 正確的用法
// getUserById(Symbol("differentId")); // 錯誤的用法，會報錯
```

## 解釋
- **常見陷阱**: 在使用 `unique symbol` 時，務必記住每個 `unique symbol` 都是獨一無二的，不能重新賦值或復用。
- **誤解**: 有人可能會混淆 `unique symbol` 與普通的 `symbol`，但後者的實例可以被多次創建，而 `unique symbol` 的實例則無法相互替代。

## 總結
"unique" 類型在 TypeScript 中提供了一種強大的方式來確保變數的唯一性，有助於提升代碼的安全性和可讀性。