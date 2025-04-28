<!--
Meta Description: # Private in TypeScript: Zugriffsmodifizierer für Klassen ## Synopsis In TypeScript ermöglicht der Zugriffsmodifizierer `private`, dass Eigenschaften ...
Meta Keywords: private, die, der, klasse, von
-->

# Private in TypeScript: Zugriffsmodifizierer für Klassen

## Synopsis
In TypeScript ermöglicht der Zugriffsmodifizierer `private`, dass Eigenschaften und Methoden einer Klasse nur innerhalb derselben Klasse zugänglich sind, wodurch die Kapselung von Daten gefördert wird.

## Dokumentation
Der `private`-Modifizierer ist ein zentraler Bestandteil der objektorientierten Programmierung in TypeScript. Er wird verwendet, um die Sichtbarkeit von Klassenmitgliedern (Eigenschaften und Methoden) zu steuern. Wenn ein Klassenmitglied als `private` deklariert wird, kann es nur innerhalb der Klasse selbst verwendet werden. Dies bedeutet, dass weder Instanzen der Klasse noch Unterklassen auf diese Mitglieder zugreifen können.

### Verwendung
Die Verwendung des `private`-Schlüsselworts erfolgt direkt vor der Deklaration von Eigenschaften oder Methoden innerhalb einer Klasse:

```typescript
class Beispiel {
    private geheimnis: string;

    constructor() {
        this.geheimnis = "Dies ist privat";
    }

    private zeigeGeheimnis(): string {
        return this.geheimnis;
    }

    public zeigeGeheimnisÖffentlich(): string {
        return this.zeigeGeheimnis();
    }
}
```

In diesem Beispiel ist sowohl die Eigenschaft `geheimnis` als auch die Methode `zeigeGeheimnis` privat und können nur innerhalb der Klasse `Beispiel` aufgerufen werden. Die öffentliche Methode `zeigeGeheimnisÖffentlich` ist der einzige Weg, um auf `zeigeGeheimnis` zuzugreifen.

## Beispiele
Hier sind einige grundlegende Beispiele, wie `private` in TypeScript verwendet wird:

### Beispiel 1: Private Eigenschaft
```typescript
class Auto {
    private hersteller: string;

    constructor(hersteller: string) {
        this.hersteller = hersteller;
    }

    public getHersteller(): string {
        return this.hersteller;
    }
}

const meinAuto = new Auto("Volkswagen");
console.log(meinAuto.getHersteller()); // Ausgabe: Volkswagen
// console.log(meinAuto.hersteller); // Fehler: Eigenschaft "hersteller" ist privat
```

### Beispiel 2: Private Methode
```typescript
class Rechner {
    private addiere(a: number, b: number): number {
        return a + b;
    }

    public berechne(a: number, b: number): number {
        return this.addiere(a, b);
    }
}

const meinRechner = new Rechner();
console.log(meinRechner.berechne(5, 3)); // Ausgabe: 8
// console.log(meinRechner.addiere(5, 3)); // Fehler: Methode "addiere" ist privat
```

## Erklärung
Die Verwendung von `private` kann dazu beitragen, die Integrität und Sicherheit von Objekten zu gewährleisten, indem die direkte Manipulation von internen Daten von außen verhindert wird. Ein häufiger Stolperstein für Entwickler ist, dass sie versuchen, auf private Mitglieder von außerhalb der Klasse zuzugreifen, was zu Fehlern führt. Es ist wichtig, sich daran zu erinnern, dass der Zweck von `private` darin besteht, die interne Logik einer Klasse zu schützen.

Zusätzlich sollte beachtet werden, dass in TypeScript auch die Zugriffsmodifizierer `public` und `protected` existieren, die unterschiedliche Sichtbarkeiten bieten. Während `public` für alle zugänglich ist und `protected` den Zugriff nur für die Klasse selbst und deren Unterklassen erlaubt, sorgt `private` für die strengste Kapselung.

## Ein-Satz-Zusammenfassung
Der `private` Zugriffsmodifizierer in TypeScript schützt Klassenmitglieder vor Zugriff von außerhalb der Klasse und fördert somit die Datenkapselung.