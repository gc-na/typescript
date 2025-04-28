<!--
Meta Description: # TypeScript中的列舉（Enum）：使用指南與示例 ## 概述 在TypeScript中，列舉（Enum）是一種特殊的數據類型，用於定義一組命名的常量，這使得代碼更具可讀性和可維護性。列舉可以幫助開發者以更清晰的方式處理一組相關的數值或字符串。 ## 文檔 ### 目的 TypeScrip...
Meta Keywords: enum, typescript, yes, weekday, response
-->

# TypeScript中的列舉（Enum）：使用指南與示例

## 概述
在TypeScript中，列舉（Enum）是一種特殊的數據類型，用於定義一組命名的常量，這使得代碼更具可讀性和可維護性。列舉可以幫助開發者以更清晰的方式處理一組相關的數值或字符串。

## 文檔
### 目的
TypeScript的列舉（Enum）提供了一種簡單的方式來定義一組具有相關性的常量，使得代碼中使用這些常量時更加明確。這種結構不僅提高了代碼的可讀性，還減少了出錯的機會。

### 使用方法
在TypeScript中，可以使用`enum`關鍵字來定義列舉。列舉的基本語法如下：

```typescript
enum EnumName {
    Constant1,
    Constant2,
    Constant3,
}
```

### 詳細信息
- **自動賦值**：列舉中的常量會自動從0開始賦值，依次遞增。例如，`Constant1`為0，`Constant2`為1，以此類推。
- **自定義賦值**：也可以為列舉中的常量手動賦值，如下所示：
  
```typescript
enum Color {
    Red = 1,
    Green = 2,
    Blue = 4,
}
```

- **字串列舉**：除了數字列舉，TypeScript還支持字串列舉，適合需要使用字符串進行比較的場景：

```typescript
enum Direction {
    Up = "UP",
    Down = "DOWN",
    Left = "LEFT",
    Right = "RIGHT",
}
```

## 示例
### 基本用法
以下是一個簡單的列舉示例，展示如何定義和使用列舉：

```typescript
enum Weekday {
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday,
}

let today: Weekday = Weekday.Monday;
console.log(today); // 輸出：1
```

### 字串列舉示例
```typescript
enum Response {
    Yes = "YES",
    No = "NO",
}

let answer: Response = Response.Yes;
console.log(answer); // 輸出：YES
```

## 說明
### 常見陷阱
- **重複定義**：注意在同一個列舉中不應有重複的常量名稱，否則會導致編譯錯誤。
- **自動賦值的理解**：當不手動賦值時，列舉的數值會自動從0開始遞增，這可能與開發者的預期不符。
- **字串列舉的使用場景**：在需要進行比較的場景下，字串列舉比數字列舉更為適合，因為它們不會發生隱式轉換。

## 總結
TypeScript中的列舉（Enum）是一種強大且靈活的工具，用於定義一組相關的常量，從而提高代碼的可讀性與可維護性。