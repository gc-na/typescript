<!--
Meta Description: # TypeScriptの「protected」アクセス修飾子について ## 概要 TypeScriptにおける「protected」は、クラスのメンバーにアクセス制限を設けるためのアクセス修飾子です。この修飾子を使用することで、同じクラスまたはそのサブクラスからのみ、特定のメンバーにアクセスできる...
Meta Keywords: protected, sound, dog, class, string
-->

# TypeScriptの「protected」アクセス修飾子について

## 概要
TypeScriptにおける「protected」は、クラスのメンバーにアクセス制限を設けるためのアクセス修飾子です。この修飾子を使用することで、同じクラスまたはそのサブクラスからのみ、特定のメンバーにアクセスできるようになります。

## ドキュメンテーション
「protected」は、クラスのプロパティやメソッドに適用され、外部からのアクセスを制限しますが、サブクラス内ではアクセス可能です。これにより、クラスの内部実装を隠蔽しつつ、継承を通じて機能を拡張することができます。

### 使用方法
「protected」を使用するには、クラスのメンバー宣言の前にキーワード「protected」を記述します。以下にその基本的な構文を示します。

```typescript
class Base {
    protected property: string;

    constructor(value: string) {
        this.property = value;
    }

    protected method(): void {
        console.log(this.property);
    }
}

class Derived extends Base {
    public show(): void {
        this.method(); // サブクラスから呼び出し可能
    }
}
```

## 例
以下は「protected」を使用した基本的な例です。

```typescript
class Animal {
    protected sound: string;

    constructor(sound: string) {
        this.sound = sound;
    }

    protected makeSound(): void {
        console.log(this.sound);
    }
}

class Dog extends Animal {
    public bark(): void {
        this.makeSound(); // 'makeSound'はサブクラスから呼び出し可能
    }
}

const dog = new Dog('ワンワン');
dog.bark(); // 出力: ワンワン
```

この例では、`Animal`クラスの`makeSound`メソッドは`protected`として定義されており、`Dog`クラスからアクセスできます。

## 説明
「protected」を使用する際の一般的な落とし穴や注意点は以下の通りです。

- **外部からのアクセス不可**: 「protected」メンバーは、同じクラスおよびそのサブクラスからのみアクセス可能であり、インスタンス化したオブジェクトからはアクセスできません。
  
- **サブクラスの利用**: サブクラスで「protected」メンバーを利用する際は、必ず同じクラスまたはその親クラスのメンバーにアクセスすることを意識する必要があります。

- **アクセス制限の理解**: 他のアクセス修飾子（`public`や`private`）と比較して、「protected」は継承を利用した設計において非常に便利ですが、適切に設計しないと、クラスの意図が不明確になることがあります。

## 一文要約
TypeScriptの「protected」は、クラス内およびそのサブクラスからのみアクセス可能なメンバーを定義するためのアクセス修飾子です。