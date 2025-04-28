<!--
Meta Description: # El Tipo de Dato "number" en TypeScript: Uso y Ejemplos ## Sinopsis En TypeScript, el tipo de dato `number` se utiliza para representar tanto números...
Meta Keywords: number, typescript, tipo, que, let
-->

# El Tipo de Dato "number" en TypeScript: Uso y Ejemplos

## Sinopsis
En TypeScript, el tipo de dato `number` se utiliza para representar tanto números enteros como números de punto flotante, permitiendo a los desarrolladores trabajar con una amplia gama de valores numéricos en sus aplicaciones.

## Documentación
El tipo `number` en TypeScript es una de las primitivos más fundamentales y se basa en el estándar IEEE 754 de doble precisión. Esto significa que puede representar valores numéricos de alta precisión, lo que es esencial para cálculos matemáticos, estadísticas y cualquier otra lógica que requiera manipulación numérica.

### Propósito
El propósito del tipo `number` es proporcionar una forma consistente y efectiva de manejar valores numéricos en TypeScript, manteniendo la tipificación estática que caracteriza al lenguaje. Esto ayuda a prevenir errores en tiempo de compilación y mejora la legibilidad del código.

### Uso
Para declarar una variable de tipo `number`, se utiliza la siguiente sintaxis:

```typescript
let variableNombre: number = valor;
```

Donde `variableNombre` es el nombre de la variable y `valor` es el número asignado a esta. TypeScript permite realizar diversas operaciones matemáticas con este tipo de dato, como suma, resta, multiplicación y división.

## Ejemplos
### Ejemplo Básico de Declaración
```typescript
let edad: number = 30;
let precio: number = 99.99;
```

### Ejemplo de Operaciones Matemáticas
```typescript
let a: number = 5;
let b: number = 10;

let suma: number = a + b; // 15
let resta: number = b - a; // 5
let multiplicacion: number = a * b; // 50
let division: number = b / a; // 2
```

### Ejemplo de Uso con Funciones
```typescript
function calcularArea(base: number, altura: number): number {
    return (base * altura) / 2;
}

let area: number = calcularArea(10, 5); // 25
```

## Explicación
Un punto importante a tener en cuenta al trabajar con el tipo `number` en TypeScript es que, debido a su representación en memoria, puede haber problemas de precisión, especialmente al realizar operaciones con números de punto flotante. Por ejemplo, sumar 0.1 y 0.2 puede no dar exactamente 0.3 debido a la forma en que estos números son representados en binario.

Además, es importante recordar que el tipo `number` en TypeScript no distingue entre enteros y flotantes. Por lo tanto, cualquier valor que se asigne a una variable de tipo `number` es tratado de la misma manera, lo que puede ser confuso para quienes vienen de lenguajes que tienen tipos numéricos más específicos.

## Resumen en Una Línea
El tipo de dato `number` en TypeScript permite representar y manipular valores numéricos, tanto enteros como de punto flotante, en aplicaciones de manera eficiente y tipada.