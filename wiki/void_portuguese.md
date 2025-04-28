<!--
Meta Description: # Entendendo o Tipo "void" no TypeScript ## Sinopse O tipo `void` em TypeScript é utilizado para indicar que uma função não retorna um valor. É uma pa...
Meta Keywords: void, que, função, uma, tipo
-->

# Entendendo o Tipo "void" no TypeScript

## Sinopse
O tipo `void` em TypeScript é utilizado para indicar que uma função não retorna um valor. É uma parte fundamental da tipagem estática que ajuda a garantir a integridade do código.

## Documentação
O tipo `void` é frequentemente usado em funções que não precisam retornar um valor. Em TypeScript, quando você declara uma função que não retorna nada, você pode especificar o tipo de retorno como `void`. Isso é útil para deixar claro para outros desenvolvedores (ou para você mesmo no futuro) que a função foi projetada para realizar uma ação sem fornecer um resultado.

### Uso
Aqui está a sintaxe básica para declarar uma função com um tipo de retorno `void`:

```typescript
function nomeDaFuncao(): void {
    // lógica da função
}
```

### Detalhes
- O tipo `void` não deve ser confundido com `undefined`. Uma função que retorna `void` pode não retornar nada (ou seja, não retorna um valor), enquanto uma função que retorna `undefined` explicitamente retorna um valor do tipo `undefined`.
- O uso de `void` é especialmente comum em funções que têm efeitos colaterais, como manipulação de DOM ou chamadas de API.

## Exemplos
Aqui estão alguns exemplos básicos de como usar o tipo `void`:

### Exemplo 1: Função sem retorno
```typescript
function mostrarMensagem(): void {
    console.log("Olá, mundo!");
}

mostrarMensagem(); // Chama a função, mas não retorna valor
```

### Exemplo 2: Função com operações que não retornam valor
```typescript
function adicionarElemento(array: number[], elemento: number): void {
    array.push(elemento);
}

const numeros: number[] = [1, 2, 3];
adicionarElemento(numeros, 4);
console.log(numeros); // Saída: [1, 2, 3, 4]
```

## Explicação
Ao usar `void`, é importante lembrar que:

- **Evitar Retornos Indesejados**: Se você declarar uma função como `void`, deve evitar retornar qualquer valor. Retornos indesejados podem causar confusão e erros de compilação.
- **Interação com Promessas**: Ao trabalhar com funções assíncronas, como aquelas que retornam Promises, `void` não deve ser usado como tipo de retorno para funções que fazem chamadas assíncronas. Isso porque a função pode, de fato, retornar uma Promise que eventualmente resolve para `undefined`. Nesses casos, é melhor utilizar `Promise<void>`.
- **Tipos de Funções de Callback**: Ao definir funções de callback que não retornam valores, o tipo `void` é uma escolha adequada.

## Resumo em Uma Linha
O tipo `void` em TypeScript é utilizado para indicar que uma função não retorna um valor, ajudando a manter a clareza e a segurança do código.