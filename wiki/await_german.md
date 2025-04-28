<!--
Meta Description: # Der `await`-Befehl in TypeScript: Asynchrone Programmierung leicht gemacht ## Synopsis Der `await`-Befehl in TypeScript ermöglicht es Entwicklern, a...
Meta Keywords: await, die, von, async, wird
-->

# Der `await`-Befehl in TypeScript: Asynchrone Programmierung leicht gemacht

## Synopsis
Der `await`-Befehl in TypeScript ermöglicht es Entwicklern, asynchrone Funktionen einfach zu handhaben, indem er die Ausführung von Code an einer bestimmten Stelle pausiert, bis ein Promise aufgelöst wird. Dies führt zu einem klareren und übersichtlicheren Code im Vergleich zu traditionellen Callback-Methoden.

## Dokumentation
### Zweck
In TypeScript ist `await` ein Schlüsselwort, das nur innerhalb von Funktionen verwendet werden kann, die mit dem `async`-Schlüsselwort deklariert sind. Es wird verwendet, um auf das Ergebnis eines Promises zu warten, ohne dass der Code blockiert wird. Dies erleichtert die Arbeit mit asynchronen Operationen, wie z.B. dem Abrufen von Daten von einem Server.

### Verwendung
Um `await` zu verwenden, muss die umgebende Funktion als `async` markiert werden. Hier ist die allgemeine Syntax:

```typescript
async function myAsyncFunction() {
    const result = await somePromise();
    console.log(result);
}
```

In diesem Beispiel wird die Ausführung von `myAsyncFunction` angehalten, bis `somePromise` aufgelöst oder abgelehnt wird.

### Details
- **Fehlerbehandlung**: Da `await` ein Promise zurückgibt, können Fehler, die während der Ausführung auftreten, mit `try...catch` behandelt werden.
- **Mehrere `await`-Befehle**: Mehrere `await`-Befehle können in einer Funktion verwendet werden, um auf mehrere asynchrone Operationen zu warten. Es ist jedoch wichtig, die Leistung zu berücksichtigen, da `await` die Ausführung sequenziell anhalten kann.
- **Parallelität**: Um mehrere Promises parallel zu verarbeiten, sollte `Promise.all` verwendet werden.

## Beispiele
### Einfaches Beispiel
```typescript
async function fetchData() {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
}
fetchData();
```

### Fehlerbehandlung
```typescript
async function fetchDataWithErrorHandling() {
    try {
        const response = await fetch('https://api.example.com/data');
        if (!response.ok) {
            throw new Error('Netzwerkfehler');
        }
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Fehler beim Abrufen der Daten:', error);
    }
}
fetchDataWithErrorHandling();
```

### Mehrere `await`-Befehle
```typescript
async function fetchMultipleData() {
    const response1 = await fetch('https://api.example.com/data1');
    const data1 = await response1.json();
    
    const response2 = await fetch('https://api.example.com/data2');
    const data2 = await response2.json();
    
    console.log(data1, data2);
}
fetchMultipleData();
```

## Erklärung
### Häufige Fallstricke
1. **Vergessen, die Funktion als `async` zu kennzeichnen**: Ohne `async` kann `await` nicht verwendet werden.
2. **Nicht behandelte Promise-Abweisungen**: Wenn ein Promise abgelehnt wird und nicht in einem `try...catch`-Block behandelt wird, führt dies zu unvorhergesehenen Fehlern.
3. **Verwendung von `await` außerhalb von `async`-Funktionen**: `await` funktioniert nur innerhalb von `async`-Funktionen und führt zu einem Syntaxfehler, wenn es außerhalb verwendet wird.

### Zusätzliche Hinweise
- Die Verwendung von `await` kann die Lesbarkeit des Codes erheblich verbessern, insbesondere im Vergleich zu verschachtelten Callback-Funktionen.
- Bei der Verwendung von `await` in Schleifen sollte darauf geachtet werden, dass die Iterationen sequenziell ablaufen, was die Leistung beeinträchtigen kann.

## Zusammenfassung in einem Satz
Der `await`-Befehl in TypeScript vereinfacht die Handhabung von asynchronen Operationen, indem er die Ausführung von Code anhalten kann, bis ein Promise aufgelöst wird.