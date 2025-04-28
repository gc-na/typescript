<!--
Meta Description: # TypeScript `protected`: Zugriffsschutz für Klassenmitglieder ## Synopsis Der `protected`-Zugriff in TypeScript ermöglicht es, Klassenmitgliedern (Va...
Meta Keywords: protected, der, geschwindigkeit, und, klasse
-->

# TypeScript `protected`: Zugriffsschutz für Klassenmitglieder

## Synopsis
Der `protected`-Zugriff in TypeScript ermöglicht es, Klassenmitgliedern (Variablen und Methoden) einen eingeschränkten Zugriff zu gewähren. Diese Mitglieder sind innerhalb der Klasse selbst und in abgeleiteten Klassen zugänglich, jedoch nicht von außen.

## Dokumentation
### Zweck
Der `protected`-Modifikator dient dazu, bestimmte Eigenschaften und Methoden einer Klasse zu schützen. Er erlaubt es, dass diese Elemente nur innerhalb der Klasse und in ihren Unterklassen verwendet werden können. Dies ist besonders nützlich, um die interne Implementierung einer Klasse zu verbergen, während gleichzeitig eine kontrollierte Erweiterung durch abgeleitete Klassen ermöglicht wird.

### Verwendung
Um ein Klassenmitglied als `protected` zu deklarieren, wird der Modifikator vor der Deklaration des Mitglieds platziert. Hier ist ein Beispiel für die Verwendung:

```typescript
class Tier {
    protected name: string;

    constructor(name: string) {
        this.name = name;
    }

    protected singen(): string {
        return `${this.name} macht ein Geräusch.`;
    }
}

class Hund extends Tier {
    public bellen(): string {
        return `${this.name} bellt!`;
    }
}

const meinHund = new Hund("Rex");
console.log(meinHund.bellen()); // "Rex bellt!"
```

In diesem Beispiel ist die Eigenschaft `name` und die Methode `singen()` geschützt, sodass sie nur innerhalb der Klasse `Tier` und deren Unterklassen zugänglich sind.

## Beispiele
### Basisbeispiel
```typescript
class Fahrzeug {
    protected geschwindigkeit: number;

    constructor(geschwindigkeit: number) {
        this.geschwindigkeit = geschwindigkeit;
    }

    protected beschleunigen(increment: number): void {
        this.geschwindigkeit += increment;
    }
}

class Auto extends Fahrzeug {
    public turboBoost(): void {
        this.beschleunigen(50);
        console.log(`Neue Geschwindigkeit: ${this.geschwindigkeit}`);
    }
}

const meinAuto = new Auto(100);
meinAuto.turboBoost(); // "Neue Geschwindigkeit: 150"
```

### Zugriff von außen
```typescript
const meinFahrzeug = new Fahrzeug(80);
// meinFahrzeug.geschwindigkeit; // Fehler: Property 'geschwindigkeit' is protected and only accessible within class 'Fahrzeug' and its subclasses.
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `protected` ist das Missverständnis über den Zugriff von außen. Während `protected` den Zugriff innerhalb der Klasse und ihrer Unterklassen erlaubt, bleibt der Zugriff von Instanzen der Klasse oder von externen Klassen ausgeschlossen. Dies kann zu Verwirrung führen, wenn Entwickler erwarten, dass `protected` ähnlich wie `public` funktioniert. 

Ein weiterer Punkt ist, dass `protected`-Mitglieder nicht im gleichen Namensraum wie `public`-Mitglieder überschrieben werden sollten, um unerwartetes Verhalten zu vermeiden. Es ist wichtig, den Unterschied zwischen `private`, `protected` und `public` zu verstehen, um die richtige Sichtbarkeit für Klassenmitglieder auszuwählen.

## Ein Satz Zusammenfassung
Der `protected`-Modifikator in TypeScript ermöglicht den Zugriff auf Klassenmitglieder nur innerhalb der Klasse und deren Unterklassen, schützt sie jedoch vor externen Zugriffen.