<!--
Meta Description: # TypeScript Enum：深入了解 TypeScript 的枚舉類型 ## 概述 TypeScript 的枚舉（enum）是一種特殊的資料類型，它允許開發者定義一組命名的常數。這對於提高程式碼的可讀性和可維護性非常有幫助，尤其在處理一組相關的值時。 ## 文檔 枚舉提供了一種方式來給一組數...
Meta Keywords: typescript, enum, cat, direction, let
-->

# TypeScript Enum：深入了解 TypeScript 的枚舉類型

## 概述
TypeScript 的枚舉（enum）是一種特殊的資料類型，它允許開發者定義一組命名的常數。這對於提高程式碼的可讀性和可維護性非常有幫助，尤其在處理一組相關的值時。

## 文檔
枚舉提供了一種方式來給一組數字或字串常數命名，這樣可以使代碼更具可讀性。TypeScript 的枚舉有三種類型：數字枚舉、字串枚舉和異構枚舉（同時包含數字和字串）。

### 定義
在 TypeScript 中，您可以使用 `enum` 關鍵字來定義一個枚舉：

```typescript
enum Direction {
    Up,
    Down,
    Left,
    Right
}
```

### 使用
使用枚舉時，您可以通過枚舉的名稱來引用相應的值。例如：

```typescript
let move: Direction = Direction.Up;
```

### 預設值
數字枚舉的預設值從 `0` 開始自動遞增，您也可以自定義起始值：

```typescript
enum Status {
    Active = 1,
    Inactive,
    Pending
}
```

字串枚舉則需要顯式賦值：

```typescript
enum FileStatus {
    Open = "OPEN",
    Closed = "CLOSED",
    Pending = "PENDING"
}
```

## 範例
以下是一些枚舉的基本使用範例：

### 數字枚舉範例
```typescript
enum Color {
    Red = 1,
    Green,
    Blue
}

let myColor: Color = Color.Green;
console.log(myColor); // 輸出 2
```

### 字串枚舉範例
```typescript
enum Animal {
    Dog = "DOG",
    Cat = "CAT",
    Fish = "FISH"
}

let myPet: Animal = Animal.Cat;
console.log(myPet); // 輸出 "CAT"
```

## 說明
在使用枚舉時，開發者應注意以下幾點：

1. **重複值**：在數字枚舉中，可以為不同的成員指定相同的數字值，但這可能會導致混淆。
   
   ```typescript
   enum ErrorCode {
       NotFound = 404,
       Unauthorized = 401,
       Forbidden = 403,
       Duplicate = 404 // 重複值
   }
   ```

2. **使用場景**：應用於需要一組固定選擇的情況，如狀態碼、方向等，避免過度使用以免增加程式碼的複雜性。

3. **型別安全**：枚舉能提高型別安全性，避免使用魔法數字或字串，從而減少錯誤可能性。

## 總結
TypeScript 的枚舉（enum）是一種強大的工具，能幫助開發者以可讀的方式管理一組相關的常數值。