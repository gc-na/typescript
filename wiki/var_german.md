<!--
Meta Description: # Verwendung von "var" in TypeScript: Grundlagen und Anwendungsfälle ## Synopsis In TypeScript ist "var" ein Schlüsselwort zur Deklaration von Variabl...
Meta Keywords: var, ist, variablen, von, typescript
-->

# Verwendung von "var" in TypeScript: Grundlagen und Anwendungsfälle

## Synopsis
In TypeScript ist "var" ein Schlüsselwort zur Deklaration von Variablen. Es wird verwendet, um Variablen zu erstellen, die in einem bestimmten Gültigkeitsbereich (Scope) existieren. Trotz der Einführung von "let" und "const" bleibt "var" relevant und wird in bestimmten Szenarien eingesetzt.

## Dokumentation
### Zweck
Das Schlüsselwort "var" dient dazu, Variablen in TypeScript zu deklarieren. Es ist Teil der JavaScript-Syntax, da TypeScript eine Obermenge von JavaScript ist. Mit "var" deklarierte Variablen sind funktional oder global, je nachdem, wo sie definiert wurden.

### Verwendung
- **Deklaration von Variablen**: "var" wird verwendet, um eine Variable zu deklarieren. 
- **Gültigkeitsbereich**: Variablen, die mit "var" deklariert werden, sind im gesamten Funktionskörper sichtbar, in dem sie deklariert wurden. Wenn sie außerhalb einer Funktion deklariert werden, sind sie global.
- **Hoisting**: Variablen, die mit "var" deklariert sind, werden "gehoisted", was bedeutet, dass sie an den Anfang ihrer Funktion oder des globalen Bereichs verschoben werden.

### Details
- **Syntax**: 
  ```typescript
  var variableName: type = value;
  ```
- **Gültigkeitsbereich**: Der Gültigkeitsbereich von "var" ist oft ein häufiges Missverständnis. Es ist wichtig zu beachten, dass "var" nicht block-scoped ist, was bedeutet, dass eine mit "var" deklarierte Variable innerhalb einer Funktion oder eines globalen Bereichs sichtbar ist, selbst wenn sie innerhalb eines Blocks (z. B. einer if-Anweisung) deklariert wird.

## Beispiele
### Grundlegende Verwendung
```typescript
function example() {
    var x = 10;
    if (true) {
        var x = 20; // dieselbe Variable
        console.log(x); // 20
    }
    console.log(x); // auch 20
}
example();
```

### Globale Variable
```typescript
var globalVar = "Ich bin global";

function test() {
    console.log(globalVar); // Gibt "Ich bin global" aus
}
test();
```

## Erklärung
Einer der häufigsten Stolpersteine bei der Verwendung von "var" ist das Verständnis des Gültigkeitsbereichs. Da "var" nicht block-scoped ist, kann es zu unerwartetem Verhalten führen, insbesondere in Schleifen oder bedingten Anweisungen. Entwickler sollten sich der Hoisting-Effekte bewusst sein, da dies dazu führen kann, dass Variablen vor ihrer tatsächlichen Deklaration verwendet werden.

Es wird empfohlen, "let" oder "const" zu verwenden, um Variablen zu deklarieren, da diese block-scoped sind und somit das Risiko von Fehlern, die durch unerwartete Gültigkeitsbereiche entstehen, verringern.

## Ein-Satz-Zusammenfassung
"var" ist ein Schlüsselwort in TypeScript zur Deklaration von Variablen mit funktionalem oder globalem Gültigkeitsbereich, das jedoch in modernen Anwendungen oft durch "let" und "const" ersetzt wird.