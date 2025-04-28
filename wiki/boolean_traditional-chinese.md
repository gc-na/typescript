<!--
Meta Description: # TypeScript 中的布林值 (Boolean) 解析與應用 ## 簡介 在 TypeScript 中，布林值（Boolean）是最基本的數據類型之一，用於表示真（true）或假（false）的狀態。這一類型在控制流、條件判斷及邏輯運算中扮演著重要角色。 ## 文檔 布林值在 TypeScr...
Meta Keywords: typescript, boolean, console, log, isadmin
-->

# TypeScript 中的布林值 (Boolean) 解析與應用

## 簡介
在 TypeScript 中，布林值（Boolean）是最基本的數據類型之一，用於表示真（true）或假（false）的狀態。這一類型在控制流、條件判斷及邏輯運算中扮演著重要角色。

## 文檔
布林值在 TypeScript 中的主要目的是用來進行邏輯運算和條件判斷。TypeScript 的布林值與 JavaScript 相同，且可以直接用於流程控制語句，如 `if`、`while` 和邏輯運算符。

### 用法
在 TypeScript 中，您可以通過以下方式來定義布林值：
```typescript
let isActive: boolean = true;
let isCompleted: boolean = false;
```

### 詳細說明
布林值可以用於多種情境，包括但不限於：
- 控制程式流程（例如，根據某個條件執行代碼）
- 在函數中作為返回值
- 在類別屬性中，作為狀態標記

TypeScript 會在編譯階段檢查布林值的正確性，以防止錯誤的類型分配。例如，將一個數字賦值給布林變數將會引發錯誤：
```typescript
let isActive: boolean = 1; // 錯誤：型別不正確
```

## 範例
以下是使用布林值的基本範例：

### 範例 1：基本使用
```typescript
let isLoggedIn: boolean = false;

if (isLoggedIn) {
    console.log("使用者已登入");
} else {
    console.log("使用者尚未登入");
}
```

### 範例 2：函數返回布林值
```typescript
function isEven(num: number): boolean {
    return num % 2 === 0;
}

console.log(isEven(4)); // 輸出: true
console.log(isEven(5)); // 輸出: false
```

### 範例 3：布林值作為類別屬性
```typescript
class User {
    isAdmin: boolean;

    constructor(isAdmin: boolean) {
        this.isAdmin = isAdmin;
    }

    checkAdmin() {
        return this.isAdmin ? "用戶是管理員" : "用戶不是管理員";
    }
}

const user = new User(true);
console.log(user.checkAdmin()); // 輸出: 用戶是管理員
```

## 解釋
在使用布林值時，常見的陷阱包括：
- 將其他類型（如數字或字符串）賦值給布林值，這會導致編譯錯誤。
- 在條件表達式中，使用非布林值的表達式時，可能會導致意想不到的行為（例如，使用 `null` 或 `undefined`）。
- 忽略布林值的初始值設定，可能會導致程式執行時出現錯誤。

使用 TypeScript 時，建議始終明確定義變數的類型，以避免潛在的錯誤和不必要的調試。

## 一句總結
布林值是 TypeScript 中用於表示真或假的基本數據類型，廣泛應用於邏輯運算和條件判斷中。