<!--
Meta Description: # TypeScript 類別 (Class) 使用指南 ## 簡介 TypeScript 的類別（Class）是一種用於創建物件的藍圖，支援物件導向程式設計的特性，如繼承和封裝。類別讓開發者能夠更清晰地組織代碼，並提高可重用性和可維護性。 ## 文檔 ### 目的 類別用於定義物件的結構和行為，幫...
Meta Keywords: typescript, name, age, class, person
-->

# TypeScript 類別 (Class) 使用指南

## 簡介
TypeScript 的類別（Class）是一種用於創建物件的藍圖，支援物件導向程式設計的特性，如繼承和封裝。類別讓開發者能夠更清晰地組織代碼，並提高可重用性和可維護性。

## 文檔

### 目的
類別用於定義物件的結構和行為，幫助開發者創建可擴展且易於管理的應用程式。TypeScript 在 JavaScript 的基礎上擴展了類別的功能，加入了型別檢查，使得開發過程更加安全。

### 使用方法
在 TypeScript 中，定義一個類別使用 `class` 關鍵字。基本語法如下：

```typescript
class ClassName {
    // 屬性
    propertyName: type;

    // 建構子
    constructor(param: type) {
        this.propertyName = param;
    }

    // 方法
    methodName(): returnType {
        // 方法邏輯
    }
}
```

### 詳細說明
- **屬性**：類別中的變數，定義物件的狀態。
- **建構子**：特殊函數，用於創建類別的實例，通常用來初始化屬性。
- **方法**：定義物件行為的函數，能夠對類別的屬性進行操作。

## 範例

### 基本範例
以下是簡單的類別定義與使用範例：

```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    greet(): string {
        return `你好，我叫 ${this.name}，今年 ${this.age} 歲。`;
    }
}

const person = new Person('小明', 25);
console.log(person.greet()); // 輸出：你好，我叫 小明，今年 25 歲。
```

### 繼承範例
TypeScript 類別支援繼承，子類別可以擴展父類別的屬性和方法：

```typescript
class Student extends Person {
    studentId: number;

    constructor(name: string, age: number, studentId: number) {
        super(name, age);
        this.studentId = studentId;
    }

    study(): string {
        return `${this.name} 正在學習。`;
    }
}

const student = new Student('小華', 22, 12345);
console.log(student.greet()); // 輸出：你好，我叫 小華，今年 22 歲。
console.log(student.study());  // 輸出：小華 正在學習。
```

## 解釋
在使用類別時，開發者應注意以下幾點：
- **型別定義**：確保屬性的型別明確，以便於 TypeScript 在編譯時進行檢查。
- **可見性修飾符**：使用 `public`、`private` 和 `protected` 來控制屬性和方法的可見性，以實現封裝。
- **抽象類別與介面**：了解何時使用抽象類別或介面來設計更靈活的類別結構。

類別的使用可能會遇到一些常見的陷阱，例如未正確初始化屬性或在繼承時未調用父類建構子，這可能導致程式錯誤。

## 一句總結
TypeScript 的類別提供了一種結構化的方式來創建和管理物件，支援物件導向程式設計的基本特性。