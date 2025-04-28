<!--
Meta Description: # Klassen in TypeScript: Eine umfassende Anleitung ## Synopsis In TypeScript ermöglichen Klassen die Erstellung von Objekten mit gemeinsamen Eigenscha...
Meta Keywords: und, klassen, typescript, die, der
-->

# Klassen in TypeScript: Eine umfassende Anleitung

## Synopsis
In TypeScript ermöglichen Klassen die Erstellung von Objekten mit gemeinsamen Eigenschaften und Methoden, die durch die objektorientierte Programmierung unterstützt werden. Sie bieten eine strukturierte Möglichkeit, Code zu organisieren und wiederverwendbare Komponenten zu erstellen.

## Dokumentation
In TypeScript sind Klassen eine grundlegende Struktur zur Definition von Objekten und deren Verhalten. Sie basieren auf dem Konzept der objektorientierten Programmierung (OOP) und unterstützen Merkmale wie Vererbung, Kapselung und Polymorphismus. 

### Zweck
Der Hauptzweck von Klassen in TypeScript ist es, eine klare und strukturierte Möglichkeit zu bieten, komplexe Datenstrukturen und deren Logik zu definieren. Klassen helfen dabei, den Code besser zu organisieren und wiederverwendbare Komponenten zu erstellen.

### Verwendung
Klassen werden mit dem Schlüsselwort `class` definiert. Sie können Konstruktoren, Methoden und Eigenschaften enthalten. Hier ist ein einfaches Beispiel:

```typescript
class Auto {
    // Eigenschaften
    marke: string;
    baujahr: number;

    // Konstruktor
    constructor(marke: string, baujahr: number) {
        this.marke = marke;
        this.baujahr = baujahr;
    }

    // Methode
    fahren(): void {
        console.log(`${this.marke} fährt.`);
    }
}
```

### Details
- **Konstruktor**: Die Methode `constructor` wird aufgerufen, wenn eine neue Instanz der Klasse erstellt wird.
- **Methoden**: Klassen können Methoden enthalten, die auf die Eigenschaften der Instanz zugreifen.
- **Vererbung**: Klassen können von anderen Klassen erben, um deren Eigenschaften und Methoden zu nutzen.
  
```typescript
class ElektroAuto extends Auto {
    batterieKapazitaet: number;

    constructor(marke: string, baujahr: number, batterieKapazitaet: number) {
        super(marke, baujahr); // Aufruf des Konstruktors der Basisklasse
        this.batterieKapazitaet = batterieKapazitaet;
    }

    laden(): void {
        console.log(`${this.marke} wird geladen.`);
    }
}
```

## Beispiele
### Grundlegende Nutzung
Hier ist ein Beispiel zur Erstellung einer Instanz der Klasse `Auto` und der Aufruf ihrer Methode:

```typescript
const meinAuto = new Auto("Volkswagen", 2021);
meinAuto.fahren(); // Ausgabe: Volkswagen fährt.
```

### Vererbung
Die Verwendung der `ElektroAuto`-Klasse:

```typescript
const meinElektroAuto = new ElektroAuto("Tesla", 2022, 100);
meinElektroAuto.fahren(); // Ausgabe: Tesla fährt.
meinElektroAuto.laden(); // Ausgabe: Tesla wird geladen.
```

## Erklärung
Ein häufiger Stolperstein bei der Arbeit mit Klassen in TypeScript ist die Verwendung von `this`. Stellen Sie sicher, dass `this` im richtigen Kontext verwendet wird, insbesondere wenn Methoden als Callback-Funktionen übergeben werden. Ein weiterer Punkt ist die Sichtbarkeit von Eigenschaften und Methoden. Standardmäßig sind sie öffentlich; Sie können jedoch `private` und `protected` verwenden, um den Zugriff zu steuern.

### Gotchas
- Vererbung in TypeScript funktioniert nicht mit dem `extends`-Schlüsselwort für Funktionen oder Objekte, sondern nur für Klassen.
- Stellen Sie sicher, dass der Konstruktor der Basisklasse mit `super()` aufgerufen wird, sonst erhalten Sie einen Fehler.

## Ein-Satz-Zusammenfassung
Klassen in TypeScript sind ein leistungsstarkes Mittel zur Definition von Objekten und deren Verhalten, die die objektorientierte Programmierung unterstützen.