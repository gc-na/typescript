<!--
Meta Description: # Uso del Bucle "for" en TypeScript: Guía Completa ## Sinopsis El bucle "for" en TypeScript es una estructura de control que permite iterar sobre una ...
Meta Keywords: bucle, typescript, número, que, sobre
-->

# Uso del Bucle "for" en TypeScript: Guía Completa

## Sinopsis
El bucle "for" en TypeScript es una estructura de control que permite iterar sobre una secuencia de elementos, como arreglos o colecciones, facilitando la ejecución repetitiva de un bloque de código.

## Documentación
El bucle "for" es uno de los elementos fundamentales en la programación, y TypeScript, al ser un superconjunto de JavaScript, hereda esta funcionalidad. Su propósito principal es permitir a los desarrolladores ejecutar un bloque de código un número específico de veces, o iterar sobre los elementos de una colección.

### Sintaxis
La sintaxis básica del bucle "for" es la siguiente:

```typescript
for (inicialización; condición; incremento) {
    // Código a ejecutar en cada iteración
}
```

- **inicialización**: Se ejecuta una vez antes de que comience el bucle, sirviendo para declarar e inicializar variables.
- **condición**: Se evalúa antes de cada iteración. Si es verdadera, se ejecuta el bloque de código; si es falsa, el bucle se detiene.
- **incremento**: Se ejecuta al final de cada iteración, generalmente utilizado para actualizar la variable de control.

### Propósito
El bucle "for" es ideal para realizar iteraciones sobre arreglos, colecciones y para ejecutar un código un número determinado de veces.

## Ejemplos

### Ejemplo 1: Iteración simple
```typescript
for (let i = 0; i < 5; i++) {
    console.log(`Número: ${i}`);
}
```
*Salida:*
```
Número: 0
Número: 1
Número: 2
Número: 3
Número: 4
```

### Ejemplo 2: Iterando sobre un arreglo
```typescript
const frutas: string[] = ['manzana', 'banana', 'naranja'];

for (let i = 0; i < frutas.length; i++) {
    console.log(frutas[i]);
}
```
*Salida:*
```
manzana
banana
naranja
```

## Explicación
Al usar el bucle "for", es crucial asegurarse de que la condición de terminación se alcance; de lo contrario, se puede generar un bucle infinito. También, se debe tener cuidado al modificar la variable de control dentro del bucle, ya que puede provocar comportamientos inesperados.

### Errores Comunes
- **Bucle infinito**: Asegurarse de que la condición eventualmente se vuelva falsa.
- **Acceso fuera de límites**: Al iterar sobre un arreglo, verificar que el índice no exceda la longitud del arreglo.
- **Uso inadecuado de tipos**: En TypeScript, es importante que los tipos de las variables sean correctos para evitar errores de compilación.

## Resumen en una línea
El bucle "for" en TypeScript permite iterar sobre colecciones y ejecutar un bloque de código repetidamente, facilitando tareas de programación comunes.