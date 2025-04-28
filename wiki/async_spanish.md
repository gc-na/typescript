<!--
Meta Description: # Uso de `async` en TypeScript: Promesas y Funciones Asíncronas ## Sinopsis El uso de `async` en TypeScript permite la creación de funciones asíncrona...
Meta Keywords: async, que, funciones, una, await
-->

# Uso de `async` en TypeScript: Promesas y Funciones Asíncronas

## Sinopsis
El uso de `async` en TypeScript permite la creación de funciones asíncronas que facilitan el manejo de operaciones que pueden tardar en completarse, como llamadas a APIs o lecturas de archivos. Esto mejora la legibilidad y el mantenimiento del código en comparación con el uso tradicional de promesas.

## Documentación
### Propósito
El modificador `async` se utiliza para declarar funciones que realizarán operaciones asíncronas, permitiendo que estas funciones devuelvan una promesa de manera implícita. Esto significa que, al llamar a una función marcada como `async`, se puede utilizar `await` dentro de ella para esperar a que se resuelvan promesas.

### Uso
Para definir una función asíncrona, simplemente se antepone la palabra clave `async` a la declaración de la función. Las funciones asíncronas pueden incluir la palabra clave `await`, la cual hace que la ejecución de la función se pause hasta que la promesa se resuelva o se rechace.

### Detalles
- **Declaración**: `async function myFunction() { ... }`
- **Uso de `await`**: Dentro de una función `async`, puedes usar `await` para trabajar con promesas de manera más sencilla.
- **Retorno**: Una función `async` siempre devolverá una promesa, incluso si se retorna un valor que no es una promesa.
- **Manejo de Errores**: Se recomienda usar `try...catch` para el manejo de errores en funciones `async` cuando se usa `await`.

## Ejemplos
### Ejemplo Básico 1: Función Asíncrona
```typescript
async function obtenerDatos(url: string): Promise<any> {
    const respuesta = await fetch(url);
    return respuesta.json();
}
```

### Ejemplo Básico 2: Manejo de Errores
```typescript
async function obtenerDatosSeguros(url: string): Promise<any> {
    try {
        const respuesta = await fetch(url);
        if (!respuesta.ok) {
            throw new Error('Error en la respuesta de la red');
        }
        return await respuesta.json();
    } catch (error) {
        console.error('Error:', error);
    }
}
```

## Explicación
Al utilizar `async`, es importante tener en cuenta algunos aspectos:

- **Uso de `await` fuera de funciones `async`**: Intentar utilizar `await` fuera de una función `async` resultará en un error de sintaxis.
- **Promesas no manejadas**: Si no se manejan adecuadamente las promesas dentro de funciones `async`, podrían ocurrir errores no detectados.
- **Variables no bloqueantes**: Las funciones `async` no bloquean el hilo de ejecución, lo que significa que el código que sigue puede ejecutarse mientras se espera la resolución de una promesa.

## Resumen en una línea
El modificador `async` en TypeScript permite crear funciones asíncronas que manejan promesas de forma más legible y eficiente.