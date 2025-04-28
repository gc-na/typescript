<!--
Meta Description: # TypeScript中的“continue”语句详解 ## 概述 “continue”语句是TypeScript和JavaScript中的一种控制流语句，用于在循环中跳过当前迭代的剩余部分，并直接进入下一次循环迭代。 ## 文档 在TypeScript中，“continue”语句主要用于`for...
Meta Keywords: continue, typescript, let, console, log
-->

# TypeScript中的“continue”语句详解

## 概述
“continue”语句是TypeScript和JavaScript中的一种控制流语句，用于在循环中跳过当前迭代的剩余部分，并直接进入下一次循环迭代。

## 文档
在TypeScript中，“continue”语句主要用于`for`、`while`和`do...while`循环。它允许开发者在满足特定条件时，跳过循环体中的代码。

### 用途
“continue”语句的主要用途是在循环中控制执行流程，避免执行某些代码块。例如，当需要过滤掉不符合条件的元素时，可以使用“continue”语句来跳过当前元素的处理。

### 使用方法
“continue”语句的基本语法如下：

```typescript
continue;
```

在特定的循环结构中，可以使用“continue”语句来控制迭代的执行。例如：

```typescript
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) {
        continue; // 如果 i 是偶数，跳过当前迭代
    }
    console.log(i); // 只会打印奇数
}
```

## 示例
以下是使用“continue”语句的几个基本示例：

### 示例 1：跳过偶数
```typescript
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) {
        continue; // 跳过偶数
    }
    console.log(i); // 输出：1, 3, 5, 7, 9
}
```

### 示例 2：在while循环中使用
```typescript
let j = 0;
while (j < 10) {
    j++;
    if (j % 3 === 0) {
        continue; // 跳过3的倍数
    }
    console.log(j); // 输出：1, 2, 4, 5, 7, 8, 10
}
```

### 示例 3：嵌套循环
```typescript
for (let x = 0; x < 3; x++) {
    for (let y = 0; y < 3; y++) {
        if (y === 1) {
            continue; // 跳过 y 为 1 的情况
        }
        console.log(`x: ${x}, y: ${y}`); // 输出：x: 0, y: 0; x: 0, y: 2; 等等
    }
}
```

## 解释
### 常见问题
1. **对嵌套循环的影响**：在嵌套循环中，`continue`语句只会影响它所在的最内层循环，而不会影响外层循环的执行。
2. **与`break`的区别**：`continue`跳过当前迭代并继续下一次迭代，而`break`则会终止整个循环。
3. **条件判断**：确保条件判断中没有遗漏，错误的条件可能导致预期外的行为。

### 附加说明
使用`continue`语句可以提高代码的可读性，避免不必要的嵌套层次。不过，过度使用可能会影响代码的逻辑清晰度，需谨慎使用。

## 一句话总结
“continue”语句在TypeScript中用于跳过当前循环的剩余部分，直接进入下一次迭代。