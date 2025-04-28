<!--
Meta Description: # El Tipo "never" en TypeScript: Comprensión y Uso ## Sinopsis El tipo `never` en TypeScript es un tipo especial que representa valores que nunca ocur...
Meta Keywords: que, tipo, never, typescript, funciones
-->

# El Tipo "never" en TypeScript: Comprensión y Uso

## Sinopsis
El tipo `never` en TypeScript es un tipo especial que representa valores que nunca ocurren. Se utiliza principalmente en situaciones donde se espera que una función nunca regrese, como en lanzamientos de excepciones o bucles infinitos.

## Documentación
El tipo `never` se utiliza para definir el tipo de valores que son inalcanzables. Este tipo es particularmente útil en funciones que no tienen un valor de retorno, es decir, que siempre arrojan un error o que entran en un ciclo infinito.

### Propósito
El propósito principal del tipo `never` es ayudar a los desarrolladores a gestionar y detectar errores en el flujo del programa. Al utilizar `never`, TypeScript puede inferir que ciertas ramas de código no se ejecutarán, lo que a su vez permite una mejor verificación de tipos.

### Uso
El tipo `never` se utiliza en las siguientes situaciones:
- En funciones que siempre lanzan excepciones.
- En funciones que no finalizan su ejecución normalmente (por ejemplo, funciones que entran en un ciclo infinito).
- Como parte de un tipo discriminado, donde se espera que un valor no coincida con ningún otro tipo.

## Ejemplos

### Ejemplo 1: Función que lanza una excepción
```typescript
function throwError(message: string): never {
    throw new Error(message);
}
```

### Ejemplo 2: Función con ciclo infinito
```typescript
function infiniteLoop(): never {
    while (true) {
        console.log("Este ciclo nunca termina");
    }
}
```

### Ejemplo 3: Uso en un tipo discriminado
```typescript
type Resultado = "éxito" | "error";

function manejarResultado(resultado: Resultado): void {
    switch (resultado) {
        case "éxito":
            console.log("Operación exitosa");
            break;
        case "error":
            throwError("Ocurrió un error");
        default:
            const _exhaustiveCheck: never = resultado; // Esto asegurará que no se pase un valor inesperado.
            break;
    }
}
```

## Explicación
Al usar el tipo `never`, es crucial tener en cuenta que:
- **No se puede crear una instancia de `never`:** No es posible asignar un valor a una variable de tipo `never`, ya que no hay valores que correspondan a este tipo.
- **Uso en funciones:** Las funciones que devuelven `never` indican que no tienen un resultado que pueda ser usado, lo que puede ser útil en la gestión de flujos de control.
- **Comprobaciones exhaustivas:** Al utilizar `never` en un tipo discriminado, se garantiza que se manejan todos los casos posibles, lo que ayuda a evitar errores en tiempo de ejecución.

## Resumen en una línea
El tipo `never` en TypeScript representa valores que nunca ocurren y se utiliza para funciones que no retornan, como en lanzamientos de excepciones o bucles infinitos.