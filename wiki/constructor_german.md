<!--
Meta Description: # TypeScript Konstruktor: Eine umfassende Anleitung ## Synopsis Der Konstruktor in TypeScript ist eine spezielle Methode einer Klasse, die beim Erstel...
Meta Keywords: name, konstruktor, string, der, typescript
-->

# TypeScript Konstruktor: Eine umfassende Anleitung

## Synopsis
Der Konstruktor in TypeScript ist eine spezielle Methode einer Klasse, die beim Erstellen einer Instanz der Klasse aufgerufen wird. Er dient dazu, die Anfangswerte von Eigenschaften festzulegen und die Klasse zu initialisieren.

## Dokumentation
In TypeScript ist ein Konstruktor eine Methode, die mit dem Schlüsselwort `constructor` definiert wird. Diese Methode wird automatisch aufgerufen, wenn eine neue Instanz der Klasse erstellt wird. Der Konstruktor kann Parameter akzeptieren, die verwendet werden, um die Eigenschaften der Klasse zu initialisieren.

### Zweck
Der Hauptzweck des Konstruktors ist es, das Objekt in einen gültigen Zustand zu versetzen, indem erforderliche Initialisierungen durchgeführt werden.

### Verwendung
Um einen Konstruktor zu definieren, platzieren Sie das Schlüsselwort `constructor` innerhalb der Klassendefinition. Hier ist ein einfaches Beispiel:

```typescript
class Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }
}

const person = new Person("Max");
console.log(person.name); // Ausgabe: Max
```

### Details
- Ein Konstruktor kann nur einmal pro Klasse definiert werden.
- Wenn kein Konstruktor definiert ist, erstellt TypeScript automatisch einen Standardkonstruktor, der keine Parameter hat.
- Konstruktoren können auch überladen werden, indem verschiedene Parameterlisten definiert werden, jedoch muss die Implementierung für jede Überladung im Konstruktor selbst behandelt werden.

## Beispiele
### Einfacher Konstruktor
```typescript
class Auto {
    marke: string;
    baujahr: number;

    constructor(marke: string, baujahr: number) {
        this.marke = marke;
        this.baujahr = baujahr;
    }
}

const meinAuto = new Auto("Volkswagen", 2020);
console.log(meinAuto.marke); // Ausgabe: Volkswagen
```

### Konstruktor mit optionalen Parametern
```typescript
class Tier {
    name: string;
    art?: string; // optionaler Parameter

    constructor(name: string, art?: string) {
        this.name = name;
        this.art = art;
    }
}

const hund = new Tier("Bello");
console.log(hund.art); // Ausgabe: undefined
```

## Erklärung
Ein häufiges Problem, auf das Entwickler stoßen, ist die Vergesslichkeit, den `super()`-Aufruf in abgeleiteten Klassen zu verwenden. In TypeScript muss der Konstruktor einer abgeleiteten Klasse den Konstruktor der Basisklasse aufrufen, bevor er auf `this` zugreift:

```typescript
class Tier {
    name: string;

    constructor(name: string) {
        this.name = name;
    }
}

class Hund extends Tier {
    rasse: string;

    constructor(name: string, rasse: string) {
        super(name); // Wichtig: super() muss aufgerufen werden
        this.rasse = rasse;
    }
}
```

Ein weiteres häufiges Missverständnis besteht darin, dass Konstruktoren nicht die Rückgabewerte wie normale Funktionen haben. Sie dienen ausschließlich zur Initialisierung des Objekts.

## Einzeilensummary
Der Konstruktor in TypeScript ermöglicht die Initialisierung von Klasseninstanzen beim Erstellen neuer Objekte.