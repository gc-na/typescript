<!--
Meta Description: # Verwendung von "super" in TypeScript: Ein umfassender Leitfaden ## Synopsis Der `super`-Befehl in TypeScript wird verwendet, um auf Eigenschaften un...
Meta Keywords: der, super, klasse, von, einer
-->

# Verwendung von "super" in TypeScript: Ein umfassender Leitfaden

## Synopsis
Der `super`-Befehl in TypeScript wird verwendet, um auf Eigenschaften und Methoden der übergeordneten Klasse innerhalb einer abgeleiteten Klasse zuzugreifen. Dies ist besonders nützlich in der objektorientierten Programmierung, um Vererbung und Polymorphismus zu implementieren.

## Dokumentation
In TypeScript ist `super` ein Schlüsselwort, das in einer abgeleiteten Klasse verwendet wird, um auf die statischen und nicht-statischen Mitglieder (Eigenschaften und Methoden) der übergeordneten Klasse zuzugreifen. Es wird häufig innerhalb von Konstruktoren, Methoden oder Getter/Setter verwendet.

### Zweck
- **Zugriff auf übergeordnete Mitglieder**: Mit `super` können Sie die Eigenschaften und Methoden der Elternklasse aufrufen, ohne den Namen der Elternklasse explizit anzugeben.
- **Konstruktoren**: Im Konstruktor einer abgeleiteten Klasse muss `super()` aufgerufen werden, bevor `this` verwendet wird.

### Verwendung
- Verwendung von `super` zur Aufruf von Methoden:
  ```typescript
  class Eltern {
      greet() {
          console.log("Hallo von der Elternklasse!");
      }
  }

  class Kind extends Eltern {
      greet() {
          super.greet(); // Aufruf der Methode der Elternklasse
          console.log("Hallo von der Kindklasse!");
      }
  }
  ```

- Verwendung von `super` im Konstruktor:
  ```typescript
  class Fahrzeug {
      constructor(public name: string) {
          console.log(`Fahrzeug erstellt: ${name}`);
      }
  }

  class Auto extends Fahrzeug {
      constructor(name: string, public typ: string) {
          super(name); // Aufruf des Konstruktors der Elternklasse
          console.log(`Auto erstellt: ${typ}`);
      }
  }
  ```

## Beispiele
### Beispiel 1: Aufruf einer Methode der Elternklasse
```typescript
class Tier {
    speak() {
        console.log("Tier macht Geräusch");
    }
}

class Hund extends Tier {
    speak() {
        super.speak(); // Aufruf der speak-Methode der Elternklasse
        console.log("Hund bellt");
    }
}

const meinHund = new Hund();
meinHund.speak();
// Ausgabe:
// Tier macht Geräusch
// Hund bellt
```

### Beispiel 2: Verwendung im Konstruktor
```typescript
class Person {
    constructor(public name: string) {
        console.log(`Person erstellt: ${name}`);
    }
}

class Mitarbeiter extends Person {
    constructor(name: string, public position: string) {
        super(name); // Aufruf des Konstruktors der Elternklasse
        console.log(`Mitarbeiter erstellt: ${position}`);
    }
}

const meinMitarbeiter = new Mitarbeiter("Max", "Entwickler");
// Ausgabe:
// Person erstellt: Max
// Mitarbeiter erstellt: Entwickler
```

## Erklärung
Ein häufiger Fallstrick beim Arbeiten mit `super` ist, sicherzustellen, dass der `super()`-Aufruf im Konstruktor der abgeleiteten Klasse vor der Verwendung von `this` erfolgt. Andernfalls führt dies zu einem Fehler, da die Instanz der abgeleiteten Klasse noch nicht vollständig initialisiert ist.

Zusätzlich ist es wichtig zu beachten, dass `super` nur innerhalb einer abgeleiteten Klasse verwendet werden kann und nicht in einer anderen Kontextform, z.B. in einer Funktion, die nicht Teil einer Klasse ist. 

## Ein Satz Zusammenfassung
Das `super`-Schlüsselwort in TypeScript ermöglicht den Zugriff auf Eigenschaften und Methoden der Elternklasse innerhalb einer abgeleiteten Klasse, was die Implementierung von Vererbung und Polymorphismus erleichtert.