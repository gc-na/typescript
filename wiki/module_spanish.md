<!--
Meta Description: # Módulos en TypeScript: Guía Completa y Ejemplos ## Sinopsis Los módulos en TypeScript son bloques de código que permiten organizar y encapsular func...
Meta Keywords: módulos, typescript, que, código, archivo
-->

# Módulos en TypeScript: Guía Completa y Ejemplos

## Sinopsis
Los módulos en TypeScript son bloques de código que permiten organizar y encapsular funcionalidades, facilitando la reutilización y el mantenimiento del código en aplicaciones grandes.

## Documentación
### ¿Qué son los Módulos en TypeScript?
Un módulo en TypeScript es un archivo que contiene código que se puede exportar e importar en otros archivos. Los módulos ayudan a dividir el código en diferentes archivos, lo que mejora la organización y la claridad del código. Cada archivo de TypeScript es un módulo por defecto, y se puede utilizar la palabra clave `export` para exponer funciones, clases o variables a otros módulos.

### Propósito de los Módulos
El uso de módulos tiene varios propósitos:
- **Encapsulación**: Permite crear un espacio de nombres que evita conflictos entre variables y funciones.
- **Reutilización**: Facilita la reutilización de código en diferentes partes de la aplicación.
- **Organización**: Ayuda a mantener el código estructurado y fácil de navegar.

### Uso de Módulos
Para usar módulos en TypeScript, se utiliza la sintaxis de `import` y `export`. A continuación se presentan ejemplos de cómo declarar y utilizar módulos.

## Ejemplos

### Ejemplo 1: Exportación de una Función
```typescript
// archivo: saludo.ts
export function saludar(nombre: string): string {
    return `Hola, ${nombre}!`;
}
```

### Ejemplo 2: Importación de una Función
```typescript
// archivo: main.ts
import { saludar } from './saludo';

const mensaje = saludar('Juan');
console.log(mensaje); // Salida: Hola, Juan!
```

### Ejemplo 3: Exportación por Defecto
```typescript
// archivo: calculadora.ts
export default function sumar(a: number, b: number): number {
    return a + b;
}
```

### Ejemplo 4: Importación de un Módulo por Defecto
```typescript
// archivo: main.ts
import sumar from './calculadora';

const resultado = sumar(5, 10);
console.log(resultado); // Salida: 15
```

## Explicación
### Errores Comunes
- **Olvidar usar `export`**: Si no se exporta una función o variable, no podrá ser importada en otros módulos.
- **Rutas Incorrectas**: Asegúrate de que las rutas de importación sean correctas; un error en la ruta resultará en un mensaje de error sobre el módulo no encontrado.
- **Módulos Cíclicos**: Ten cuidado con las dependencias cíclicas entre módulos, ya que pueden causar errores de inicialización.

### Notas Adicionales
- TypeScript utiliza el sistema de módulos de ECMAScript, lo que significa que puedes utilizar la misma sintaxis en JavaScript moderno.
- Es recomendable utilizar un gestor de paquetes como npm para manejar las dependencias de tus módulos.

## Resumen en Una Línea
Los módulos en TypeScript permiten organizar el código en bloques reutilizables y encapsulados, mejorando la estructura y mantenibilidad de las aplicaciones.