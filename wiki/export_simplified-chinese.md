<!--
Meta Description: # TypeScript 中的 export 关键字详解 ## 概述 `export` 是 TypeScript 中用于导出模块内容的关键字，使得其他模块能够访问这些内容。通过使用 `export`，开发者可以实现代码的组织和重用，提高代码的可维护性。 ## 文档 在 TypeScript 中，`e...
Meta Keywords: export, typescript, mymodule, import, 导出变量
-->

# TypeScript 中的 export 关键字详解

## 概述
`export` 是 TypeScript 中用于导出模块内容的关键字，使得其他模块能够访问这些内容。通过使用 `export`，开发者可以实现代码的组织和重用，提高代码的可维护性。

## 文档
在 TypeScript 中，`export` 关键字用于将类、接口、变量、函数等导出，以便在其他模块中导入和使用。模块是 TypeScript 的核心概念之一，允许开发者将代码分隔到不同的文件中，从而实现更好的结构和管理。

### 目的
- 促进代码重用：允许一个模块的内容在其他模块中被访问。
- 提高可读性：将相关的代码组织到一起，使代码更易于理解。

### 用法
`export` 可以用于：
1. 导出变量
2. 导出函数
3. 导出类
4. 导出接口

### 细节
- 可以在一个文件中导出多个内容。
- 可以使用默认导出（`export default`）和命名导出（`export { ... }`）。
- 通过 `import` 关键字可以在其他模块中引入导出的内容。

## 示例
### 1. 导出变量
```typescript
// myModule.ts
export const myVariable = 42;
```

### 2. 导出函数
```typescript
// myModule.ts
export function myFunction() {
    return "Hello, world!";
}
```

### 3. 导出类
```typescript
// myModule.ts
export class MyClass {
    constructor(public name: string) {}
}
```

### 4. 默认导出
```typescript
// myModule.ts
export default class MyDefaultClass {
    constructor(public name: string) {}
}
```

### 5. 导入
```typescript
// otherModule.ts
import { myVariable, myFunction } from './myModule';
import MyDefaultClass from './myModule';
```

## 说明
- **命名冲突**：在导入多个模块时，可能会遇到命名冲突。可以使用 `as` 关键字来重命名导入的内容。
- **默认导出与命名导出**：每个模块只能有一个默认导出，但可以有多个命名导出。使用默认导出时，导入时不需要使用花括号。

## 一句话总结
`export` 关键字在 TypeScript 中用于将模块内容导出，以便其他模块能够访问和重用这些内容。