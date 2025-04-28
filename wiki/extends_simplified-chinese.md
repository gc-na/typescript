<!--
Meta Description: # TypeScript 中的 "extends": 继承与类型约束 ## 摘要 在 TypeScript 中，`extends` 关键字用于实现类之间的继承关系以及约束泛型类型。通过使用 `extends`，开发者可以创建更灵活与可重用的代码结构。 ## 文档 ### 目的 `extends` 关...
Meta Keywords: extends, typescript, class, void, console
-->

# TypeScript 中的 "extends": 继承与类型约束

## 摘要
在 TypeScript 中，`extends` 关键字用于实现类之间的继承关系以及约束泛型类型。通过使用 `extends`，开发者可以创建更灵活与可重用的代码结构。

## 文档
### 目的
`extends` 关键字允许一个类继承另一个类的属性和方法，或者在定义泛型时约束传入的类型。使用 `extends` 可以提高代码的可维护性和可读性。

### 用法
1. **类的继承**：
   TypeScript 允许一个类从另一个类继承属性和方法。使用 `extends` 关键字可以创建一个子类，该子类将拥有父类的所有功能。

   语法：
   ```typescript
   class 子类名 extends 父类名 {
       // 子类特有的属性和方法
   }
   ```

2. **泛型约束**：
   在泛型定义中，`extends` 可以用来限制泛型参数应当是某种特定类型或其子类型。

   语法：
   ```typescript
   function 函数名<T extends 基础类型>(参数: T): void {
       // 函数体
   }
   ```

## 示例
### 类的继承示例
```typescript
class 动物 {
    蹦跳() {
        console.log("动物在蹦跳");
    }
}

class 狗 extends 动物 {
    吠叫() {
        console.log("汪汪");
    }
}

const 我的狗 = new 狗();
我的狗.蹦跳(); // 输出: 动物在蹦跳
我的狗.吠叫(); // 输出: 汪汪
```

### 泛型约束示例
```typescript
interface 可飞行 {
    飞行(): void;
}

class 鸟 implements 可飞行 {
    飞行() {
        console.log("鸟在飞");
    }
}

function 在空中飞<T extends 可飞行>(飞行物: T): void {
    飞行物.飞行();
}

const 我的鸟 = new 鸟();
在空中飞(我的鸟); // 输出: 鸟在飞
```

## 解释
使用 `extends` 时，开发者需要注意以下几点：

- **多重继承**：TypeScript 不支持多重继承，即一个类不能同时继承多个类。但可以通过接口实现多重继承的效果。
- **类型兼容性**：在泛型约束中，使用 `extends` 时，传入的类型必须符合约束条件，否则会导致编译错误。
- **构造函数**：在继承时，子类需要调用父类的构造函数来确保父类的属性正确初始化。

## 一句话总结
在 TypeScript 中，`extends` 关键字用于实现类的继承和限制泛型参数类型，从而提升代码的灵活性和重用性。