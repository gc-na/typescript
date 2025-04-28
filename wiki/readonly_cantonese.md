<!--
Meta Description: # TypeScript 嘅 readonly 屬性：一個詳細指南 ## 摘要 `readonly` 係 TypeScript 中一個重要嘅關鍵字，佢用嚟定義只能讀取而不能修改嘅屬性，從而提高代碼嘅安全性同可維護性。 ## 文檔 `readonly` 關鍵字可以用喺類別屬性、介面屬性同陣列元素上。當...
Meta Keywords: readonly, typescript, user, number, point
-->

# TypeScript 嘅 readonly 屬性：一個詳細指南

## 摘要
`readonly` 係 TypeScript 中一個重要嘅關鍵字，佢用嚟定義只能讀取而不能修改嘅屬性，從而提高代碼嘅安全性同可維護性。

## 文檔
`readonly` 關鍵字可以用喺類別屬性、介面屬性同陣列元素上。當一個屬性被標記為 `readonly` 時，呢個屬性只能喺聲明時或者構造函數中初始化，之後就唔可以再修改。呢個功能主要用來防止意外修改對象嘅狀態，特別係喺大型應用程式中。

### 用法
- **類別**：可以使用 `readonly` 定義類別屬性，確保佢哋喺實例創建後無法被改變。
- **介面**：可以喺介面中定義 `readonly` 屬性，強制實現該介面的類別遵循只讀約束。
- **陣列**：可以使用 `ReadonlyArray<T>` 來定義只讀陣列，確保陣列嘅內容唔會被修改。

## 示例
### 類別中的 `readonly` 屬性
```typescript
class User {
    readonly id: number;
    name: string;

    constructor(id: number, name: string) {
        this.id = id;
        this.name = name;
    }
}

const user = new User(1, "Alice");
console.log(user.id); // 1
user.id = 2; // 錯誤：無法分配到 'id'，因為它是只讀屬性
```

### 介面中的 `readonly` 屬性
```typescript
interface Point {
    readonly x: number;
    readonly y: number;
}

const point: Point = { x: 10, y: 20 };
console.log(point.x); // 10
point.x = 15; // 錯誤：無法分配到 'x'，因為它是只讀屬性
```

### 只讀陣列
```typescript
const numbers: ReadonlyArray<number> = [1, 2, 3];
numbers.push(4); // 錯誤：推送到只讀數組中
```

## 解釋
使用 `readonly` 時，有幾個常見嘅陷阱需要注意：
1. **層級只讀**：如果一個物件的某個屬性是只讀的，但這個屬性本身是一個物件，則內部屬性仍然可以被修改。要實現深層只讀，可能需要使用不變數據結構。
2. **類型不匹配**：在使用 `readonly` 時，確保屬性類型與初始化值類型相符，否則會引發類型錯誤。
3. **只讀陣列限制**：`ReadonlyArray<T>` 陣列無法修改，但仍然可以進行讀取操作。

## 一句總結
`readonly` 係 TypeScript 中一個強大嘅工具，能夠幫助開發者確保物件屬性嘅不可變性，從而增強代碼質量同可維護性。