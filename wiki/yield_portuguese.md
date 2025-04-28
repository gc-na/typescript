<!--
Meta Description: # Yield em TypeScript: Entenda Como Utilizar Esta Funcionalidade Poderosa ## Sinopse O `yield` em TypeScript é uma palavra-chave utilizada em funções ...
Meta Keywords: yield, função, que, typescript, uma
-->

# Yield em TypeScript: Entenda Como Utilizar Esta Funcionalidade Poderosa

## Sinopse
O `yield` em TypeScript é uma palavra-chave utilizada em funções geradoras, permitindo a pausa e a retomada da execução de funções, facilitando a manipulação de sequências de dados de forma assíncrona e eficiente.

## Documentação
O `yield` é uma característica fundamental das funções geradoras em TypeScript, que são definidas usando a sintaxe `function*`. Estas funções permitem que você produza uma sequência de valores ao longo do tempo, ao invés de retornar todos de uma vez. Quando a palavra-chave `yield` é chamada, a execução da função é suspensa, e o valor fornecido é retornado ao chamador. Na próxima vez que a função geradora for chamada, a execução retoma do ponto onde foi pausada.

### Propósito
O principal objetivo do `yield` é fornecer uma maneira de gerar valores sob demanda, facilitando a criação de iteradores e permitindo que a execução de código seja interrompida e retomada sem perder o estado da função.

### Uso
Para utilizar `yield`, você deve definir uma função geradora. Aqui está a estrutura básica:

```typescript
function* nomeDaFuncaoGeradora() {
    yield valor1;
    yield valor2;
    // mais yields
}
```

Para invocar a função geradora, você deve usar o método `.next()`, que retorna um objeto com duas propriedades: `value` (o valor retornado pelo `yield`) e `done` (um booleano indicando se a função geradora foi concluída).

## Exemplos
### Exemplo Básico
```typescript
function* contador() {
    yield 1;
    yield 2;
    yield 3;
}

const gen = contador();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

### Exemplo com Iteração
```typescript
function* geradorDeNumeros() {
    for (let i = 0; i < 5; i++) {
        yield i;
    }
}

for (const numero of geradorDeNumeros()) {
    console.log(numero); // 0, 1, 2, 3, 4
}
```

## Explicação
É importante estar ciente de algumas particularidades ao trabalhar com `yield`:

- **Retorno de Valores**: O valor retornado por um `yield` é acessado através do método `.next()`. Se a função geradora já tiver terminado, o `value` será `undefined`.
  
- **Execução Sob Demanda**: Ao usar `yield`, a execução da função geradora é controlada manualmente, o que pode levar a confusões se não for gerenciado corretamente.

- **Contexto de Execução**: O estado da função geradora é mantido entre as chamadas de `.next()`, o que permite um controle mais flexível, mas também requer atenção para evitar efeitos colaterais indesejados.

## Resumo em Uma Linha
O `yield` em TypeScript permite a criação de funções geradoras que retornam valores sob demanda, facilitando a manipulação de sequências de dados de forma eficiente e controlada.