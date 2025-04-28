<!--
Meta Description: # Uso del "if" en TypeScript: Estructura de Control Fundamental ## Sinopsis La declaración `if` en TypeScript permite la ejecución condicional de bloq...
Meta Keywords: typescript, código, else, que, verdadera
-->

# Uso del "if" en TypeScript: Estructura de Control Fundamental

## Sinopsis
La declaración `if` en TypeScript permite la ejecución condicional de bloques de código, facilitando la toma de decisiones en la lógica de programación. Es un componente esencial en la programación que ayuda a controlar el flujo del programa basado en evaluaciones booleanas.

## Documentación
La declaración `if` es una de las estructuras de control más utilizadas en TypeScript (y en JavaScript). Su propósito es evaluar una condición y ejecutar un bloque de código si esa condición es verdadera. La sintaxis básica es la siguiente:

```typescript
if (condición) {
    // código a ejecutar si la condición es verdadera
}
```

### Uso
- **Condición**: Una expresión que se evalúa como verdadera o falsa.
- **Bloque de código**: Código que se ejecuta solo si la condición resulta ser verdadera.

### Sintaxis Extendida
Además del uso básico, el `if` puede complementarse con otras estructuras como `else` y `else if` para manejar múltiples condiciones:

```typescript
if (condición1) {
    // código si condición1 es verdadera
} else if (condición2) {
    // código si condición2 es verdadera
} else {
    // código si ninguna de las condiciones anteriores es verdadera
}
```

## Ejemplos
### Ejemplo Básico
```typescript
let numero: number = 10;

if (numero > 5) {
    console.log("El número es mayor que 5");
}
```

### Ejemplo con else
```typescript
let edad: number = 18;

if (edad >= 18) {
    console.log("Eres mayor de edad");
} else {
    console.log("Eres menor de edad");
}
```

### Ejemplo con else if
```typescript
let calificacion: number = 75;

if (calificacion >= 90) {
    console.log("A");
} else if (calificacion >= 80) {
    console.log("B");
} else if (calificacion >= 70) {
    console.log("C");
} else {
    console.log("F");
}
```

## Explicación
Aunque el uso de `if` es bastante directo, existen algunos puntos a tener en cuenta:

- **Tipado Estricto**: TypeScript promueve el uso de tipos. Asegúrate de que las condiciones que evaluas sean del tipo booleano, ya que cualquier otro tipo puede conducir a comportamientos inesperados.
  
- **Cuidado con el Ámbito**: Las variables definidas dentro del bloque `if` no son accesibles fuera de él. Esto puede causar confusiones si se intenta acceder a esas variables más adelante en el código.

- **Evaluación de Verdaderos y Falsos**: En JavaScript, se evalúan varios valores como falsos (0, "", null, undefined, NaN). Asegúrate de entender cómo se comportan estas evaluaciones en TypeScript.

## Resumen en Una Línea
La declaración `if` en TypeScript permite ejecutar bloques de código condicionalmente, basado en la evaluación de expresiones booleanas.