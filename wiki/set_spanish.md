<!--
Meta Description: # Uso de "Set" en TypeScript: Guía Completa ## Sinopsis El tipo `Set` en TypeScript es una colección de valores únicos que permite almacenar y manipul...
Meta Keywords: set, que, numeros, typescript, datos
-->

# Uso de "Set" en TypeScript: Guía Completa

## Sinopsis
El tipo `Set` en TypeScript es una colección de valores únicos que permite almacenar y manipular datos sin duplicados, facilitando operaciones de inserción, eliminación y verificación de existencia.

## Documentación
El tipo `Set` está disponible en TypeScript como parte del estándar ECMAScript 2015 (ES6). Su propósito principal es gestionar colecciones de datos en las que cada elemento es único. Esto lo hace especialmente útil para evitar duplicados y realizar operaciones matemáticas como uniones e intersecciones.

### Propósito
- Almacenar valores únicos.
- Permitir operaciones eficientes de búsqueda y eliminación.
- Manejar colecciones de datos de forma más intuitiva.

### Uso
Para crear un `Set`, simplemente se utiliza el constructor `Set()`:

```typescript
let conjunto = new Set<number>();
```

Puedes inicializar un `Set` con un array existente:

```typescript
let conjunto = new Set<number>([1, 2, 3, 4]);
```

### Métodos Comunes
- `add(value)`: Agrega un nuevo elemento al `Set`.
- `delete(value)`: Elimina un elemento del `Set`.
- `has(value)`: Verifica si un elemento existe en el `Set`.
- `clear()`: Elimina todos los elementos del `Set`.
- `size`: Devuelve el número de elementos en el `Set`.

## Ejemplos
### Ejemplo Básico
```typescript
let numeros = new Set<number>();

numeros.add(1);
numeros.add(2);
numeros.add(3);
numeros.add(2); // No se añade, ya que 2 ya existe

console.log(numeros); // Output: Set { 1, 2, 3 }
```

### Verificación de Existencia
```typescript
console.log(numeros.has(2)); // Output: true
console.log(numeros.has(5)); // Output: false
```

### Eliminación de Elementos
```typescript
numeros.delete(2);
console.log(numeros); // Output: Set { 1, 3 }
```

### Uso de `clear()`
```typescript
numeros.clear();
console.log(numeros.size); // Output: 0
```

## Explicación
Al trabajar con `Set`, es importante tener en cuenta que:
- Los elementos son únicos y no se permiten duplicados.
- Los `Set` son iterables, lo que permite usar bucles `for...of` para recorrer sus elementos.
- Los tipos de datos que se pueden almacenar incluyen tipos primitivos y objetos. Sin embargo, los objetos son referenciados por su dirección en memoria, por lo que dos objetos con el mismo contenido son considerados diferentes si no son la misma instancia.

### Errores Comunes
- Intentar agregar un elemento que ya existe, que no generará errores pero no tendrá efecto.
- Confundir el `Set` con un `Array`, ya que los métodos y el comportamiento son diferentes.
- No considerar que `Set` es un tipo iterable, lo que puede llevar a errores en la manipulación de datos.

## Resumen en una Línea
El tipo `Set` en TypeScript permite almacenar colecciones de valores únicos, facilitando la gestión de datos sin duplicados.