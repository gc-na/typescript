<!--
Meta Description: # TypeScript 中的 Getter 方法：深入解析與使用示例 ## 摘要 在 TypeScript 中，Getter 方法（get）是一種特殊屬性，允許對物件的屬性進行訪問時，自動執行一些代碼。這使得物件的封裝性更強，並能夠在訪問屬性時進行計算或邏輯處理。 ## 文檔 Getter 方法是...
Meta Keywords: getter, number, typescript, get, person
-->

# TypeScript 中的 Getter 方法：深入解析與使用示例

## 摘要
在 TypeScript 中，Getter 方法（get）是一種特殊屬性，允許對物件的屬性進行訪問時，自動執行一些代碼。這使得物件的封裝性更強，並能夠在訪問屬性時進行計算或邏輯處理。

## 文檔
Getter 方法是使用 `get` 關鍵字來定義的，屬於 TypeScript 的類（class）語法的一部分。其主要目的是讓開發者能夠在訪問類屬性時執行自定義邏輯，從而提高代碼的靈活性和可讀性。

### 用法
要定義一個 Getter 方法，您需要在類中使用 `get` 關鍵字，後面跟著屬性名稱和一個返回值的函數。例如：

```typescript
class Person {
    private firstName: string;
    private lastName: string;

    constructor(firstName: string, lastName: string) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    get fullName(): string {
        return `${this.firstName} ${this.lastName}`;
    }
}

const person = new Person("John", "Doe");
console.log(person.fullName); // 輸出: John Doe
```

在這個例子中，`fullName` 是一個 Getter 方法，當訪問 `person.fullName` 時，會自動執行 `fullName` 函數並返回結果。

## 示例
以下是幾個基本的使用示例：

1. **基本 Getter 方法**：

    ```typescript
    class Rectangle {
        private width: number;
        private height: number;

        constructor(width: number, height: number) {
            this.width = width;
            this.height = height;
        }

        get area(): number {
            return this.width * this.height;
        }
    }

    const rect = new Rectangle(5, 10);
    console.log(rect.area); // 輸出: 50
    ```

2. **計算屬性**：

    ```typescript
    class Circle {
        private radius: number;

        constructor(radius: number) {
            this.radius = radius;
        }

        get circumference(): number {
            return 2 * Math.PI * this.radius;
        }
    }

    const circle = new Circle(3);
    console.log(circle.circumference); // 輸出: 18.84955592153876
    ```

3. **封裝性**：

    ```typescript
    class BankAccount {
        private balance: number;

        constructor(initialBalance: number) {
            this.balance = initialBalance;
        }

        get currentBalance(): number {
            return this.balance;
        }
    }

    const account = new BankAccount(1000);
    console.log(account.currentBalance); // 輸出: 1000
    ```

## 解釋
在使用 Getter 方法時，有幾個常見的坑和注意事項：

- **只讀性**：Getter 方法通常不應該更改物件的狀態，這樣會破壞屬性的可預測性。
- **性能問題**：如果 Getter 方法內部的計算過於複雜，可能會影響性能，特別是在多次訪問同一屬性時。
- **無法使用賦值**：Getter 方法是只讀的，因此不能對其進行賦值操作，如 `person.fullName = "Jane Doe"` 將會引發錯誤。

## 一句總結
TypeScript 中的 Getter 方法允許開發者在訪問類屬性時執行自定義邏輯，從而增強物件的封裝性與靈活性。