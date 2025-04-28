<!--
Meta Description: # Uso de la declaración "switch" en TypeScript: Guía completa ## Sinopsis La declaración `switch` en TypeScript permite seleccionar entre múltiples bl...
Meta Keywords: switch, break, código, expresión, case
-->

# Uso de la declaración "switch" en TypeScript: Guía completa 

## Sinopsis
La declaración `switch` en TypeScript permite seleccionar entre múltiples bloques de código a ejecutar, basándose en el valor de una expresión. Es una alternativa más legible y estructurada que múltiples declaraciones `if-else`.

## Documentación
La declaración `switch` se utiliza para ejecutar diferentes partes de código basadas en el valor de una expresión. Su sintaxis es clara y permite manejar múltiples casos de forma más eficiente que múltiples condiciones `if`.

### Sintaxis
```typescript
switch (expresión) {
    case valor1:
        // Bloque de código a ejecutar si expresión === valor1
        break;
    case valor2:
        // Bloque de código a ejecutar si expresión === valor2
        break;
    default:
        // Bloque de código a ejecutar si ningún caso coincide
}
```

### Propósito
El propósito de `switch` es simplificar el control de flujo en situaciones donde se necesita evaluar una única expresión contra múltiples valores posibles. Esto mejora la legibilidad y el mantenimiento del código.

### Uso
- La expresión se evalúa una vez y su resultado se compara con los valores en los casos.
- Cada caso puede tener un bloque de código asociado que se ejecutará si hay coincidencia.
- El uso de `break` es crucial para evitar la ejecución de casos subsiguientes, a menos que se desee este comportamiento (conocido como "fall-through").

## Ejemplos

### Ejemplo Básico
```typescript
let dia: number = 3;
let nombreDia: string;

switch (dia) {
    case 1:
        nombreDia = "Lunes";
        break;
    case 2:
        nombreDia = "Martes";
        break;
    case 3:
        nombreDia = "Miércoles";
        break;
    default:
        nombreDia = "Día inválido";
}

console.log(nombreDia); // Salida: Miércoles
```

### Ejemplo de Fall-Through
```typescript
let calificacion: number = 85;
let resultado: string;

switch (true) {
    case (calificacion >= 90):
        resultado = "Excelente";
        break;
    case (calificacion >= 75):
        resultado = "Bueno";
        break;
    case (calificacion >= 60):
        resultado = "Suficiente";
        break;
    default:
        resultado = "Insuficiente";
}

console.log(resultado); // Salida: Bueno
```

## Explicación
Al usar `switch`, es importante tener en cuenta lo siguiente:
- **Fall-through**: Si se omite el `break`, el código seguirá ejecutándose en los siguientes casos, lo que puede no ser el comportamiento deseado.
- **Tipo estricto**: `switch` utiliza comparación estricta (===), por lo que los tipos de datos deben coincidir.
- **Uso de valores booleanos**: Es posible usar `switch` con expresiones booleanas, aunque no es común.

## Resumen en una línea
La declaración `switch` en TypeScript permite evaluar una expresión contra múltiples valores y ejecutar el bloque correspondiente, mejorando la legibilidad del código.