<!--
Meta Description: # TypeScript 介面 (Interface) 的詳細介紹 ## 概述 介面（Interface）是 TypeScript 中的一個重要概念，用於定義物件的結構和形狀。透過介面，開發者可以強制類別或物件遵循特定的格式，提升代碼的可讀性和可維護性。 ## 文檔 介面在 TypeScript 中...
Meta Keywords: typescript, interface, string, const, example
-->

# TypeScript 介面 (Interface) 的詳細介紹

## 概述
介面（Interface）是 TypeScript 中的一個重要概念，用於定義物件的結構和形狀。透過介面，開發者可以強制類別或物件遵循特定的格式，提升代碼的可讀性和可維護性。

## 文檔
介面在 TypeScript 中的主要目的是為了描述物件的型別。它允許開發者定義物件的屬性及其類型，還可以用於函數的參數和返回值。介面提供了一個靈活的方式來擴展和重用代碼，並且能夠在編譯時進行型別檢查，減少運行時錯誤。

### 使用方式
介面的定義語法如下：

```typescript
interface InterfaceName {
    property1: type1;
    property2: type2;
    methodName(param: type): returnType;
}
```

### 詳細介紹
1. **定義屬性**：在介面中可以定義多個屬性，並為每個屬性指定類型。
2. **可選屬性**：使用問號 `?` 可以定義可選屬性，使這些屬性在實現介面時可以被省略。
3. **只讀屬性**：使用 `readonly` 關鍵字可以定義只讀屬性，這些屬性在物件創建後不可被修改。
4. **擴展介面**：介面可以通過 `extends` 關鍵字來擴展其他介面，實現多重繼承的效果。
5. **函數類型**：介面也可以用來定義函數的類型，這對於回調函數特別有用。

## 範例
以下是一些介面的基本使用範例：

### 定義介面
```typescript
interface Person {
    name: string;
    age: number;
    greet(): string;
}
```

### 使用介面
```typescript
const user: Person = {
    name: "小明",
    age: 30,
    greet() {
        return `你好，我是${this.name}`;
    }
};

console.log(user.greet()); // 你好，我是小明
```

### 可選屬性
```typescript
interface Contact {
    email: string;
    phone?: string; // 可選屬性
}

const contact1: Contact = { email: "example@example.com" };
const contact2: Contact = { email: "example@example.com", phone: "12345678" };
```

### 擴展介面
```typescript
interface Animal {
    species: string;
}

interface Dog extends Animal {
    bark(): void;
}

const dog: Dog = {
    species: "狗",
    bark() {
        console.log("汪汪");
    }
};
```

## 解釋
在使用介面時，開發者需留意以下幾點：

1. **命名衝突**：如果多個介面使用相同的屬性名稱，可能會導致錯誤。因此，應避免在擴展介面時使用相同的屬性名稱。
2. **性能考量**：過度使用複雜介面可能會影響代碼的性能，應根據實際需求合理設計介面。
3. **可選屬性與未定義**：可選屬性在未定義時會返回 `undefined`，因此在使用時應注意檢查該屬性的存在性。

## 總結
TypeScript 的介面提供了一種強大的方式來定義物件的形狀和結構，從而提高代碼的可讀性和可維護性。