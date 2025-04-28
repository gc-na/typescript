<!--
Meta Description: # TypeScriptのモジュール: 効果的なコード管理と再利用のための基本 ## 概要 TypeScriptのモジュールは、コードを分割し、管理するための仕組みです。モジュールを使用することで、再利用性が高く、保守性のあるプログラムを構築できます。TypeScriptは、JavaScriptのモ...
Meta Keywords: export, typescript, number, import, typescriptのモジュールは
-->

# TypeScriptのモジュール: 効果的なコード管理と再利用のための基本

## 概要
TypeScriptのモジュールは、コードを分割し、管理するための仕組みです。モジュールを使用することで、再利用性が高く、保守性のあるプログラムを構築できます。TypeScriptは、JavaScriptのモジュールシステムをサポートしており、ESモジュール（ESM）およびCommonJS形式の両方を使用できます。

## ドキュメンテーション
TypeScriptのモジュールは、独立したコードの単位であり、他のモジュールと連携することができます。モジュールを定義するには、`export`キーワードを使用して、モジュール内の関数、クラス、変数を外部に公開します。逆に、他のモジュールからの機能を利用するには、`import`キーワードを使用します。これにより、スコープを整理し、名前の衝突を避けることができます。

### モジュールの使用方法
1. **モジュールの作成**: モジュールを作成するには、ファイルを作成し、`export`を使って公開したい要素を指定します。
2. **モジュールのインポート**: 別のファイルからモジュールを利用するには、`import`文を使います。

### モジュールの詳細
- **ESモジュール**: TypeScriptはES6以降のモジュールをサポートしており、`import`および`export`文を使用します。
- **CommonJSモジュール**: Node.js環境では、`require`と`module.exports`を使用してモジュールを定義します。
- **デフォルトエクスポート**: モジュールから単一の値をエクスポートするためには、`export default`を使用します。

## 例
### モジュールの作成とインポート
**math.ts**
```typescript
export function add(x: number, y: number): number {
    return x + y;
}

export function subtract(x: number, y: number): number {
    return x - y;
}
```

**main.ts**
```typescript
import { add, subtract } from './math';

console.log(add(5, 3)); // 8
console.log(subtract(5, 3)); // 2
```

### デフォルトエクスポートの使用
**greeter.ts**
```typescript
export default function greet(name: string): string {
    return `Hello, ${name}!`;
}
```

**app.ts**
```typescript
import greet from './greeter';

console.log(greet('TypeScript')); // Hello, TypeScript!
```

## 説明
TypeScriptのモジュールを使用する際の一般的な落とし穴には、以下があります。
- **循環依存関係**: モジュール間で相互に依存する場合、循環参照エラーが発生する可能性があります。この問題を避けるために、依存関係を明確に整理することが重要です。
- **インポートの間違い**: モジュールをインポートする際に、正しいパスや名前を指定していないと、実行時エラーが発生します。
- **型の不一致**: 型の不一致がある場合、TypeScriptはコンパイルエラーを出力します。型を適切に定義することで、この問題を回避できます。

## 一言まとめ
TypeScriptのモジュールは、コードの整理と再利用を促進するための強力な機能です。