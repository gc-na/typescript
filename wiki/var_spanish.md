<!--
Meta Description: # Uso de "var" en TypeScript: Declaración de Variables ## Sinopsis La palabra clave "var" en TypeScript es utilizada para declarar variables. A pesar ...
Meta Keywords: var, que, ámbito, typescript, variables
-->

# Uso de "var" en TypeScript: Declaración de Variables

## Sinopsis
La palabra clave "var" en TypeScript es utilizada para declarar variables. A pesar de que su uso ha disminuido con la introducción de "let" y "const", "var" sigue siendo relevante en ciertas situaciones, especialmente en el contexto de la compatibilidad con JavaScript.

## Documentación
La declaración de variables con "var" permite que una variable sea accesible en todo el ámbito de la función donde se declara. A diferencia de "let" y "const", que tienen un ámbito de bloque, "var" tiene un ámbito de función.

### Propósito
El propósito principal de "var" es crear variables que se pueden utilizar en diferentes partes del código, permitiendo una mayor flexibilidad en la programación. Sin embargo, su uso debe ser considerado con precaución debido a su ámbito de función que puede llevar a comportamientos inesperados.

### Uso
Para declarar una variable usando "var", se utiliza la siguiente sintaxis:

```typescript
var nombreVariable: tipo = valor;
```

Donde `nombreVariable` es el identificador de la variable, `tipo` es el tipo de datos (opcional en algunos casos) y `valor` es el valor inicial que se le asigna.

## Ejemplos

### Ejemplo 1: Declaración simple
```typescript
var mensaje: string = "Hola, TypeScript";
console.log(mensaje); // Salida: Hola, TypeScript
```

### Ejemplo 2: Ámbito de función
```typescript
function ejemploVar() {
    var numero: number = 10;
    if (true) {
        var numeroDentroDelBloque: number = 20;
        console.log(numeroDentroDelBloque); // Salida: 20
    }
    console.log(numeroDentroDelBloque); // Salida: 20, accesible aquí también
}
ejemploVar();
```

### Ejemplo 3: Redeclaración
```typescript
var x: number = 10;
var x: number = 20; // Redeclaración permitida
console.log(x); // Salida: 20
```

## Explicación
Aunque "var" es totalmente funcional, existen algunas trampas y peculiaridades:

1. **Ámbito de función**: Las variables declaradas con "var" son accesibles dentro de toda la función, lo que puede causar confusión si se espera un comportamiento de ámbito de bloque.
   
2. **Redeclaración**: A diferencia de "let" y "const", que generan un error si intentas redeclarar una variable en el mismo ámbito, "var" permite la redeclaración sin problemas.

3. **Hoisting**: Las variables declaradas con "var" son elevadas (hoisted) al inicio de su contexto de ejecución. Esto significa que puedes referenciar una variable antes de su declaración, aunque su valor será `undefined` hasta que se alcance la línea de declaración.

## Resumen en una línea
La palabra clave "var" en TypeScript permite la declaración de variables con ámbito de función, aunque su uso debe ser limitado por el potencial de confusión en el ámbito y la redeclaración.