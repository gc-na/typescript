<!--
Meta Description: # TypeScript 中的 "true" 值详解 ## 概述 在 TypeScript 中，`true` 是一个布尔值，表示逻辑上的真。这一值在条件判断、类型检查及其他逻辑操作中扮演着重要角色。 ## 文档 ### 目的 `true` 是 TypeScript 中的基本数据类型之一，属于布尔类型...
Meta Keywords: typescript, true, boolean, console, log
-->

# TypeScript 中的 "true" 值详解

## 概述
在 TypeScript 中，`true` 是一个布尔值，表示逻辑上的真。这一值在条件判断、类型检查及其他逻辑操作中扮演着重要角色。

## 文档
### 目的
`true` 是 TypeScript 中的基本数据类型之一，属于布尔类型（Boolean）。它用于表示逻辑真值，通常与 `false` 对应，广泛应用于控制流、条件语句和布尔表达式中。

### 用法
在 TypeScript 中，布尔值 `true` 可以直接使用，并且可以在声明变量时赋值。布尔类型的变量可以用于条件判断，以决定代码的执行路径。

```typescript
let isActive: boolean = true;
if (isActive) {
    console.log("状态是激活的");
}
```

### 详细信息
- **类型定义**: 在 TypeScript 中，可以通过使用 `boolean` 类型来定义布尔值。
- **逻辑操作**: `true` 可用于与逻辑运算符（如 `&&` 和 `||`）结合使用。
- **类型推断**: TypeScript 可以根据上下文自动推断布尔值的类型。

## 示例
以下是一些基本用法示例：

```typescript
let isLoggedIn: boolean = true;

if (isLoggedIn) {
    console.log("用户已登录");
} else {
    console.log("用户未登录");
}

// 使用逻辑运算符
let hasPermission: boolean = true;
let isAdmin: boolean = false;

if (hasPermission && isAdmin) {
    console.log("用户具有管理员权限");
} else {
    console.log("用户不具有管理员权限");
}
```

## 说明
常见的陷阱和注意事项：
- **类型不匹配**: 确保在需要布尔值的地方不要意外地使用其他类型（如数字或字符串），这会导致类型错误。
- **非布尔值的真值**: 在 JavaScript 中，某些非布尔值（如非零数字、非空字符串等）在条件语句中会被视为“真”，但在 TypeScript 中，布尔类型只接受 `true` 或 `false`。
- **严格模式**: 在启用严格模式下，TypeScript 会更严格地检查布尔值的使用，确保类型安全。

## 一句话总结
在 TypeScript 中，`true` 是表示逻辑真值的布尔类型，广泛用于条件判断和逻辑运算中。