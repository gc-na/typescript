<!--
Meta Description: # TypeScript 中的命名空間 (namespace) 使用指南 ## 摘要 命名空間（namespace）是 TypeScript 提供的一種組織代碼的方式，主要用來防止全局變數的衝突，並使代碼結構更加清晰。 ## 文檔 ### 目的 命名空間是一種將相關變數、函數、類和介面組織在一起的機...
Meta Keywords: export, number, typescript, namespace, function
-->

# TypeScript 中的命名空間 (namespace) 使用指南

## 摘要
命名空間（namespace）是 TypeScript 提供的一種組織代碼的方式，主要用來防止全局變數的衝突，並使代碼結構更加清晰。

## 文檔
### 目的
命名空間是一種將相關變數、函數、類和介面組織在一起的機制。它有助於將代碼模組化，特別是在大型應用程序中，可以有效避免命名衝突。

### 用法
在 TypeScript 中，您可以透過 `namespace` 關鍵字來定義命名空間。命名空間可以包含類、介面、函數和變數，並且可以嵌套。

以下是定義命名空間的基本語法：
```typescript
namespace NamespaceName {
    export class ClassName {
        // 類的內容
    }
    
    export function functionName() {
        // 函數的內容
    }
}
```
使用 `export` 關鍵字可以讓命名空間中的成員在外部可見。

### 詳細信息
命名空間可以在同一個文件中定義，也可以跨文件進行引用。為了引用其他文件中的命名空間，您可以使用 `/// <reference path="..." />` 指令。

命名空間的使用方式有助於保持代碼的整潔和可維護性，特別是在多個開發人員協作時。

## 示例
### 基本用法示例
```typescript
namespace MathUtilities {
    export function add(x: number, y: number): number {
        return x + y;
    }

    export function subtract(x: number, y: number): number {
        return x - y;
    }
}

let sum = MathUtilities.add(5, 3); // 返回 8
let difference = MathUtilities.subtract(5, 3); // 返回 2
```

### 嵌套命名空間示例
```typescript
namespace Shapes {
    export namespace Circle {
        export const PI = 3.14;

        export function area(radius: number): number {
            return PI * radius * radius;
        }
    }
}

let circleArea = Shapes.Circle.area(5); // 返回 78.5
```

## 解釋
在使用命名空間時，開發者常見的陷阱包括：
- **未使用 `export`**：如果沒有使用 `export`，命名空間內的成員將無法被外部訪問。
- **命名衝突**：雖然命名空間的目的是避免衝突，但如果命名空間的名稱與其他全局變數相同，仍然可能導致衝突。
- **過度使用命名空間**：對於小型項目，過度使用命名空間可能會導致代碼過於複雜，而在這種情況下，使用模組化的方式更為合適。

## 一句總結
命名空間是 TypeScript 中的一個重要特性，用於組織代碼並避免全局命名衝突。