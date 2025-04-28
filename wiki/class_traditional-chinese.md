<!--
Meta Description: # TypeScript 中的類別 (Class) 使用指南 ## 概述 在 TypeScript 中，類別（Class）是用來創建物件的藍圖，提供了一種面向物件的編程風格，使得代碼結構更清晰且易於維護。類別支援繼承、封裝及多型等特性，讓開發者能夠有效地組織和管理代碼。 ## 文件說明 ### 目的...
Meta Keywords: typescript, class, name, dog, constructor
-->

# TypeScript 中的類別 (Class) 使用指南

## 概述
在 TypeScript 中，類別（Class）是用來創建物件的藍圖，提供了一種面向物件的編程風格，使得代碼結構更清晰且易於維護。類別支援繼承、封裝及多型等特性，讓開發者能夠有效地組織和管理代碼。

## 文件說明
### 目的
類別的主要目的是將相關的屬性（狀態）和方法（行為）封裝在一起，使得物件的創建與管理變得更簡單和直觀。

### 使用方式
在 TypeScript 中，類別的語法與 JavaScript 的類別相似，但 TypeScript 透過靜態類型系統增強了類別的功能。可以使用 `class` 關鍵字來定義一個類別，並用 `constructor` 方法來初始化物件的屬性。

### 詳細說明
- **定義類別**：使用 `class` 關鍵字來定義類別。
- **建構函數**：使用 `constructor` 方法來初始化類別的屬性。
- **屬性**：可以在類別內部定義屬性，這些屬性可以是公開的（`public`）、私有的（`private`）或受保護的（`protected`）。
- **方法**：類別內部可以定義方法，這些方法可以用來操作類別的屬性或執行其他行為。
- **繼承**：使用 `extends` 關鍵字來擴展其他類別，以實現代碼的重用。
- **多型**：可以通過方法覆寫來實現多型。

## 範例
以下是定義和使用 TypeScript 類別的基本範例：

```typescript
class Animal {
    name: string;
    
    constructor(name: string) {
        this.name = name;
    }
    
    speak(): void {
        console.log(`${this.name} 發出聲音`);
    }
}

class Dog extends Animal {
    speak(): void {
        console.log(`${this.name} 吠叫`);
    }
}

const dog = new Dog("狗狗");
dog.speak(); // 輸出: 狗狗 吠叫
```

## 解釋
- **常見陷阱**：在 TypeScript 中，如果沒有指定屬性的類型，將會被推斷為 `any` 類型，這可能會導致潛在的錯誤。
- **建構函數**：如果未定義建構函數，TypeScript 會自動生成一個預設建構函數，但建議始終顯式定義以避免混淆。
- **私有和受保護屬性**：私有屬性只能在類別內部訪問，而受保護屬性則可以在子類別中訪問，應根據需求合理使用。

## 一句總結
TypeScript 中的類別提供了一種結構化的方式來創建和管理物件，使得代碼更具可讀性和可維護性。