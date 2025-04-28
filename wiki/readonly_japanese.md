<!--
Meta Description: # TypeScriptにおける「readonly」キーワードの徹底解説 ## 概要 TypeScriptの「readonly」キーワードは、オブジェクトのプロパティや配列の要素を不変にするための機能です。これにより、データの整合性を保ちながら、安全にコードを記述することができます。 ## ドキュメ...
Meta Keywords: readonly, property, string, typescript, エラー
-->

# TypeScriptにおける「readonly」キーワードの徹底解説

## 概要
TypeScriptの「readonly」キーワードは、オブジェクトのプロパティや配列の要素を不変にするための機能です。これにより、データの整合性を保ちながら、安全にコードを記述することができます。

## ドキュメンテーション
### 目的
「readonly」は、TypeScriptにおいて特定のプロパティが変更されないことを保証するために使用されます。これにより、意図しない変更からデータを保護し、コードの信頼性を向上させます。

### 使用法
「readonly」は、クラスのプロパティやインターフェースのプロパティに適用可能です。次のように定義します。

```typescript
class Example {
    readonly property: string;

    constructor(prop: string) {
        this.property = prop;
    }
}

const example = new Example("Hello");
// example.property = "World"; // エラー: Cannot assign to 'property' because it is a read-only property.
```

### 詳細
- **クラスのプロパティ**: クラス内で定義されたプロパティに「readonly」を付けることで、そのプロパティはコンストラクタ内でのみ設定可能になります。
- **インターフェースのプロパティ**: インターフェースでも「readonly」を使用することができ、オブジェクトの形状を定義する際に特定のプロパティが変更不可であることを示します。

```typescript
interface ReadonlyInterface {
    readonly id: number;
    name: string;
}

const obj: ReadonlyInterface = { id: 1, name: "TypeScript" };
// obj.id = 2; // エラー: Cannot assign to 'id' because it is a read-only property.
```

## 例
以下に「readonly」を使用した基本的な例を示します。

### クラスの例
```typescript
class User {
    readonly username: string;

    constructor(name: string) {
        this.username = name;
    }
}

const user = new User("Alice");
// user.username = "Bob"; // エラー: Cannot assign to 'username' because it is a read-only property.
```

### インターフェースの例
```typescript
interface Point {
    readonly x: number;
    readonly y: number;
}

const point: Point = { x: 10, y: 20 };
// point.x = 15; // エラー: Cannot assign to 'x' because it is a read-only property.
```

## 説明
「readonly」を使用する際の一般的な落とし穴や注意点は以下の通りです。

- **不変性についての誤解**: 「readonly」はプロパティの不変性を保証しますが、オブジェクト自体の不変性を保証するものではありません。オブジェクトのネストされたプロパティは変更可能です。
- **配列に対する注意**: 配列に「readonly」を適用した場合、配列自体は変更できませんが、要素の値がオブジェクトである場合、そのオブジェクトのプロパティは変更可能です。

```typescript
readonly string[] readonlyArray = ["a", "b", "c"];
// readonlyArray.push("d"); // エラー: Property 'push' does not exist on type 'readonly string[]'.
```

## 1行要約
TypeScriptの「readonly」キーワードは、オブジェクトや配列の特定のプロパティを不変にすることで、データの整合性を保つための強力な機能です。