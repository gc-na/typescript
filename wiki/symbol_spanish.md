<!--
Meta Description: # Símbolo en TypeScript: Todo lo que Necesitas Saber ## Sinopsis El tipo `symbol` en TypeScript es un primitivo que permite la creación de identificad...
Meta Keywords: que, symbol, propiedades, typescript, símbolo
-->

# Símbolo en TypeScript: Todo lo que Necesitas Saber

## Sinopsis
El tipo `symbol` en TypeScript es un primitivo que permite la creación de identificadores únicos y inmutables, ideales para propiedades de objetos que no deben colisionar con otras.

## Documentación
El tipo `symbol` fue introducido en ECMAScript 2015 (ES6) y es ampliamente utilizado en TypeScript para definir propiedades únicas en objetos. Los símbolos son especialmente útiles en la programación orientada a objetos y la creación de bibliotecas, ya que permiten la encapsulación y evitan conflictos en los nombres de propiedades.

### Propósito
El propósito principal de `symbol` es crear identificadores únicos que no se pueden accidentalmente sobrescribir o acceder desde otros contextos.

### Uso
Los símbolos se crean utilizando la función `Symbol()`, que devuelve un nuevo símbolo único. Se pueden usar directamente como propiedades de objetos o como claves en mapas.

```typescript
const mySymbol = Symbol('description');
```

### Detalles
- **Inmutabilidad:** Una vez creado, un símbolo no puede ser cambiado.
- **Unicidad:** Cada llamada a `Symbol()` genera un símbolo único, incluso si se proporciona la misma descripción.
- **No se convierten a cadenas automáticamente:** A diferencia de otros tipos de datos, los símbolos no se convierten a cadenas cuando se utilizan como claves de propiedades.

## Ejemplos

### Ejemplo Básico de Uso
```typescript
const id = Symbol('id');
const user = {
    [id]: 123,
    name: 'Juan'
};

console.log(user[id]); // 123
```

### Ejemplo con Propiedades Únicas
```typescript
const uniqueKey = Symbol('uniqueKey');

const obj = {
    [uniqueKey]: 'Valor único'
};

console.log(obj[uniqueKey]); // 'Valor único'
console.log(obj['uniqueKey']); // undefined
```

## Explicación
Algunas confusiones comunes incluyen la creencia de que los símbolos son similares a las cadenas. Aunque pueden tener descripciones, estas son meramente informativas y no afectan la unicidad del símbolo. Además, hay que tener cuidado al utilizar símbolos como claves de propiedades, ya que no se pueden acceder mediante notación de punto o cadenas.

Un error común es intentar utilizar símbolos en comparación directa, lo que siempre resultará en `false`, ya que cada símbolo es único, incluso si son creados con la misma descripción.

## Resumen en Una Línea
El tipo `symbol` en TypeScript permite crear identificadores únicos e inmutables para propiedades de objetos, evitando colisiones en los nombres.