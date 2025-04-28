<!--
Meta Description: # Símbolo (Symbol) no TypeScript: Entenda o Tipo Primitivo Único ## Sinopse O `Symbol` é um tipo primitivo em TypeScript que representa um identificad...
Meta Keywords: symbol, que, propriedades, typescript, symbols
-->

# Símbolo (Symbol) no TypeScript: Entenda o Tipo Primitivo Único

## Sinopse
O `Symbol` é um tipo primitivo em TypeScript que representa um identificador único e imutável, ideal para criar chaves de propriedades que não colidam com outras.

## Documentação
O `Symbol` foi introduzido no ECMAScript 2015 (ES6) e é utilizado em TypeScript para criar identificadores únicos que podem ser usados como chaves de propriedades em objetos. Ao contrário de strings, dois `Symbols` com a mesma descrição são sempre diferentes, proporcionando uma maneira de evitar conflitos entre propriedades.

### Propósito
Os `Symbols` são úteis em situações onde você deseja garantir que uma propriedade de um objeto não seja acidentalmente sobrescrita ou acessada. Eles são frequentemente utilizados em bibliotecas e APIs para definir propriedades que não devem ser expostas ou acessadas diretamente.

### Uso
Para criar um novo `Symbol`, você pode usar a função global `Symbol()`, que pode receber uma descrição opcional:

```typescript
const meuSimbolo = Symbol('minhaDescrição');
```

### Detalhes
- Os `Symbols` não são enumeráveis nas iterações padrão, como `for...in` ou `Object.keys()`.
- Cada `Symbol` é único, mesmo que tenham a mesma descrição.
- Você pode adicionar `Symbols` como propriedades de objetos, garantindo que não haja conflito com strings.

## Exemplos
### Criação de um Symbol
```typescript
const id = Symbol('id');
```

### Usando Symbols como chaves de propriedades
```typescript
const objeto = {
    [id]: 123,
    nome: 'Exemplo'
};

console.log(objeto[id]); // 123
console.log(objeto.nome); // Exemplo
```

### Verificando a unicidade dos Symbols
```typescript
const simbolo1 = Symbol('teste');
const simbolo2 = Symbol('teste');

console.log(simbolo1 === simbolo2); // false
```

## Explicação
Um dos principais erros ao usar `Symbols` é tentar acessá-los como se fossem propriedades normais de um objeto. Lembre-se de que, por padrão, `Symbols` não aparecem em listas de propriedades. Outra armadilha comum é esquecer que, mesmo com a mesma descrição, cada `Symbol` é único. Portanto, evitar a sobreposição de chaves pode ser um pouco mais complicado do que parece.

## Resumo em Uma Linha
O `Symbol` em TypeScript é um tipo primitivo que fornece identificadores únicos e imutáveis, ideal para propriedades de objeto sem conflitos.