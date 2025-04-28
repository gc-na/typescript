<!--
Meta Description: # TypeScriptにおける「default」の使い方 ## 概要 TypeScriptでは、「default」はモジュールのエクスポートやインポートにおいて、デフォルトエクスポートを指定するために使用されます。この機能により、モジュールをより直感的に扱うことができ、コードの可読性が向上します。...
Meta Keywords: typescript, default, greet, myfunction, hello
-->

# TypeScriptにおける「default」の使い方

## 概要
TypeScriptでは、「default」はモジュールのエクスポートやインポートにおいて、デフォルトエクスポートを指定するために使用されます。この機能により、モジュールをより直感的に扱うことができ、コードの可読性が向上します。

## ドキュメンテーション
「default」は、TypeScriptのモジュールシステムにおける重要な要素です。モジュールは、他のファイルから機能やデータをエクスポートし、またインポートすることを可能にします。デフォルトエクスポートは、特定のモジュールから一つの主要なエクスポートを指定する方法です。

### 目的
デフォルトエクスポートを使用することで、モジュールが提供する主要な機能を簡単にインポートでき、スムーズなコーディング体験を実現します。

### 使用法
デフォルトエクスポートを行うには、以下のように`export default`を使用します：

```typescript
// モジュールの定義
const myFunction = () => {
    console.log("Hello, TypeScript!");
};

export default myFunction;
```

インポートする際は、以下のように記述します：

```typescript
import myFunction from './myModule';

myFunction(); // "Hello, TypeScript!"と表示
```

## 例
以下は、デフォルトエクスポートとインポートの具体的な例です。

### 例1: デフォルト関数のエクスポート
```typescript
// greet.ts
const greet = (name: string) => `Hello, ${name}!`;
export default greet;
```

### 例2: デフォルト関数のインポート
```typescript
// app.ts
import greet from './greet';

console.log(greet('TypeScript')); // "Hello, TypeScript!"と表示
```

## 説明
デフォルトエクスポートを使用する際の一般的な注意点や落とし穴には、以下のようなものがあります。

- **名前の衝突**: 一つのモジュールからデフォルトエクスポートを使用する場合、他のエクスポートとの名前が衝突する可能性があります。この場合、インポート時に異なる名前を指定することができます。
  
- **複数のデフォルトエクスポート**: TypeScriptでは、一つのモジュールから複数のデフォルトエクスポートを行うことはできません。デフォルトエクスポートはモジュールあたり一つだけです。

- **インポートの柔軟性**: デフォルトエクスポートは、インポート時に任意の名前を使用できるため、複数のモジュールから同名のエクスポートをインポートする際に便利です。

## 一文要約
TypeScriptの「default」は、モジュールから主要な機能をエクスポートし、簡潔にインポートするための重要な手段です。