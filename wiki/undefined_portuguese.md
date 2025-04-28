<!--
Meta Description: # O que é "undefined" em TypeScript: Compreensão e Uso ## Sinopse "Undefined" em TypeScript refere-se a um tipo primitivo que indica que uma variável ...
Meta Keywords: undefined, que, valor, typescript, uma
-->

# O que é "undefined" em TypeScript: Compreensão e Uso

## Sinopse
"Undefined" em TypeScript refere-se a um tipo primitivo que indica que uma variável não foi atribuída a um valor. Este artigo explora o conceito, a utilização e as nuances do tipo "undefined" em TypeScript.

## Documentação
### O que é "undefined"?
Em TypeScript, "undefined" é um dos tipos primitivos, representando uma variável que não possui um valor definido. É um conceito fundamental que ajuda a distinguir entre variáveis que não foram inicializadas e aquelas que têm um valor explícito, como `null`.

### Propósito
O uso de "undefined" é crucial para a segurança de tipos em TypeScript, pois permite que os desenvolvedores identifiquem claramente se uma variável foi inicializada ou não. Isso ajuda a evitar erros comuns em tempo de execução que podem ocorrer em JavaScript.

### Utilização
O tipo "undefined" pode ser utilizado em várias situações:
- Ao declarar uma variável sem um valor inicial.
- Como parte de tipos mais complexos, como `string | undefined`, que indica que uma variável pode ser uma string ou pode não ter um valor definido.

### Detalhes
- **Tipo Estrito**: Por padrão, TypeScript permite `undefined` como um valor, mas é possível restringir seu uso através da configuração `strictNullChecks`, que, quando ativada, exige que os desenvolvedores tratem `undefined` explicitamente.
- **Comparação com `null`**: É importante distinguir entre `undefined` e `null`. Enquanto `undefined` indica a ausência de um valor, `null` é um valor atribuído que representa a "ausência intencional" de qualquer objeto.

## Exemplos

### Exemplo 1: Declaração de variável
```typescript
let valor: number | undefined;
console.log(valor); // Saída: undefined
```

### Exemplo 2: Função com parâmetro opcional
```typescript
function exibirValor(num?: number): void {
    console.log(num);
}

exibirValor(); // Saída: undefined
```

### Exemplo 3: Uso com `strictNullChecks`
```typescript
let nome: string | undefined;
nome = "João"; // Válido
nome = undefined; // Válido

let sobrenome: string;
// sobrenome = undefined; // Erro: Tipo 'undefined' não pode ser atribuído ao tipo 'string'.
```

## Explicação
### Armadilhas Comuns
- **Acesso a propriedades de variáveis `undefined`**: Tentar acessar propriedades de uma variável que é `undefined` resulta em um erro em tempo de execução.
  
  ```typescript
  let pessoa: { nome?: string } | undefined;
  console.log(pessoa.nome); // Erro em tempo de execução
  ```

- **Comparação com `null`**: Não confundir `undefined` com `null`. O uso incorreto pode levar a comportamentos inesperados.

### Notas Adicionais
- Ative `strictNullChecks` para garantir que seu código trate `undefined` de maneira segura.
- O operador de coalescência nula (`??`) pode ser usado para fornecer um valor padrão quando uma variável é `undefined`.

## Resumo em Uma Linha
"Undefined" em TypeScript é um tipo primitivo que indica que uma variável não possui um valor definido, essencial para a segurança de tipos e o manejo de variáveis não inicializadas.