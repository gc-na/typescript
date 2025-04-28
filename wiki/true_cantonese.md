<!--
Meta Description: # TypeScript 中的 "true" 值的詳細介紹 ## 概述 在 TypeScript 中，`true` 是一個布爾值，表示真相的狀態。它是 TypeScript 基本數據類型之一，廣泛應用於邏輯運算和條件判斷中。 ## 文檔 ### 目的 `true` 值的主要目的是用於表示邏輯上的真。...
Meta Keywords: true, typescript, boolean, let, false
-->

# TypeScript 中的 "true" 值的詳細介紹

## 概述
在 TypeScript 中，`true` 是一個布爾值，表示真相的狀態。它是 TypeScript 基本數據類型之一，廣泛應用於邏輯運算和條件判斷中。

## 文檔
### 目的
`true` 值的主要目的是用於表示邏輯上的真。它在 TypeScript 的類型系統中扮演著重要角色，特別是在控制流程和條件語句中。

### 使用方法
在 TypeScript 中，`true` 可以直接作為布爾型變量的賦值使用。以下是 `true` 的基本用法：

```typescript
let isActive: boolean = true;
```

### 詳細說明
- **數據類型**: `true` 是 Boolean 類型的其中一個值，另外一個值是 `false`。
- **條件語句**: `true` 經常用於 `if` 語句、循環和其他條件邏輯中，以控制代碼的執行流。
- **邏輯運算**: 在邏輯運算中，`true` 與 `false` 可用於進行 AND (`&&`)、OR (`||`) 和 NOT (`!`) 等運算。

## 範例
### 基本用法
以下是一些使用 `true` 的簡單範例：

```typescript
let isLoggedIn: boolean = true;

if (isLoggedIn) {
    console.log("用戶已登入");
} else {
    console.log("用戶尚未登入");
}
```

### 與邏輯運算搭配
```typescript
let hasAccess: boolean = true;
let isAdmin: boolean = false;

if (hasAccess && !isAdmin) {
    console.log("用戶有訪問權限，但不是管理員");
}
```

## 解釋
### 常見陷阱
- **類型不匹配**: 確保變量類型正確設置為 `boolean`，否則可能導致意外的行為。
- **用於非布爾上下文**: 在某些情況下，將 `true` 用於非布爾上下文（例如數學運算）會引起錯誤，因為 TypeScript 不會自動進行類型轉換。

### 附加說明
- `true` 與 `false` 是獨立的布爾值，並且在使用時必須明確。
- 使用 `===` 進行比較時，`true` 的比較對象必須是布爾類型，這樣才能避免類型隱式轉換帶來的問題。

## 一句話總結
在 TypeScript 中，`true` 是一個表示真值的布爾型常量，廣泛用於邏輯運算和條件判斷中。