<!--
Meta Description: # TypeScript 中的 keyof：用於提取物件鍵的關鍵字 ## 概述 `keyof` 是 TypeScript 中的一個關鍵字，用於提取一個物件類型的所有鍵，並生成一個聯合類型。這個特性使得在進行型別安全的物件操作時更加靈活和方便。 ## 文檔 ### 目的 `keyof` 的主要目的是提...
Meta Keywords: keyof, typescript, person, make, string
-->

# TypeScript 中的 keyof：用於提取物件鍵的關鍵字

## 概述
`keyof` 是 TypeScript 中的一個關鍵字，用於提取一個物件類型的所有鍵，並生成一個聯合類型。這個特性使得在進行型別安全的物件操作時更加靈活和方便。

## 文檔
### 目的
`keyof` 的主要目的是提供一種方式來獲取物件類型的所有鍵，這對於創建通用函數或類型映射非常有用。

### 用法
`keyof` 用於定義一個型別，該型別代表指定物件類型的所有鍵。語法如下：

```typescript
keyof T
```

其中 `T` 是一個物件類型。例如，若有一個接口 `Person` 定義如下：

```typescript
interface Person {
    name: string;
    age: number;
}
```

使用 `keyof` 可以這樣獲取 `Person` 的所有鍵：

```typescript
type PersonKeys = keyof Person; // "name" | "age"
```

### 詳細信息
- `keyof` 可以與其他 TypeScript 特性結合使用，例如 mapped types 和 indexed access types。
- `keyof` 會返回一個聯合類型，這意味著如果物件有多個鍵，則會生成這些鍵的交集。
- 使用 `keyof` 時，必須確保被操作的類型是物件類型，否則會導致編譯錯誤。

## 示例
以下是一些基本使用範例：

### 基本範例
```typescript
interface Vehicle {
    make: string;
    model: string;
    year: number;
}

type VehicleKeys = keyof Vehicle; // "make" | "model" | "year"
```

### 在函數中使用
```typescript
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
    return obj[key];
}

const car = {
    make: 'Toyota',
    model: 'Corolla',
    year: 2020
};

const carMake = getProperty(car, 'make'); // 'Toyota'
```

## 解釋
### 常見陷阱
- 使用 `keyof` 時，必須確保傳入的是一個物件類型，否則會造成編譯錯誤。
- `keyof` 不能直接用於函數類型，因為函數沒有鍵的概念。

### 注意事項
- `keyof` 只會提取物件的公共屬性，私有屬性不會被包括在內。
- 在 TypeScript 中，`keyof` 與 `in` 關鍵字有相似之處，但 `in` 用於遍歷一個聯合類型。

## 總結
`keyof` 是 TypeScript 中一個強大的工具，能夠安全地提取物件類型的鍵，並用於型別安全的操作。