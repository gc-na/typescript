<!--
Meta Description: # Conjunto (Set) em TypeScript: Entenda Como Utilizar ## Sinopse O tipo `Set` em TypeScript permite criar coleções de valores únicos, proporcionando u...
Meta Keywords: set, numeros, typescript, console, log
-->

# Conjunto (Set) em TypeScript: Entenda Como Utilizar

## Sinopse
O tipo `Set` em TypeScript permite criar coleções de valores únicos, proporcionando uma maneira eficiente de armazenar e manipular dados sem duplicatas.

## Documentação
O `Set` é uma estrutura de dados que armazena valores únicos de qualquer tipo, seja primitivo ou referência. Ao contrário de arrays, onde elementos duplicados são permitidos, um `Set` garante que cada valor seja único. Isso é especialmente útil quando você precisa manter uma lista de itens sem repetições.

### Propósito
O principal propósito do `Set` é gerenciar coleções de dados onde a duplicidade não é desejada. Ele oferece operações como adição, remoção e verificação de presença de elementos de maneira eficiente.

### Uso
Para utilizar um `Set` em TypeScript, você pode criá-lo da seguinte maneira:

```typescript
const meuConjunto = new Set<number>();
```

Os métodos mais comuns disponíveis em `Set` incluem:
- `add(value)`: Adiciona um novo elemento ao conjunto.
- `delete(value)`: Remove um elemento do conjunto.
- `has(value)`: Verifica se um elemento existe no conjunto.
- `clear()`: Remove todos os elementos do conjunto.
- `size`: Propriedade que retorna a quantidade de elementos no conjunto.

## Exemplos
### Criando e Usando um Set
```typescript
const numeros = new Set<number>();

numeros.add(1);
numeros.add(2);
numeros.add(2); // Não será adicionado, pois já existe

console.log(numeros.size); // Saída: 2
console.log(numeros.has(1)); // Saída: true
console.log(numeros.has(3)); // Saída: false

numeros.delete(1);
console.log(numeros.size); // Saída: 1

numeros.clear();
console.log(numeros.size); // Saída: 0
```

### Usando um Set com Strings
```typescript
const frutas = new Set<string>(["maçã", "banana", "laranja", "maçã"]);

console.log(frutas.size); // Saída: 3
console.log(frutas.has("banana")); // Saída: true
```

## Explicação
Embora o `Set` seja uma estrutura poderosa, existem algumas armadilhas comuns a serem observadas:
1. **Tipagem**: Ao criar um `Set`, é essencial definir o tipo de valor que ele armazenará. Se não for especificado, o TypeScript pode inferir o tipo como `any`.
2. **Objetos e Referências**: O `Set` compara referências de objetos. Se dois objetos com o mesmo conteúdo forem adicionados, eles serão considerados diferentes se não forem a mesma instância.
3. **Iteração**: Você pode iterar sobre os elementos de um `Set` usando o loop `for...of`. No entanto, a ordem de inserção é mantida, o que pode não ser intuitivo em alguns casos.

## Resumo em Uma Linha
O `Set` em TypeScript é uma estrutura de dados que permite armazenar valores únicos, oferecendo operações eficientes para manipulação de coleções de dados sem duplicatas.