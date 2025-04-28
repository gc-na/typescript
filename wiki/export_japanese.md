<!--
Meta Description: # TypeScriptの「export」：モジュール間でのデータ共有 ## 概要 TypeScriptにおける「export」は、モジュールが他のモジュールに対して変数、関数、クラス、インターフェイスなどを公開するための構文です。この機能により、コードの再利用性が向上し、モジュールの依存関係が明確...
Meta Keywords: export, typescript, greeting, const, myvariable
-->

# TypeScriptの「export」：モジュール間でのデータ共有

## 概要
TypeScriptにおける「export」は、モジュールが他のモジュールに対して変数、関数、クラス、インターフェイスなどを公開するための構文です。この機能により、コードの再利用性が向上し、モジュールの依存関係が明確になります。

## ドキュメンテーション
### 目的
「export」キーワードは、TypeScriptモジュール内で定義されたエンティティを他のモジュールで利用できるようにするために使用されます。これにより、アプリケーションの構造を整理し、異なるファイル間でのコードの共有が可能になります。

### 使用法
`export`は、変数、関数、クラス、およびインターフェイスの前に記述することで使用します。以下は基本的な構文です。

```typescript
// 変数のエクスポート
export const myVariable = 42;

// 関数のエクスポート
export function myFunction() {
    return "Hello, World!";
}

// クラスのエクスポート
export class MyClass {
    constructor() {
        // コンストラクタの処理
    }
}

// インターフェイスのエクスポート
export interface MyInterface {
    property: string;
}
```

### エクスポートの詳細
TypeScriptでは、複数のエンティティを同時にエクスポートすることも可能です。その場合、以下のようにまとめてエクスポートできます。

```typescript
const myVariable = 42;
function myFunction() {
    return "Hello, World!";
}

export { myVariable, myFunction };
```

また、デフォルトエクスポートもサポートしており、モジュールが単一のエンティティをエクスポートする場合に使用されます。デフォルトエクスポートは以下のように定義します。

```typescript
export default class MyDefaultClass {
    // クラスの処理
}
```

## 例
以下は、`export`を使用した簡単な例です。

```typescript
// moduleA.ts
export const greeting = "こんにちは";

export function greet() {
    console.log(greeting);
}

// moduleB.ts
import { greeting, greet } from './moduleA';

greet(); // こんにちは
console.log(greeting); // こんにちは
```

## 説明
- **共通の落とし穴**: `export`を使用する際は、エクスポートされたエンティティ名が一意であることを確認する必要があります。同じ名前のエンティティを他のモジュールでエクスポートすると、名前の衝突が発生する可能性があります。
- **デフォルトエクスポートと名前付きエクスポート**: デフォルトエクスポートはモジュールが単一のエンティティをエクスポートする際に便利ですが、名前付きエクスポートは複数のエンティティをエクスポートする場合により適しています。どちらを使用するかは、プロジェクトのニーズに応じて選択してください。

## 一文要約
TypeScriptの「export」は、モジュール間で変数や関数などのエンティティを公開し、再利用性を高めるために使用される。