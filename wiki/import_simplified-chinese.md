<!--
Meta Description: # TypeScript 中的 "import" 语句详解 ## 概述 在 TypeScript 中，`import` 语句用于引入模块、类、函数或变量，使得代码更加模块化和可重用。通过使用 `import`，开发者可以将功能分散到多个文件中，从而提高代码的可维护性和清晰度。 ## 文档 ### 目...
Meta Keywords: typescript, import, from, export, const
-->

# TypeScript 中的 "import" 语句详解

## 概述
在 TypeScript 中，`import` 语句用于引入模块、类、函数或变量，使得代码更加模块化和可重用。通过使用 `import`，开发者可以将功能分散到多个文件中，从而提高代码的可维护性和清晰度。

## 文档
### 目的
`import` 语句的主要目的是在 TypeScript 文件中引入外部模块或库的功能，允许开发者使用其他文件中定义的类型、接口、类等。

### 用法
`import` 语句的基本语法如下：
```typescript
import { 名称 } from '模块路径';
```
- `名称` 是要引入的变量、函数或类的名称。
- `模块路径` 是要引入的模块的相对或绝对路径。

#### 示例
1. 引入单个变量：
```typescript
// utils.ts
export const PI = 3.14;

// app.ts
import { PI } from './utils';
console.log(PI); // 输出: 3.14
```

2. 引入多个变量：
```typescript
// constants.ts
export const MAX_SIZE = 100;
export const MIN_SIZE = 1;

// app.ts
import { MAX_SIZE, MIN_SIZE } from './constants';
console.log(MAX_SIZE, MIN_SIZE); // 输出: 100 1
```

3. 引入整个模块：
```typescript
// math.ts
export const add = (a: number, b: number) => a + b;
export const subtract = (a: number, b: number) => a - b;

// app.ts
import * as MathUtils from './math';
console.log(MathUtils.add(2, 3)); // 输出: 5
```

4. 默认导入：
```typescript
// logger.ts
const logger = (message: string) => console.log(message);
export default logger;

// app.ts
import logger from './logger';
logger('Hello, TypeScript!'); // 输出: Hello, TypeScript!
```

## 说明
在使用 `import` 时，有几个常见的注意事项：
- **模块路径**：确保提供正确的路径，包含文件扩展名（如 `.ts` 或 `.js`）在某些情况下是必要的，尤其是在 Node.js 环境中。
- **命名冲突**：如果不同模块中有相同名称的导出，可能会导致命名冲突。可以使用 `as` 关键字重命名导入。
  ```typescript
  import { add as addition } from './math';
  ```
- **循环依赖**：如果两个模块相互依赖，可能导致运行时错误。应尽量避免这种情况。
- **TypeScript 配置**：确保 TypeScript 编译器配置（如 `tsconfig.json`）正确设置，以支持模块解析。

## 一句话总结
`import` 语句在 TypeScript 中用于引入外部模块或功能，促进代码的模块化和重用。