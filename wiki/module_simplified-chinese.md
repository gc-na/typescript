<!--
Meta Description: # TypeScript 模块详解：模块化开发的关键 ## 概述 TypeScript 中的模块是一种用于组织代码的方式，它允许开发者将代码分割成多个文件，并在需要时进行引入。这种结构化的方式提高了代码的可维护性和可重用性。 ## 文档 TypeScript 模块是通过 `export` 和 `im...
Meta Keywords: typescript, export, import, number, log
-->

# TypeScript 模块详解：模块化开发的关键

## 概述
TypeScript 中的模块是一种用于组织代码的方式，它允许开发者将代码分割成多个文件，并在需要时进行引入。这种结构化的方式提高了代码的可维护性和可重用性。

## 文档
TypeScript 模块是通过 `export` 和 `import` 关键字来定义和使用的。模块可以是一个文件，也可以是一个文件夹中的多个文件。每个文件都可以导出变量、函数、类或接口，以便在其他模块中使用。

### 目的
模块的主要目的是将逻辑分离，避免全局命名冲突，并提高代码的可读性。

### 用法
1. **导出模块**：使用 `export` 关键字将变量、函数或类导出。
   ```typescript
   // math.ts
   export function add(x: number, y: number): number {
       return x + y;
   }
   ```

2. **导入模块**：在需要使用时，通过 `import` 关键词引入模块。
   ```typescript
   // app.ts
   import { add } from './math';

   console.log(add(2, 3)); // 输出: 5
   ```

3. **默认导出**：模块还可以有一个默认导出，使用 `export default`。
   ```typescript
   // logger.ts
   export default function log(message: string): void {
       console.log(message);
   }

   // app.ts
   import log from './logger';

   log('Hello, TypeScript!'); // 输出: Hello, TypeScript!
   ```

## 示例
以下是 TypeScript 模块的基本用法示例：

**模块文件：math.ts**
```typescript
export function multiply(a: number, b: number): number {
    return a * b;
}
```

**主文件：app.ts**
```typescript
import { multiply } from './math';

let result = multiply(4, 5);
console.log(result); // 输出: 20
```

## 解释
在使用 TypeScript 模块时，开发者需要注意以下几点：

1. **模块作用域**：每个模块都有自己的作用域，导入的内容不会污染全局命名空间。
2. **相对路径**：确保在导入模块时使用正确的相对路径，避免路径错误导致的编译失败。
3. **循环依赖**：尽量避免循环依赖，因为这可能导致模块无法正确加载。
4. **类型声明**：如果模块包含类型声明，确保在导入时能够正确识别类型，尤其是在大型项目中。

## 一句话总结
TypeScript 模块通过 `export` 和 `import` 关键字实现代码的组织与复用，提高了代码的结构性和可维护性。