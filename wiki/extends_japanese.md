<!--
Meta Description: # TypeScriptにおける「extends」の使い方 ## 概要 TypeScriptの「extends」は、クラスやインターフェースの継承を可能にするキーワードです。これにより、既存のクラスやインターフェースの機能を拡張し、新しい機能を追加することができます。 ## ドキュメンテーション #...
Meta Keywords: extends, console, log, dog, move
-->

# TypeScriptにおける「extends」の使い方

## 概要
TypeScriptの「extends」は、クラスやインターフェースの継承を可能にするキーワードです。これにより、既存のクラスやインターフェースの機能を拡張し、新しい機能を追加することができます。

## ドキュメンテーション
### 目的
「extends」は、クラスやインターフェースが他のクラスやインターフェースを基にして、新しいクラスやインターフェースを作成するために使用されます。これにより、コードの再利用性が向上し、オブジェクト指向プログラミングの原則に従った設計が可能になります。

### 使用法
- **クラスの継承**: 新しいクラスが基底クラスのプロパティやメソッドを継承します。
- **インターフェースの継承**: 新しいインターフェースが既存のインターフェースのメンバーを継承します。

### 詳細
1. **クラスの継承**:
    ```typescript
    class Animal {
        move() {
            console.log("動いています");
        }
    }

    class Dog extends Animal {
        bark() {
            console.log("ワンワン");
        }
    }

    const dog = new Dog();
    dog.move(); // 動いています
    dog.bark(); // ワンワン
    ```

2. **インターフェースの継承**:
    ```typescript
    interface Animal {
        move(): void;
    }

    interface Dog extends Animal {
        bark(): void;
    }

    const myDog: Dog = {
        move() {
            console.log("動いています");
        },
        bark() {
            console.log("ワンワン");
        }
    };

    myDog.move(); // 動いています
    myDog.bark(); // ワンワン
    ```

## 例
- **基本的なクラスの継承**:
    ```typescript
    class Vehicle {
        drive() {
            console.log("運転しています");
        }
    }

    class Car extends Vehicle {
        honk() {
            console.log("ビービー");
        }
    }

    const car = new Car();
    car.drive(); // 運転しています
    car.honk(); // ビービー
    ```

- **インターフェースの継承**:
    ```typescript
    interface Shape {
        area(): number;
    }

    interface Circle extends Shape {
        radius: number;
    }

    const myCircle: Circle = {
        radius: 5,
        area() {
            return Math.PI * this.radius * this.radius;
        }
    };

    console.log(myCircle.area()); // 78.53981633974483
    ```

## 説明
「extends」を使用する際の一般的な落とし穴として、基底クラスやインターフェースのメンバーをオーバーライドする際に、適切な型を保つことが重要です。また、クラスを多重継承することはできないため、他の手法（例えば、ミックスイン）を考慮する必要があります。

### 注意点
- クラスの継承は単一継承のみ。
- インターフェースは多重継承が可能。
- 継承したメソッドをオーバーライドする際、`super`キーワードを使って基底クラスのメソッドを呼び出せます。

## 一行要約
TypeScriptにおける「extends」は、クラスやインターフェースの継承を通じて、コードの再利用性と組織化を促進する重要な機能です。