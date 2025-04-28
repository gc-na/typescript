<!--
Meta Description: # Comando "delete" em TypeScript: Como Remover Propriedades de Objetos ## Sinopse O comando `delete` em TypeScript é utilizado para remover propriedad...
Meta Keywords: delete, propriedade, remover, não, typescript
-->

# Comando "delete" em TypeScript: Como Remover Propriedades de Objetos

## Sinopse
O comando `delete` em TypeScript é utilizado para remover propriedades de objetos, permitindo que os desenvolvedores manipulem a estrutura dos mesmos de forma dinâmica durante a execução do código.

## Documentação
O `delete` é uma instrução do JavaScript que também é suportada pelo TypeScript. Sua principal finalidade é remover uma propriedade de um objeto. Quando uma propriedade é removida, ela não estará mais acessível no objeto, e sua presença no objeto será considerada `undefined`.

### Uso
A sintaxe básica do comando `delete` é a seguinte:

```typescript
delete objeto.propriedade;
```

Onde `objeto` é o objeto do qual você deseja remover a propriedade, e `propriedade` é o nome da propriedade que será excluída.

### Detalhes
- O `delete` pode ser usado para remover propriedades de objetos literais, instâncias de classes e até elementos de arrays, embora o uso em arrays não seja comum.
- O uso do `delete` não deve ser feito em variáveis e funções, já que isso resultaria em um erro. 
- O comando `delete` retorna `true` se a propriedade foi removida com sucesso, e `false` caso a propriedade não possa ser removida.

## Exemplos

### Exemplo 1: Removendo uma propriedade de um objeto
```typescript
interface Pessoa {
    nome: string;
    idade: number;
}

let pessoa: Pessoa = { nome: "João", idade: 30 };
console.log(pessoa); // { nome: "João", idade: 30 }

delete pessoa.idade;
console.log(pessoa); // { nome: "João" }
```

### Exemplo 2: Tentando remover uma propriedade não configurável
```typescript
const carro = Object.create({}, {
    marca: { value: "Fusca", writable: false, configurable: false }
});

console.log(carro.marca); // Fusca
delete carro.marca; // false
console.log(carro.marca); // Fusca
```

### Exemplo 3: Removendo propriedades de um array
```typescript
let frutas: string[] = ["maçã", "banana", "laranja"];
delete frutas[1]; // Remove "banana"
console.log(frutas); // ["maçã", <empty>, "laranja"]
```

## Explicação
Um dos principais pontos a se considerar ao usar o comando `delete` é que ele não altera o comprimento do array se usado para remover elementos de um array, resultando em um "buraco" no array (ou seja, o índice correspondente fica `undefined`). Além disso, o `delete` não pode remover propriedades que são definidas como não configuráveis.

Outro ponto importante é que, ao remover uma propriedade, caso essa propriedade tenha sido definida em um objeto a partir de uma classe, o comportamento pode variar dependendo da configuração das propriedades (ex: se são configuráveis ou não).

## Resumo em Uma Linha
O comando `delete` em TypeScript permite remover propriedades de objetos, alterando sua estrutura dinâmica durante a execução do código.