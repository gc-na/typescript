<!--
Meta Description: # TypeScript 中的 default 关键字详解 ## 概述 在 TypeScript 中，`default` 关键字用于定义模块的默认导出。它使得在导入模块时可以直接获取一个特定的值或对象，简化了模块的使用方式。 ## 文档 在 TypeScript 中，`default` 关键字可以用...
Meta Keywords: typescript, default, person, greet, hello
-->

# TypeScript 中的 default 关键字详解

## 概述
在 TypeScript 中，`default` 关键字用于定义模块的默认导出。它使得在导入模块时可以直接获取一个特定的值或对象，简化了模块的使用方式。

## 文档
在 TypeScript 中，`default` 关键字可以用于函数、类、对象或任何其他类型的导出。使用 `default` 导出的模块在导入时不需要使用大括号，允许开发者更灵活地命名导入的内容。

### 目的
- 简化模块的导入。
- 提供一种清晰的方式来指定模块的主导出内容。

### 用法
1. **定义默认导出**：
   ```typescript
   // MyModule.ts
   const myFunction = () => {
       console.log("Hello, TypeScript!");
   };
   export default myFunction;
   ```

2. **导入默认导出**：
   ```typescript
   // main.ts
   import myFunc from './MyModule';
   myFunc(); // 输出: Hello, TypeScript!
   ```

## 示例
### 示例 1：默认导出一个函数
```typescript
// greet.ts
const greet = (name: string) => `Hello, ${name}!`;
export default greet;

// app.ts
import greet from './greet';
console.log(greet("World")); // 输出: Hello, World!
```

### 示例 2：默认导出一个类
```typescript
// Person.ts
class Person {
    constructor(public name: string) {}
}
export default Person;

// app.ts
import Person from './Person';
const person = new Person("Alice");
console.log(person.name); // 输出: Alice
```

## 解释
在使用 `default` 导出时，开发者可以避免在导入时使用大括号，这使得代码更清晰。不过，有几个常见的注意事项：

- **只允许一个默认导出**：每个模块只能有一个默认导出，尝试多次使用 `export default` 会导致错误。
- **重命名导入**：导入时可以自由命名，而不必与导出时的名称一致。
- **与命名导出结合使用**：一个模块可以同时有默认导出和命名导出。

## 一句话总结
`default` 关键字在 TypeScript 中用于简化模块的默认导出及导入，提升代码的可读性和灵活性。