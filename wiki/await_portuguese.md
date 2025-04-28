<!--
Meta Description: # Aguardando em TypeScript: Compreendendo o Comando Await ## Sinopse O `await` é uma palavra-chave em TypeScript que permite a utilização de funções a...
Meta Keywords: await, que, dados, typescript, código
-->

# Aguardando em TypeScript: Compreendendo o Comando Await

## Sinopse
O `await` é uma palavra-chave em TypeScript que permite a utilização de funções assíncronas de forma mais simples e legível, aguardando a resolução de Promises antes de continuar a execução do código.

## Documentação
O `await` é utilizado dentro de funções marcadas com a palavra-chave `async`. Ele pausa a execução da função até que a Promise seja resolvida ou rejeitada. Isso permite que você escreva código assíncrono de maneira semelhante ao código síncrono, facilitando a leitura e a manutenção.

### Propósito
O principal objetivo do `await` é simplificar o manuseio de operações assíncronas, como chamadas a APIs ou manipulação de dados, tornando o fluxo do código mais claro.

### Uso
Para utilizar o `await`, primeiro declare uma função como `async`. Dentro dessa função, você pode usar `await` antes de uma Promise:

```typescript
async function exemplo() {
    const resultado = await promessa();
    console.log(resultado);
}
```

### Detalhes
- O `await` só pode ser usado dentro de funções assíncronas.
- Se a Promise for rejeitada, uma exceção será lançada. Para lidar com isso, é comum usar blocos `try...catch`.
- O uso excessivo de `await` pode levar a um desempenho inferior, pois o código é executado de forma sequencial, um após o outro, em vez de paralelamente.

## Exemplos
Aqui estão alguns exemplos de como usar `await` em TypeScript:

### Exemplo 1: Simples Await

```typescript
async function buscarDados() {
    const resposta = await fetch('https://api.exemplo.com/dados');
    const dados = await resposta.json();
    console.log(dados);
}
```

### Exemplo 2: Tratamento de Erros

```typescript
async function buscarDadosComErro() {
    try {
        const resposta = await fetch('https://api.exemplo.com/dados-inexistentes');
        if (!resposta.ok) {
            throw new Error('Erro ao buscar dados');
        }
        const dados = await resposta.json();
        console.log(dados);
    } catch (erro) {
        console.error(erro);
    }
}
```

## Explicação
Embora o `await` torne o código assíncrono mais fácil de ler, é importante estar ciente de alguns pontos:

- **Bloqueio da Execução**: O uso de `await` pode bloquear a execução da função até que a Promise seja resolvida. Portanto, evite o uso de múltiplos `await` em sequência, a menos que necessário.
- **Escopo de `await`**: O `await` deve ser usado apenas dentro de funções `async`. Tentar usá-lo fora desse contexto resultará em um erro de sintaxe.
- **Comportamento de Promises**: Lembre-se de que você pode aguardar várias Promises simultaneamente utilizando `Promise.all()`, que pode melhorar a eficiência.

## Resumo em uma Frase
O `await` em TypeScript facilita a escrita de código assíncrono, permitindo que funções assíncronas aguardem a resolução de Promises de forma legível e intuitiva.