<!--
Meta Description: # Der "new"-Operator in TypeScript: Instanziierung von Objekten ## Synopsis Der "new"-Operator in TypeScript wird verwendet, um Instanzen von Klassen ...
Meta Keywords: new, der, von, operator, typescript
-->

# Der "new"-Operator in TypeScript: Instanziierung von Objekten

## Synopsis
Der "new"-Operator in TypeScript wird verwendet, um Instanzen von Klassen zu erstellen und ermöglicht die Verwendung von Konstruktoren zur Initialisierung von Objekten.

## Documentation
Der "new"-Operator ist ein zentraler Bestandteil der objektorientierten Programmierung in TypeScript. Er wird eingesetzt, um eine neue Instanz einer Klasse zu erstellen. Bei der Verwendung von "new" wird der Konstruktor der Klasse aufgerufen, und das neu erstellte Objekt wird zurückgegeben.

### Zweck
- Erstellen von Instanzen von Klassen.
- Aufrufen des Konstruktors zur Initialisierung von Eigenschaften.

### Verwendung
Um den "new"-Operator zu verwenden, muss eine Klasse definiert sein. Der Operator wird gefolgt von dem Klassennamen und gegebenenfalls den notwendigen Argumenten für den Konstruktor.

```typescript
class Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }
}

const person1 = new Person("Max");
```

## Examples
Hier sind einige grundlegende Anwendungsbeispiele des "new"-Operators:

### Beispiel 1: Einfache Klasseninstanz
```typescript
class Tier {
    art: string;

    constructor(art: string) {
        this.art = art;
    }
}

const hund = new Tier("Hund");
console.log(hund.art); // Ausgabe: Hund
```

### Beispiel 2: Konstruktor mit mehreren Parametern
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
console.log(`${meinAuto.marke}, Baujahr: ${meinAuto.baujahr}`); // Ausgabe: Volkswagen, Baujahr: 2020
```

### Beispiel 3: Vererbung
```typescript
class Fahrzeug {
    geschwindigkeit: number;

    constructor(geschwindigkeit: number) {
        this.geschwindigkeit = geschwindigkeit;
    }
}

class Motorrad extends Fahrzeug {
    typ: string;

    constructor(geschwindigkeit: number, typ: string) {
        super(geschwindigkeit);
        this.typ = typ;
    }
}

const meinMotorrad = new Motorrad(180, "Sport");
console.log(`${meinMotorrad.typ} mit ${meinMotorrad.geschwindigkeit} km/h`); // Ausgabe: Sport mit 180 km/h
```

## Explanation
Ein häufiger Stolperstein ist die Verwendung von "new" ohne die Definition einer Klasse. Dies führt zu einem Fehler, da der "new"-Operator nur mit Klassen funktioniert. Ebenso kann es zu Verwirrung kommen, wenn man versucht, den "new"-Operator auf Funktionen anzuwenden, die keine Klassen sind. Es ist wichtig, sicherzustellen, dass die Argumente, die an den Konstruktor übergeben werden, die richtige Anzahl und den richtigen Typ haben, um Laufzeitfehler zu vermeiden.

Ein weiterer wichtiger Punkt ist, dass der "new"-Operator immer ein neues Objekt erstellt. Dies bedeutet, dass bei jedem Aufruf eine neue Instanz generiert wird, was bei der Handhabung von Zuständen berücksichtigt werden muss.

## One Line Summary
Der "new"-Operator in TypeScript wird verwendet, um neue Instanzen von Klassen zu erstellen und deren Konstruktoren zur Initialisierung aufzurufen.