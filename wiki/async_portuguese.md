<!--
Meta Description: # Async em TypeScript: Programação Assíncrona Simplificada ## Sinopse O `async` em TypeScript é uma palavra-chave que permite a definição de funções a...
Meta Keywords: async, await, dados, uma, typescript
-->

# Async em TypeScript: Programação Assíncrona Simplificada

## Sinopse
O `async` em TypeScript é uma palavra-chave que permite a definição de funções assíncronas, facilitando o trabalho com Promises e proporcionando um código mais legível e organizado.

## Documentação
A palavra-chave `async` é utilizada para declarar funções assíncronas. Uma função marcada como `async` sempre retorna uma Promise. Se a função retornar um valor, esse valor será automaticamente encapsulado em uma Promise resolvida. Se ocorrer um erro, a Promise será rejeitada.

### Propósito
O principal objetivo do `async` é simplificar o trabalho com operações assíncronas, permitindo a utilização da palavra-chave `await` dentro da função, o que torna o código mais fácil de entender e manter.

### Uso
Para definir uma função assíncrona, basta preceder a declaração da função com a palavra-chave `async`. Dentro dessa função, você pode usar `await` para esperar a resolução de Promises.

```typescript
async function exemploAsync() {
    const resultado = await promisseQueRetornaValor();
    console.log(resultado);
}
```

## Exemplos

### Exemplo Básico
```typescript
async function buscarDados() {
    const resposta = await fetch('https://api.exemplo.com/dados');
    const dados = await resposta.json();
    return dados;
}

buscarDados().then(dados => console.log(dados));
```

### Tratamento de Erros
```typescript
async function obterDadosSeguros() {
    try {
        const resposta = await fetch('https://api.exemplo.com/dados');
        if (!resposta.ok) {
            throw new Error('Erro ao buscar dados');
        }
        const dados = await resposta.json();
        return dados;
    } catch (erro) {
        console.error(erro);
    }
}

obterDadosSeguros();
```

## Explicação
Um dos principais desafios ao trabalhar com funções assíncronas é o tratamento de erros. Quando se usa `await`, é importante envolver o código em um bloco `try...catch` para capturar possíveis exceções. Além disso, é importante lembrar que:

- Funções `async` retornam sempre uma Promise.
- O uso excessivo de `await` pode resultar em código mais lento, pois cada chamada aguarda a anterior ser concluída.
- `async` e `await` não substituem completamente o uso de Promises e podem ser usados em conjunto.

## Resumo em Uma Linha
O `async` em TypeScript facilita a criação de funções assíncronas, tornando o código mais legível e simplificando o gerenciamento de Promises.