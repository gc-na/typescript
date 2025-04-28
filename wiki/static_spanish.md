<!--
Meta Description: # static en TypeScript: Definición, Uso y Ejemplos ## Sinopsis El modificador `static` en TypeScript permite definir propiedades y métodos en una clas...
Meta Keywords: clase, que, miembros, estáticos, static
-->

# static en TypeScript: Definición, Uso y Ejemplos

## Sinopsis
El modificador `static` en TypeScript permite definir propiedades y métodos en una clase que pertenecen a la clase misma en lugar de a las instancias de la clase. Esto significa que se pueden acceder sin necesidad de crear un objeto de la clase.

## Documentación
El modificador `static` se utiliza para definir miembros estáticos en una clase. Estos miembros pueden ser propiedades o métodos que son compartidos entre todas las instancias de la clase. Esto resulta útil para crear funciones utilitarias o constantes que no dependen del estado de una instancia específica.

### Propósito
El propósito principal de los miembros estáticos es proporcionar un contexto compartido y reutilizable que puede ser accedido directamente a través de la clase.

### Uso
Para declarar un miembro estático, se utiliza la palabra clave `static` antes de la declaración de la propiedad o método dentro de la clase. Los miembros estáticos pueden ser llamados directamente utilizando el nombre de la clase, seguido del operador de acceso a miembros `.`.

### Detalles
- Los miembros estáticos no pueden ser accedidos a través de instancias de la clase.
- Los miembros estáticos son útiles para almacenar información que no está relacionada con instancias específicas.
- La declaración de miembros estáticos puede incluir tanto propiedades como métodos.

## Ejemplos

### Ejemplo 1: Propiedad estática
```typescript
class Contador {
    static totalContadores: number = 0;

    constructor() {
        Contador.totalContadores++;
    }

    static obtenerTotalContadores(): number {
        return Contador.totalContadores;
    }
}

const contador1 = new Contador();
const contador2 = new Contador();
console.log(Contador.obtenerTotalContadores()); // Salida: 2
```

### Ejemplo 2: Método estático
```typescript
class Matematica {
    static suma(a: number, b: number): number {
        return a + b;
    }
}

console.log(Matematica.suma(5, 10)); // Salida: 15
```

## Explicación
Al trabajar con miembros estáticos, es importante recordar que estos no tienen acceso a `this`, ya que `this` se refiere a la instancia de la clase, y los miembros estáticos no están ligados a ninguna instancia. Esto puede causar confusión si se intenta acceder a propiedades de instancia desde un método estático.

Además, es común que los desarrolladores se confundan al intentar crear instancias de clases estáticas, ya que no se puede hacer. Los miembros estáticos están diseñados para ser utilizados sin instanciar la clase.

## Resumen en una línea
El modificador `static` en TypeScript permite definir propiedades y métodos que pertenecen a la clase en sí, en lugar de a sus instancias.