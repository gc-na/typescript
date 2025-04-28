<!--
Meta Description: # TypeScript 中的 static 關鍵字：靜態屬性與方法的完整指南 ## 摘要 在 TypeScript 中，`static` 關鍵字用於定義靜態屬性和靜態方法，這些屬性和方法屬於類別本身，而非類別的實例。這使得開發者能夠在不創建實例的情況下使用這些屬性和方法，提供了一種方便的方式來管理...
Meta Keywords: static, typescript, number, calculator, class
-->

# TypeScript 中的 static 關鍵字：靜態屬性與方法的完整指南

## 摘要
在 TypeScript 中，`static` 關鍵字用於定義靜態屬性和靜態方法，這些屬性和方法屬於類別本身，而非類別的實例。這使得開發者能夠在不創建實例的情況下使用這些屬性和方法，提供了一種方便的方式來管理類別級別的數據和行為。

## 文檔
### 目的
`static` 關鍵字的主要目的是讓開發者能夠定義與類別相關但不屬於特定實例的屬性和方法。這在需要共享數據或行為的情況下非常有用，例如計數器或與類別相關的工具函數。

### 用法
在 TypeScript 中，使用 `static` 關鍵字來聲明靜態屬性和方法。靜態成員可以通過類別名直接訪問，而無需創建類別的實例。以下是靜態屬性和方法的基本語法：

```typescript
class MyClass {
    static myStaticProperty: number = 10;

    static myStaticMethod(): string {
        return "Hello from static method!";
    }
}
```

### 詳細說明
- **靜態屬性**: 靜態屬性可以用來存儲與類別本身相關的數據。這些屬性對所有實例是共享的。
- **靜態方法**: 靜態方法可以在不實例化類別的情況下被調用。這對於需要訪問靜態屬性或提供工具函數的場景非常有用。

## 範例
以下是靜態屬性和靜態方法的基本使用範例：

```typescript
class Calculator {
    static add(a: number, b: number): number {
        return a + b;
    }

    static pi: number = 3.14;
}

// 使用靜態方法
console.log(Calculator.add(5, 10)); // 輸出: 15

// 使用靜態屬性
console.log(Calculator.pi); // 輸出: 3.14
```

## 解釋
在使用靜態成員時，開發者需要注意以下幾點：
- 靜態成員無法通過實例訪問，必須通過類別名稱來訪問。
- 靜態屬性和方法不能使用 `this` 關鍵字來引用實例屬性，因為靜態成員不屬於任何實例。
- 如果在子類中重新定義靜態成員，這些成員不會繼承自父類，而是獨立於各自的類別。

## 一句總結
TypeScript 中的 `static` 關鍵字允許開發者定義屬於類別本身的靜態屬性和靜態方法，從而促進了類別級別的數據和行為管理。