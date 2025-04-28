<!--
Meta Description: # TypeScript 中的「物件」：完整指南與範例 ## 概述 在 TypeScript 中，「物件」是指一組鍵值對的集合。物件是 JavaScript 的核心概念，TypeScript 在此基礎上增加了型別系統，使開發者能更有效地管理和使用物件。 ## 文件說明 ### 目的 「物件」在 Ty...
Meta Keywords: typescript, string, person, name, number
-->

# TypeScript 中的「物件」：完整指南與範例

## 概述
在 TypeScript 中，「物件」是指一組鍵值對的集合。物件是 JavaScript 的核心概念，TypeScript 在此基礎上增加了型別系統，使開發者能更有效地管理和使用物件。

## 文件說明
### 目的
「物件」在 TypeScript 中用於表示複雜的資料結構，提供了一種組織資料及行為的方式。透過 TypeScript 的型別系統，開發者可以定義物件的結構，確保資料的完整性和可讀性。

### 使用方式
在 TypeScript 中，物件的定義可以使用物件型別或介面。以下是定義物件的基本方法：

1. **物件型別定義**：
   ```typescript
   let person: { name: string; age: number } = {
       name: "張三",
       age: 30
   };
   ```

2. **介面定義**：
   ```typescript
   interface Person {
       name: string;
       age: number;
   }

   let person: Person = {
       name: "張三",
       age: 30
   };
   ```

### 詳細解釋
在 TypeScript 中，物件可以包含各種資料型別，包括字串、數字、布林值、陣列、甚至其他物件。透過使用介面，開發者可以定義物件的形狀，並在需要時進行擴展。

#### 物件的屬性
每個物件都可以擁有多個屬性，這些屬性可以是可選的或是只讀的，使用 `?` 來表示可選屬性，使用 `readonly` 關鍵字來表示只讀屬性：
```typescript
interface Person {
    readonly id: number;
    name: string;
    age?: number; // 可選屬性
}
```

## 範例
### 基本物件範例
```typescript
let car: { brand: string; model: string; year: number } = {
    brand: "豐田",
    model: "Camry",
    year: 2022
};
```

### 使用介面
```typescript
interface Car {
    brand: string;
    model: string;
    year: number;
}

let myCar: Car = {
    brand: "豐田",
    model: "Camry",
    year: 2022
};
```

### 嵌套物件
```typescript
interface Address {
    street: string;
    city: string;
}

interface Person {
    name: string;
    address: Address;
}

let person: Person = {
    name: "張三",
    address: {
        street: "中華路",
        city: "台北"
    }
};
```

## 解釋
在使用物件時，開發者需要注意以下幾點：

- **型別安全**：TypeScript 提供型別檢查，確保物件的屬性符合預期的型別。但若屬性名稱拼寫錯誤，會導致編譯錯誤。
- **可選屬性**：使用可選屬性時，需注意在使用該屬性前進行檢查，避免出現 `undefined` 的情況。
- **只讀屬性**：若屬性被標記為 `readonly`，則該屬性在物件創建後不能再被修改，這有助於維護資料的完整性。

## 一句總結
在 TypeScript 中，物件是一組鍵值對的集合，透過型別系統增強了資料的結構性和安全性。