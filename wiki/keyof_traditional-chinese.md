<!--
Meta Description: # TypeScript `keyof` 關鍵字詳細說明 ## 簡介 `keyof` 是 TypeScript 中的一個關鍵字，用於獲取一個物件類型的所有鍵名，並將其轉換為字符串字面量聯合類型。這使得在開發中可以更靈活地操作物件型別。 ## 文檔 `keyof` 用於取得給定物件類型的鍵名，這些鍵名...
Meta Keywords: keyof, typescript, string, user, username
-->

# TypeScript `keyof` 關鍵字詳細說明

## 簡介
`keyof` 是 TypeScript 中的一個關鍵字，用於獲取一個物件類型的所有鍵名，並將其轉換為字符串字面量聯合類型。這使得在開發中可以更靈活地操作物件型別。

## 文檔
`keyof` 用於取得給定物件類型的鍵名，這些鍵名會被表示為一個字符串聯合類型。這在需要對物件的屬性進行動態操作時非常有用。使用 `keyof` 可以提高型別的安全性和代碼的可讀性。

### 使用方式
`keyof` 的基本語法如下：

```typescript
type Keys = keyof T;
```

其中 `T` 是一個物件類型，`Keys` 將會是一個字符串聯合類型，包含 `T` 的所有鍵名。

### 詳細解釋
- `keyof` 可以與索引類型結合使用，以實現更靈活的型別推斷。
- 它可以與映射類型一起使用，以創建新類型。

例如：

```typescript
interface Person {
    name: string;
    age: number;
}

type PersonKeys = keyof Person; // 'name' | 'age'
```

## 範例
以下是 `keyof` 的基本用法範例：

### 基本範例
```typescript
interface Car {
    make: string;
    model: string;
    year: number;
}

type CarKeys = keyof Car; // 'make' | 'model' | 'year'
```

### 與索引類型結合使用
```typescript
interface User {
    id: number;
    username: string;
    email: string;
}

function getValue<T, K extends keyof T>(obj: T, key: K): T[K] {
    return obj[key];
}

const user: User = { id: 1, username: 'Alice', email: 'alice@example.com' };
const username = getValue(user, 'username'); // 'Alice'
```

## 解釋
在使用 `keyof` 時，開發者需要注意以下幾點：

1. **只適用於物件類型**：`keyof` 僅適用於物件類型，對於原始類型（如數字、字符串等）無法使用。
2. **類型推斷**：使用 `keyof` 時，TypeScript 會自動推斷出相應的鍵名類型，開發者不需要手動指定。
3. **不支持私有屬性**：`keyof` 僅能獲取公共屬性，對於私有屬性將無法獲得。

## 總結
`keyof` 是 TypeScript 中一個強大的工具，可以提取物件的鍵名並作為字符串聯合類型使用，從而提高代碼的靈活性和安全性。