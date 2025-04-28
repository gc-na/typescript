<!--
Meta Description: # TypeScript 的建構子 (Constructor) 詳解 ## 概述 在 TypeScript 中，建構子（Constructor）是一種特殊的方法，用於創建和初始化類的實例。它使得物件的屬性在實例化時可以被賦值並且設置為所需的狀態。 ## 文件說明 建構子是 TypeScript 類別...
Meta Keywords: typescript, name, age, constructor, super
-->

# TypeScript 的建構子 (Constructor) 詳解

## 概述
在 TypeScript 中，建構子（Constructor）是一種特殊的方法，用於創建和初始化類的實例。它使得物件的屬性在實例化時可以被賦值並且設置為所需的狀態。

## 文件說明
建構子是 TypeScript 類別中的一個關鍵組件。當你使用 `new` 關鍵字創建類的實例時，建構子會自動被調用。建構子可以有參數，這些參數可以用來初始化類的屬性。

### 目的
建構子的主要目的是為類的實例提供初始化邏輯，例如設定屬性值、執行必要的計算等。

### 用法
在 TypeScript 中，建構子的語法如下：

```typescript
class ClassName {
    constructor(parameters) {
        // 初始化邏輯
    }
}
```

- `ClassName` 是類的名稱。
- `parameters` 是建構子接收的參數，可以用來初始化屬性。

### 詳細說明
建構子可以接受任意數量的參數，並且可以指定參數的類型。以下是建構子的一些重要特性：

1. **多個建構子**：TypeScript 不支持方法重載，但可以使用可選參數或預設參數來模擬多個建構子。
2. **訪問修飾符**：在建構子中，你可以使用 `public`、`private` 或 `protected` 修飾符來定義屬性，這樣可以在建構子中自動創建屬性並賦值。
3. **呼叫父建構子**：如果你在子類中定義了建構子，則必須在子建構子中使用 `super()` 來呼叫父類的建構子。

## 範例
以下是使用建構子的基本範例：

```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    introduce() {
        console.log(`你好，我叫 ${this.name}，我 ${this.age} 歲。`);
    }
}

const person1 = new Person("小明", 25);
person1.introduce(); // 輸出: 你好，我叫 小明，我 25 歲。
```

## 解釋
在使用建構子時，有一些常見的陷阱和注意事項：

1. **未呼叫 `super()`**：在子類中定義建構子時，必須呼叫 `super()`，否則會拋出錯誤。
2. **可選參數的使用**：如果使用可選參數，需注意在建構子內對該參數的檢查，以避免未定義的情況。
3. **屬性初始化**：在建構子中初始化屬性是非常重要的，若屬性未正確初始化，可能會導致運行時錯誤。

## 一句總結
TypeScript 的建構子是類的特殊方法，用於創建和初始化類的實例，並可以接收參數來設置屬性值。