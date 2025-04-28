<!--
Meta Description: # TypeScriptにおける「static」の使い方 ## 概要 TypeScriptの「static」キーワードは、クラスのプロパティやメソッドをインスタンス化せずにアクセスできるようにするために使用されます。これにより、クラスの特定の機能やデータを共有することが可能になります。 ## ドキュ...
Meta Keywords: static, number, console, log, counter
-->

# TypeScriptにおける「static」の使い方

## 概要
TypeScriptの「static」キーワードは、クラスのプロパティやメソッドをインスタンス化せずにアクセスできるようにするために使用されます。これにより、クラスの特定の機能やデータを共有することが可能になります。

## ドキュメント
「static」は、クラス内部で宣言されるメンバーに適用されます。これにより、そのメンバーはクラス自体に属し、インスタンスを作成しなくてもアクセスすることができます。一般的に、ユーティリティメソッドやクラス全体で共有するデータに使用されます。

### 使用法
```typescript
class MyClass {
    static staticProperty: string = "これは静的プロパティです";

    static staticMethod(): void {
        console.log("これは静的メソッドです");
    }
}

// 静的プロパティにアクセス
console.log(MyClass.staticProperty); // "これは静的プロパティです"

// 静的メソッドを呼び出し
MyClass.staticMethod(); // "これは静的メソッドです"
```

## 例
以下は、TypeScriptでの「static」の基本的な使用例です。

### 静的プロパティの例
```typescript
class Counter {
    static count: number = 0;

    static increment(): void {
        this.count++;
    }

    static getCount(): number {
        return this.count;
    }
}

Counter.increment();
Counter.increment();
console.log(Counter.getCount()); // 出力: 2
```

### 静的メソッドの例
```typescript
class MathUtils {
    static multiply(a: number, b: number): number {
        return a * b;
    }
}

console.log(MathUtils.multiply(2, 3)); // 出力: 6
```

## 説明
静的メンバーは、インスタンスを介さずに直接クラス名を使ってアクセスします。これは、クラスのインスタンスが不要なユーティリティ関数や共通の状態を管理する場合に便利です。ただし、以下の注意点に留意してください。

- **インスタンスメンバーとの違い**: 静的メンバーはインスタンスメンバーと異なり、クラスのインスタンスを生成しなくてもアクセス可能です。
- **継承の際の振る舞い**: 静的メンバーは親クラスから子クラスに継承されますが、子クラスから親クラスの静的メンバーにアクセスすることはできません。

## 一言でのまとめ
TypeScriptの「static」キーワードは、クラスに直接関連付けられたプロパティやメソッドを定義し、インスタンス化せずにアクセスできるようにするために使用されます。