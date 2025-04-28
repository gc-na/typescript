<!--
Meta Description: # TypeScript "extends" Schlüsselwort: Verwendung und Bedeutung ## Synopsis Das "extends" Schlüsselwort in TypeScript wird verwendet, um Vererbung und ...
Meta Keywords: von, die, extends, und, das
-->

# TypeScript "extends" Schlüsselwort: Verwendung und Bedeutung

## Synopsis
Das "extends" Schlüsselwort in TypeScript wird verwendet, um Vererbung und Schnittstellenvererbung zu implementieren, wodurch die Wiederverwendbarkeit von Code erhöht wird und Typen erzeugt werden können, die auf bestehenden Typen basieren.

## Dokumentation
In TypeScript ist das "extends" Schlüsselwort ein zentrales Element der objektorientierten Programmierung. Es ermöglicht einer Klasse, von einer anderen Klasse zu erben, oder einer Schnittstelle, von einer anderen Schnittstelle zu erben. Durch die Verwendung von "extends" können Entwickler eine Hierarchie von Typen schaffen, die sowohl Funktionen als auch Eigenschaften von übergeordneten Typen erben.

### Zweck
Der Hauptzweck von "extends" besteht darin, die Wiederverwendbarkeit von Code zu fördern und die Struktur von Programmen zu verbessern, indem eine klare Beziehung zwischen Typen hergestellt wird.

### Verwendung
1. **Klassenvererbung**: Eine Klasse kann von einer anderen Klasse erben, um deren Eigenschaften und Methoden zu übernehmen.
2. **Schnittstellenvererbung**: Eine Schnittstelle kann von einer anderen Schnittstelle erben, um deren Typen zu erweitern.

### Details
- Bei der Klassenvererbung wird die Basisklasse als Parameter an das Schlüsselwort "extends" übergeben.
- Bei der Schnittstellenvererbung wird ebenfalls das Schlüsselwort "extends" verwendet, um die Beziehung zwischen den Schnittstellen klarzustellen.
- TypeScript unterstützt auch Mehrfachvererbung über Schnittstellen, jedoch nicht bei Klassen.

## Beispiele

### Beispiel 1: Klassenvererbung

```typescript
class Tier {
    geschlecht: string;

    constructor(geschlecht: string) {
        this.geschlecht = geschlecht;
    }

    macheGeräusch(): void {
        console.log("Das Tier macht ein Geräusch.");
    }
}

class Hund extends Tier {
    macheGeräusch(): void {
        console.log("Der Hund bellt.");
    }
}

const meinHund = new Hund("männlich");
meinHund.macheGeräusch(); // Ausgabe: Der Hund bellt.
```

### Beispiel 2: Schnittstellenvererbung

```typescript
interface Fahrzeug {
    geschwindigkeit: number;
    fahren(): void;
}

interface Elektrofahrzeug extends Fahrzeug {
    ladeBatterie(): void;
}

class EAuto implements Elektrofahrzeug {
    geschwindigkeit: number;

    constructor(geschwindigkeit: number) {
        this.geschwindigkeit = geschwindigkeit;
    }

    fahren(): void {
        console.log(`Das Elektrofahrzeug fährt mit ${this.geschwindigkeit} km/h.`);
    }

    ladeBatterie(): void {
        console.log("Die Batterie wird geladen.");
    }
}

const meinEAuto = new EAuto(120);
meinEAuto.fahren(); // Ausgabe: Das Elektrofahrzeug fährt mit 120 km/h.
meinEAuto.ladeBatterie(); // Ausgabe: Die Batterie wird geladen.
```

## Erklärung
Ein häufiger Stolperstein beim Arbeiten mit "extends" ist das Verständnis der Vererbungshierarchie. Wenn eine Klasse von einer anderen Klasse erbt, hat die abgeleitete Klasse Zugriff auf die öffentlichen und geschützten Eigenschaften und Methoden der Basisklasse. Es ist wichtig, die Sichtbarkeit von Eigenschaften und Methoden zu berücksichtigen, da private Mitglieder nicht vererbt werden können.

Ein weiterer Punkt ist, dass TypeScript keine Mehrfachvererbung von Klassen unterstützt, was bedeutet, dass eine Klasse nur von einer anderen Klasse erben kann. Beim Arbeiten mit Schnittstellen können jedoch mehrere Schnittstellen gleichzeitig implementiert werden, was eine flexible Typdefinition ermöglicht.

## Einzeilensummary
Das "extends" Schlüsselwort in TypeScript ermöglicht die Vererbung von Klassen und Schnittstellen, was die Wiederverwendbarkeit und Strukturierung von Code verbessert.