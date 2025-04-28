<!--
Meta Description: # TypeScript 中的「型別」(Type) 詳解 ## 簡介 在 TypeScript 中，「型別」是一個關鍵概念，幫助開發者定義變數、函數、物件等的數據形態，以提高代碼的可讀性和可維護性。 ## 文檔 「型別」在 TypeScript 的主要目的是提供靜態類型檢查，這樣可以在編譯階段捕捉錯...
Meta Keywords: typescript, number, let, string, type
-->

# TypeScript 中的「型別」(Type) 詳解

## 簡介
在 TypeScript 中，「型別」是一個關鍵概念，幫助開發者定義變數、函數、物件等的數據形態，以提高代碼的可讀性和可維護性。

## 文檔
「型別」在 TypeScript 的主要目的是提供靜態類型檢查，這樣可以在編譯階段捕捉錯誤，從而減少運行時錯誤。TypeScript 支持多種型別，包括基本型別（如 `string`、`number`、`boolean`）、複合型別（如 `array`、`tuple`、`enum`）、自定義型別（如 `interface` 和 `type alias`）等。

### 使用方式
1. **基本型別**: 
   - `number`: 數字型別。
   - `string`: 字符串型別。
   - `boolean`: 布林型別。
2. **複合型別**:
   - `array`: 可包含多個相同型別的元素。
   - `tuple`: 限定數量和型別的數組。
   - `enum`: 定義一組命名常數。
3. **自定義型別**:
   - `interface`: 定義物件的結構。
   - `type alias`: 為型別創建別名。

## 例子
### 基本型別
```typescript
let age: number = 25;
let name: string = "Alice";
let isStudent: boolean = true;
```

### 複合型別
```typescript
let scores: number[] = [90, 80, 75];
let person: [string, number] = ["Bob", 30];
enum Direction {
    Up,
    Down,
    Left,
    Right
}
```

### 自定義型別
```typescript
interface User {
    id: number;
    username: string;
}

type Point = {
    x: number;
    y: number;
};

let user: User = { id: 1, username: "Charlie" };
let point: Point = { x: 10, y: 20 };
```

## 解釋
使用型別的時候，開發者需要注意以下幾點：
1. **型別推斷**: TypeScript 能夠自動推斷型別，但有時候顯式指定型別能提升代碼的可讀性。
2. **聯合型別**: 可以使用 `|` 符號定義多種可能的型別，例如 `string | number`。
3. **型別不匹配**: 若一個變數被賦予不符合其型別的值，編譯器會報錯。

## 一句總結
在 TypeScript 中，「型別」是定義數據形態的重要工具，有助於提升代碼安全性和可維護性。