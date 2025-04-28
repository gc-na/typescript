<!--
Meta Description: # TypeScriptの関数: 基本と使い方 ## 概要 TypeScriptにおける関数は、特定のタスクを実行するための再利用可能なコードのブロックです。JavaScriptの機能を拡張し、型安全性を提供します。 ## ドキュメント TypeScriptでは、関数は次の目的で使用されます： - ...
Meta Keywords: number, typescript, return, const, console
-->

# TypeScriptの関数: 基本と使い方

## 概要
TypeScriptにおける関数は、特定のタスクを実行するための再利用可能なコードのブロックです。JavaScriptの機能を拡張し、型安全性を提供します。

## ドキュメント
TypeScriptでは、関数は次の目的で使用されます：

- **再利用性**: 一度定義した関数は、プログラム内の他の部分から何度でも呼び出すことができます。
- **型安全性**: TypeScriptは引数や戻り値の型を指定することで、実行時エラーを減らすことができます。

### 基本的な構文
関数は次のように定義できます：

```typescript
function 関数名(引数: 型): 戻り値の型 {
    // 処理内容
    return 戻り値;
}
```

### アロー関数
TypeScriptでは、アロー関数を使用して簡潔に関数を定義することもできます：

```typescript
const 関数名 = (引数: 型): 戻り値の型 => {
    // 処理内容
    return 戻り値;
};
```

## 例
以下に、TypeScriptの関数の基本的な使用例を示します。

### 通常の関数

```typescript
function add(a: number, b: number): number {
    return a + b;
}

const result = add(5, 3);
console.log(result); // 出力: 8
```

### アロー関数

```typescript
const multiply = (x: number, y: number): number => {
    return x * y;
};

const product = multiply(4, 2);
console.log(product); // 出力: 8
```

### オプショナル引数

```typescript
function greet(name: string, greeting?: string): string {
    return `${greeting ? greeting : 'こんにちは'}、${name}さん！`;
}

console.log(greet('太郎')); // 出力: こんにちは、太郎さん！
console.log(greet('次郎', 'こんばんは')); // 出力: こんばんは、次郎さん！
```

## 説明
TypeScriptの関数を使用する際の一般的な落とし穴や注意点：

- **型の不一致**: 引数や戻り値の型を間違えると、コンパイルエラーが発生します。常に正しい型を指定することが重要です。
- **オプショナル引数の使用**: オプショナル引数を使用する場合は、デフォルト値を設定しないと、呼び出し時に未定義になる可能性があります。
- **thisの文脈**: アロー関数は`this`の文脈をレキシカルに保持しますが、通常の関数は呼び出し元によって異なるため注意が必要です。

## 一文での要約
TypeScriptの関数は、型安全な再利用可能なコードのブロックで、特定のタスクを実行するために使用されます。