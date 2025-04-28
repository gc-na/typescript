<!--
Meta Description: # Comando "throw" em TypeScript: Manipulação de Exceções ## Sinopse O comando `throw` em TypeScript é utilizado para lançar exceções, permitindo que o...
Meta Keywords: throw, que, error, uma, lançar
-->

# Comando "throw" em TypeScript: Manipulação de Exceções

## Sinopse
O comando `throw` em TypeScript é utilizado para lançar exceções, permitindo que os desenvolvedores interrompam a execução normal do código e tratem erros de forma controlada.

## Documentação
O `throw` é uma instrução que permite a um programa sinalizar que ocorreu um erro ou uma condição excepcional. Ao utilizar `throw`, você pode lançar uma exceção personalizada ou uma das exceções internas do JavaScript, como `Error`, `TypeError`, ou `RangeError`. 

### Propósito
O objetivo principal do `throw` é interromper o fluxo normal do programa, possibilitando que os erros sejam tratados em um bloco `try...catch`, garantindo que a aplicação não quebre de maneira inesperada.

### Uso
A sintaxe básica do `throw` é a seguinte:

```typescript
throw expression;
```

Aqui, `expression` pode ser qualquer valor que você deseja lançar como uma exceção, como uma instância de um objeto de erro ou uma string.

### Detalhes
- O `throw` deve ser utilizado dentro de funções ou blocos de código onde você deseja manipular exceções.
- Sempre que `throw` é invocado, a execução do código é interrompida, e o controle é passado para o primeiro bloco `catch` correspondente.
- Você pode lançar erros personalizados criando uma nova instância da classe `Error` ou de suas subclasses.

## Exemplos

### Exemplo 1: Lançando um erro simples
```typescript
function verificarIdade(idade: number) {
    if (idade < 18) {
        throw new Error("Você deve ter pelo menos 18 anos.");
    }
    return "Acesso permitido.";
}

try {
    console.log(verificarIdade(15));
} catch (error) {
    console.error(error.message); // Saída: Você deve ter pelo menos 18 anos.
}
```

### Exemplo 2: Lançando um erro personalizado
```typescript
class ErroPersonalizado extends Error {
    constructor(mensagem: string) {
        super(mensagem);
        this.name = "ErroPersonalizado";
    }
}

function validarNumero(num: number) {
    if (num <= 0) {
        throw new ErroPersonalizado("O número deve ser maior que zero.");
    }
    return num;
}

try {
    console.log(validarNumero(0));
} catch (error) {
    console.error(error.name + ": " + error.message); // Saída: ErroPersonalizado: O número deve ser maior que zero.
}
```

## Explicação
Ao utilizar o `throw`, é importante ter em mente algumas armadilhas comuns:
- **Não capturar erros**: Se você não envolver o código que pode lançar uma exceção em um bloco `try`, a aplicação pode parar inesperadamente.
- **Lançar tipos incorretos**: Evite lançar valores que não são instâncias de `Error`, como strings ou números, pois isso pode dificultar o tratamento de erros.
- **Não esquecer de tratar exceções**: Sempre que usar `throw`, implemente uma lógica de captura adequada para garantir que sua aplicação continue funcionando de maneira suave.

## Resumo em uma linha
O comando `throw` em TypeScript é usado para lançar exceções, permitindo um controle eficaz sobre o fluxo de erros na aplicação.