<!--
Meta Description: # TypeScript 中的 extends 關鍵字：用於繼承與擴展的功能 ## 概述 在 TypeScript 中，`extends` 關鍵字用於創建繼承關係，允許一個類或介面擴展另一個類或介面，從而實現代碼的重用和多態性。 ## 文檔 ### 目的 `extends` 主要用於類和介面的繼承，...
Meta Keywords: extends, typescript, string, name, make
-->

# TypeScript 中的 extends 關鍵字：用於繼承與擴展的功能

## 概述
在 TypeScript 中，`extends` 關鍵字用於創建繼承關係，允許一個類或介面擴展另一個類或介面，從而實現代碼的重用和多態性。

## 文檔

### 目的
`extends` 主要用於類和介面的繼承，使得開發者可以基於現有的類或介面來創建新的類或介面，並增加或修改屬性和方法。

### 使用
在 TypeScript 中，`extends` 可以用於以下幾種情況：

1. **類的繼承**：
   當一個類繼承另一個類時，可以使用 `extends` 關鍵字來獲取父類的屬性和方法。

   ```typescript
   class Animal {
       name: string;
       constructor(name: string) {
           this.name = name;
       }
       speak() {
           console.log(`${this.name} makes a noise.`);
       }
   }

   class Dog extends Animal {
       speak() {
           console.log(`${this.name} barks.`);
       }
   }
   ```

2. **介面的擴展**：
   當一個介面需要擴展另一個介面的屬性時，可以使用 `extends`。

   ```typescript
   interface Person {
       name: string;
       age: number;
   }

   interface Employee extends Person {
       employeeId: number;
   }
   ```

### 詳細說明
使用 `extends` 時，有幾個重要的點需要注意：

- 子類會繼承父類的所有公有和保護屬性及方法。
- 可以重寫父類的方法來提供不同的實現。
- 當擴展介面時，新的介面會擁有所有父介面的屬性，並可以增加新的屬性。

## 範例

### 類的繼承範例
```typescript
class Vehicle {
    make: string;
    constructor(make: string) {
        this.make = make;
    }
}

class Car extends Vehicle {
    model: string;
    constructor(make: string, model: string) {
        super(make);
        this.model = model;
    }
}

const myCar = new Car('Toyota', 'Corolla');
console.log(myCar.make); // Toyota
console.log(myCar.model); // Corolla
```

### 介面的擴展範例
```typescript
interface Shape {
    area(): number;
}

interface Circle extends Shape {
    radius: number;
}

const circle: Circle = {
    radius: 5,
    area: function() {
        return Math.PI * this.radius * this.radius;
    }
};

console.log(circle.area()); // 78.53981633974483
```

## 解釋
使用 `extends` 時可能會遇到以下常見問題：

- **多重繼承**：TypeScript 不支持多重繼承，但可以通過混合類和介面來達到類似效果。
- **屬性衝突**：當子類和父類有相同名稱的屬性時，子類的屬性會覆蓋父類的屬性，這可能導致意外行為。

## 一句總結
`extends` 在 TypeScript 中是一個強大的關鍵字，可用於實現類和介面的繼承，從而促進代碼重用和靈活性。