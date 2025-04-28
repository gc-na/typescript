<!--
Meta Description: # TypeScript 中的 const：用法與注意事項 ## 簡介 在 TypeScript 中，`const` 是用來聲明變數的一種關鍵字。它表示變數的值是常數，不會被重新賦值，這使得在編寫代碼時能夠增加可讀性和安全性。 ## 文檔 ### 目的 `const` 的主要目的是聲明一個常量，即一...
Meta Keywords: const, typescript, person, age, type
-->

# TypeScript 中的 const：用法與注意事項

## 簡介
在 TypeScript 中，`const` 是用來聲明變數的一種關鍵字。它表示變數的值是常數，不會被重新賦值，這使得在編寫代碼時能夠增加可讀性和安全性。

## 文檔
### 目的
`const` 的主要目的是聲明一個常量，即一旦賦值後就不能再改變其指向。這對於需要保持不變的數據（例如配置參數或數學常數）特別有用。

### 用法
在 TypeScript 中，使用 `const` 聲明變數的語法如下：

```typescript
const variableName: type = value;
```

這裡的 `type` 是可選的，TypeScript 可以根據賦值自動推斷類型。

### 詳細說明
- 使用 `const` 聲明的變量必須在聲明時初始化。
- `const` 適用於原始數據類型（如數字、字符串和布爾值）以及引用類型（如對象和數組）。
- 對於引用類型，`const` 只保證變量的引用不會改變，但對於引用的對象內容卻是可以修改的。

## 示例
### 基本用法
1. 聲明一個數字常量：
   ```typescript
   const pi: number = 3.14;
   ```

2. 聲明一個字符串常量：
   ```typescript
   const greeting: string = "Hello, TypeScript!";
   ```

3. 聲明一個對象常量：
   ```typescript
   const person = {
       name: "John",
       age: 30
   };
   ```

   修改對象內容：
   ```typescript
   person.age = 31; // 這是可以的
   ```

   嘗試重新賦值將會出錯：
   ```typescript
   // person = { name: "Doe", age: 25 }; // 錯誤：不能重新賦值
   ```

## 解釋
### 常見陷阱
- **未初始化的常量**：聲明 `const` 變量時必須立即初始化，否則會導致編譯錯誤。
- **引用類型的誤解**：雖然 `const` 保證變量的引用不變，但對於對象的內容仍然可以修改，這可能會導致不必要的錯誤。

### 注意事項
- `const` 除了用於變量聲明，還可以用於函數表達式和數組。
- 因為 `const` 使變量變得不可重新賦值，這對於避免意外的變量重寫非常有幫助。

## 一句總結
在 TypeScript 中，`const` 用來聲明不可變的變量，增強代碼的安全性和可讀性。