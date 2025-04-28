<!--
Meta Description: # Espacios de Nombres en TypeScript: Guía Completa ## Sinopsis Los espacios de nombres (namespaces) en TypeScript son una forma de agrupar lógicamente...
Meta Keywords: nombres, los, espacios, typescript, código
-->

# Espacios de Nombres en TypeScript: Guía Completa

## Sinopsis
Los espacios de nombres (namespaces) en TypeScript son una forma de agrupar lógicamente código en un solo bloque, lo que ayuda a evitar conflictos de nombres y a organizar el código de manera más efectiva.

## Documentación
### ¿Qué son los Espacios de Nombres?
Los espacios de nombres en TypeScript permiten encapsular y organizar el código en módulos lógicos. A diferencia de los módulos ES6 que utilizan `import` y `export`, los espacios de nombres son una forma más antigua de agrupar código, pero siguen siendo útiles, especialmente en proyectos más grandes o en aplicaciones que necesitan una estructura clara.

### Propósito
El propósito principal de los espacios de nombres es evitar colisiones de nombres en el ámbito global y mejorar la legibilidad del código. Al encapsular funciones, clases y variables dentro de un espacio de nombres, se puede gestionar el código de manera más efectiva.

### Uso
Para definir un espacio de nombres, se utiliza la palabra clave `namespace`, seguida del nombre del espacio. El contenido se coloca dentro de llaves. Para acceder a los elementos dentro de un espacio de nombres, se utiliza la notación de punto.

```typescript
namespace MiEspacioDeNombres {
    export class MiClase {
        constructor(public nombre: string) {}
        
        mostrarNombre() {
            console.log(`Nombre: ${this.nombre}`);
        }
    }
}
```

En este ejemplo, hemos creado un espacio de nombres llamado `MiEspacioDeNombres` que contiene una clase `MiClase`. La palabra clave `export` permite que la clase sea accesible fuera del espacio de nombres.

## Ejemplos
### Ejemplo Básico
```typescript
namespace Geometria {
    export class Circulo {
        constructor(public radio: number) {}

        area() {
            return Math.PI * this.radio * this.radio;
        }
    }
}

const miCirculo = new Geometria.Circulo(5);
console.log(miCirculo.area()); // Salida: 78.53981633974483
```

### Ejemplo con Funciones
```typescript
namespace Utilidades {
    export function sumar(a: number, b: number): number {
        return a + b;
    }
}

console.log(Utilidades.sumar(5, 10)); // Salida: 15
```

## Explicación
### Errores Comunes
- **Acceso a elementos no exportados**: Si no se utiliza la palabra clave `export`, los elementos dentro del espacio de nombres no serán accesibles desde fuera de él.
- **Confusión con módulos**: Es importante no confundir los espacios de nombres con módulos de ES6. Aunque ambos sirven para organizar el código, los espacios de nombres son más adecuados para aplicaciones más antiguas que no utilizan módulos.

### Notas Adicionales
- Los espacios de nombres son más comunes en proyectos TypeScript antiguos. En proyectos nuevos, es recomendable utilizar módulos de ES6 para mantener la compatibilidad y aprovechar las funcionalidades más modernas del lenguaje.
- Asegúrate de que los nombres de los espacios de nombres sean únicos para evitar conflictos con otros espacios de nombres o módulos.

## Resumen en Una Línea
Los espacios de nombres en TypeScript permiten organizar y encapsular el código de manera efectiva, evitando conflictos de nombres y mejorando la estructura del proyecto.