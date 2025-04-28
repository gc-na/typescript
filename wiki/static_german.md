<!--
Meta Description: # Das Schlüsselwort "static" in TypeScript: Eine umfassende Anleitung ## Synopsis Das Schlüsselwort "static" in TypeScript ermöglicht es Entwicklern, ...
Meta Keywords: die, static, der, klasse, typescript
-->

# Das Schlüsselwort "static" in TypeScript: Eine umfassende Anleitung

## Synopsis
Das Schlüsselwort "static" in TypeScript ermöglicht es Entwicklern, statische Eigenschaften und Methoden innerhalb von Klassen zu definieren, die nicht an Instanzen der Klasse gebunden sind, sondern zur Klasse selbst gehören.

## Dokumentation
In TypeScript ermöglicht das Schlüsselwort "static" die Definition von Eigenschaften und Methoden, die auf die Klasse selbst und nicht auf ihre Instanzen zugreifen. Diese statischen Mitglieder sind nützlich, um Funktionen zu implementieren, die nicht auf den Zustand eines Objekts angewiesen sind. Sie können direkt über den Klassennamen aufgerufen werden, ohne dass eine Instanz der Klasse erstellt werden muss.

### Zweck
Der Hauptzweck von "static" ist es, gemeinsame Funktionen oder Konstanten zu definieren, die für alle Instanzen einer Klasse relevant sind, ohne dass ein Objekt erstellt werden muss. Dies fördert die Wiederverwendbarkeit und Organisation des Codes.

### Verwendung
Um eine statische Eigenschaft oder Methode zu definieren, wird das Schlüsselwort "static" vor der Eigenschaft oder Methode in der Klassendeklaration verwendet. Hier ist die grundlegende Syntax:

```typescript
class MeineKlasse {
    static meineStatischeEigenschaft: number = 42;

    static meineStatischeMethode(): string {
        return "Hallo von der statischen Methode!";
    }
}
```

## Beispiele
### Beispiel 1: Statische Eigenschaft
```typescript
class Mathe {
    static pi: number = 3.14;

    static berechneKreisFlaeche(radius: number): number {
        return Mathe.pi * radius * radius;
    }
}

console.log(Mathe.pi); // Ausgabe: 3.14
console.log(Mathe.berechneKreisFlaeche(5)); // Ausgabe: 78.5
```

### Beispiel 2: Statische Methode
```typescript
class Taschenrechner {
    static addiere(a: number, b: number): number {
        return a + b;
    }
}

console.log(Taschenrechner.addiere(5, 7)); // Ausgabe: 12
```

## Erklärung
Ein häufiger Stolperstein beim Arbeiten mit statischen Mitgliedern ist die Verwechslung zwischen statischen und Instanzmitgliedern. Statische Mitglieder können nicht über eine Instanz der Klasse aufgerufen werden, sondern müssen über den Klassennamen angesprochen werden. Ein weiterer Punkt ist, dass statische Mitglieder nicht auf Instanzvariablen oder -methoden zugreifen können, da sie nicht im Kontext einer Instanz existieren.

Zusätzlich ist es wichtig zu beachten, dass statische Mitglieder nicht vererbt werden, wenn eine Unterklasse von einer Oberklasse abgeleitet wird. Sie bleiben spezifisch für die Klasse, in der sie definiert sind.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "static" in TypeScript ermöglicht die Definition von Eigenschaften und Methoden auf Klassenebene, die unabhängig von Instanzen der Klasse sind.