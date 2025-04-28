<!--
Meta Description: # TypeScript: Der Zugriffsschutz "public" – Eine umfassende Anleitung ## Synopsis Der Zugriffsschutz "public" in TypeScript ermöglicht es, Klassenmitg...
Meta Keywords: public, der, ist, und, typescript
-->

# TypeScript: Der Zugriffsschutz "public" – Eine umfassende Anleitung

## Synopsis
Der Zugriffsschutz "public" in TypeScript ermöglicht es, Klassenmitglieder für den Zugriff von außen frei zugänglich zu machen. Dies ist eine grundlegende Funktionalität der objektorientierten Programmierung, die Entwicklern hilft, die Sichtbarkeit und den Zugriff auf Klassenattribute und -methoden zu steuern.

## Dokumentation
In TypeScript ist der Zugriffsmodifizierer `public` der Standardmodifizierer für Klassenmitglieder. Er wird verwendet, um anzugeben, dass eine Eigenschaft oder Methode einer Klasse von überall aus zugänglich ist. Dies bedeutet, dass sowohl Instanzen der Klasse als auch externe Komponenten der Anwendung auf die `public`-Mitglieder zugreifen können.

### Zweck
Der Hauptzweck von `public` ist es, eine klare und flexible API für Klassen zu definieren. Entwickler können entscheiden, welche Teile ihrer Klassen für andere Teile der Anwendung sichtbar und zugänglich sein sollen.

### Verwendung
Um ein Klassenmitglied als `public` zu deklarieren, wird der Modifizierer vor der Deklaration des Mitglieds platziert:

```typescript
class Auto {
    public marke: string;

    constructor(marke: string) {
        this.marke = marke;
    }

    public zeigeMarke(): string {
        return this.marke;
    }
}
```

In diesem Beispiel ist sowohl die Eigenschaft `marke` als auch die Methode `zeigeMarke()` als `public` deklariert.

### Details
- **Standardverhalten**: Wenn kein Zugriffsmodifizierer angegeben wird, sind alle Mitglieder einer Klasse in TypeScript standardmäßig `public`.
- **Kombination mit anderen Modifizierern**: `public` kann zusammen mit anderen Modifizierern wie `protected` und `private` verwendet werden, um die Sichtbarkeit entsprechend den Anforderungen der Anwendung zu steuern.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `public` in TypeScript:

```typescript
class Person {
    public name: string;

    constructor(name: string) {
        this.name = name;
    }

    public begruessen(): string {
        return `Hallo, mein Name ist ${this.name}.`;
    }
}

const person = new Person("Max");
console.log(person.begruessen()); // Ausgabe: Hallo, mein Name ist Max.
```

In diesem Beispiel wird die `name`-Eigenschaft und die `begruessen()`-Methode als `public` definiert, was bedeutet, dass sie von außen zugänglich sind.

## Erklärung
Einige häufige Herausforderungen und Missverständnisse im Zusammenhang mit `public` sind:

- **Übermäßige Sichtbarkeit**: Wenn alle Mitglieder `public` sind, kann dies zu einer ungewollten Abhängigkeit zwischen Klassen führen. Daher sollte `public` nur dann verwendet werden, wenn es notwendig ist.
- **Verwendung von `public` in Interfaces**: In Interfaces sind alle Mitglieder standardmäßig `public`, sodass der Modifizierer in diesem Kontext nicht angegeben werden muss.
- **Missverständnisse bei der Sichtbarkeit**: Es ist wichtig zu wissen, dass `public` nicht bedeutet, dass Mitglieder von überall ohne Einschränkungen verändert werden können. Es bedeutet lediglich, dass sie zugänglich sind.

## Ein-Satz-Zusammenfassung
Der Zugriffsmodifizierer `public` in TypeScript ermöglicht den uneingeschränkten Zugriff auf Klassenmitglieder von außen und ist der Standardmodifizierer für Eigenschaften und Methoden.