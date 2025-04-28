<!--
Meta Description: # Funciones en TypeScript: Guía Completa ## Sinopsis Las funciones en TypeScript son bloques de código reutilizables que permiten encapsular lógica y ...
Meta Keywords: typescript, funciones, parámetros, función, que
-->

# Funciones en TypeScript: Guía Completa

## Sinopsis
Las funciones en TypeScript son bloques de código reutilizables que permiten encapsular lógica y realizar tareas específicas. Con la tipificación estática de TypeScript, las funciones pueden tener parámetros y valores de retorno con tipos definidos, mejorando la seguridad y la legibilidad del código.

## Documentación
### Propósito
Las funciones son fundamentales en la programación y permiten organizar el código en segmentos manejables. TypeScript amplía las capacidades de JavaScript al introducir un sistema de tipos, lo que ayuda a detectar errores en tiempo de compilación.

### Uso
Para definir una función en TypeScript, se utiliza la palabra clave `function`, seguida del nombre de la función, una lista de parámetros entre paréntesis (con tipos opcionales) y un bloque de código entre llaves. La sintaxis básica es la siguiente:

```typescript
function nombreFuncion(parametro1: tipo1, parametro2: tipo2): tipoDeRetorno {
    // cuerpo de la función
}
```

### Detalles
- **Parámetros:** Se pueden definir múltiples parámetros con sus respectivos tipos.
- **Tipo de retorno:** Se puede especificar el tipo de dato que la función devolverá, si es que retorna algo.
- **Funciones anónimas:** TypeScript permite definir funciones sin nombre, que pueden ser asignadas a variables.
- **Funciones de flecha:** Una sintaxis más concisa introducida en ES6 que TypeScript también soporta.

## Ejemplos

### Ejemplo 1: Función simple
```typescript
function saludar(nombre: string): string {
    return `Hola, ${nombre}!`;
}

console.log(saludar("Juan")); // Salida: Hola, Juan!
```

### Ejemplo 2: Función con parámetros opcionales
```typescript
function sumar(a: number, b: number, c?: number): number {
    return c ? a + b + c : a + b;
}

console.log(sumar(2, 3)); // Salida: 5
console.log(sumar(2, 3, 4)); // Salida: 9
```

### Ejemplo 3: Función de flecha
```typescript
const multiplicar = (x: number, y: number): number => x * y;

console.log(multiplicar(3, 4)); // Salida: 12
```

## Explicación
### Errores comunes
1. **Tipado incorrecto:** Olvidar definir tipos de parámetros o el tipo de retorno puede llevar a errores en el tiempo de ejecución, aunque TypeScript lo detectará en la mayoría de los casos.
2. **Uso de `this`:** En funciones regulares, el contexto de `this` puede ser confuso. Se recomienda usar funciones de flecha para mantener el contexto de `this`.
3. **Parámetros opcionales mal manejados:** No proporcionar valores para parámetros opcionales puede causar comportamientos inesperados si no se manejan adecuadamente dentro de la función.

## Resumen en una línea
Las funciones en TypeScript son bloques de código que permiten realizar tareas específicas con tipado estático, mejorando la seguridad y la mantenibilidad del código.