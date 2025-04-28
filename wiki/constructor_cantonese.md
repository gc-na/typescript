<!--
Meta Description: # TypeScript 中的 Constructor：構造函數的深入解析 ## 簡介 在 TypeScript 中，構造函數（constructor）是用來初始化對象的特殊方法。它在類別實例化時被自動調用，幫助開發者定義對象的初始狀態和屬性。 ## 文檔 構造函數是類別使用的一個重要組件。在 Ty...
Meta Keywords: name, age, typescript, constructor, string
-->

# TypeScript 中的 Constructor：構造函數的深入解析

## 簡介
在 TypeScript 中，構造函數（constructor）是用來初始化對象的特殊方法。它在類別實例化時被自動調用，幫助開發者定義對象的初始狀態和屬性。

## 文檔
構造函數是類別使用的一個重要組件。在 TypeScript 中，當你創建一個類別時，可以定義一個名為 `constructor` 的方法。這個方法可以接收參數，並用來設置類別的屬性。在對類的實例化過程中，構造函數會被自動調用，確保所有必要的初始化工作在對象使用之前完成。

### 用法
構造函數的基本語法如下：

```typescript
class ClassName {
    constructor(param1: Type1, param2: Type2) {
        // 初始化屬性
    }
}
```

在這段代碼中，`ClassName` 是類別名稱，`param1` 和 `param2` 是構造函數的參數。可以使用這些參數來設置類別的屬性。

## 示例
以下是一個簡單的構造函數示例：

```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    introduce() {
        console.log(`你好，我是 ${this.name}，今年 ${this.age} 歲。`);
    }
}

const person1 = new Person("小明", 30);
person1.introduce(); // 輸出：你好，我是 小明，今年 30 歲。
```

在這個例子中，`Person` 類別的構造函數接收 `name` 和 `age` 參數，並將其設置為對象的屬性。

## 解釋
在使用構造函數時，有一些常見的陷阱需要注意：

1. **多個構造函數**：TypeScript 不支持在同一個類中定義多個同名構造函數。如果需要不同的初始化行為，可以使用可選參數或重載。
   
2. **屬性初始化**：如果在構造函數中沒有初始化屬性，這些屬性將會是 `undefined`，可能會造成運行時錯誤。

3. **繼承中的構造函數**：如果一個類繼承自另一個類，子類的構造函數必須調用 `super()` 方法來調用父類的構造函數，否則將會報錯。

```typescript
class Employee extends Person {
    position: string;

    constructor(name: string, age: number, position: string) {
        super(name, age); // 調用父類構造函數
        this.position = position;
    }

    introduce() {
        console.log(`你好，我是 ${this.name}，今年 ${this.age} 歲，職位是 ${this.position}。`);
    }
}
```

## 簡短總結
構造函數是 TypeScript 中用於初始化類別對象的重要工具，它在創建實例時自動執行，幫助設置對象的初始狀態。