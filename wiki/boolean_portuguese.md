<!--
Meta Description: # Boolean em TypeScript: Entendendo o Tipo Primitivo ## Sinopse O tipo `boolean` em TypeScript é um dos tipos primitivos que representa um valor lógic...
Meta Keywords: boolean, tipo, typescript, que, como
-->

# Boolean em TypeScript: Entendendo o Tipo Primitivo

## Sinopse
O tipo `boolean` em TypeScript é um dos tipos primitivos que representa um valor lógico, podendo ser verdadeiro (`true`) ou falso (`false`). Este tipo é fundamental para a lógica de programação e o controle de fluxo em aplicações TypeScript.

## Documentação
O tipo `boolean` é utilizado para armazenar valores que podem ser avaliados como verdadeiros ou falsos. Em TypeScript, a declaração de variáveis do tipo booleano é feita de maneira semelhante a outras linguagens de programação, utilizando a palavra-chave `boolean`.

### Propósito
O principal propósito do tipo `boolean` é permitir que os desenvolvedores realizem operações lógicas, condições e controle de fluxo, facilitando a tomada de decisões em seu código.

### Uso
Para declarar uma variável do tipo `boolean`, você pode fazer o seguinte:

```typescript
let isActive: boolean = true;
let isComplete: boolean = false;
```

### Detalhes
- O tipo `boolean` pode ser utilizado em condições de controle, como `if`, `while`, `for`, entre outros.
- Ele suporta operações lógicas como `&&` (E), `||` (OU) e `!` (NÃO).
- TypeScript é fortemente tipado, portanto, é importante garantir que as variáveis booleanas sejam atribuídas apenas com valores `true` ou `false`.

## Exemplos
Aqui estão alguns exemplos de como utilizar o tipo `boolean`:

### Exemplo 1: Uso Básico
```typescript
let isUserLoggedIn: boolean = false;

if (isUserLoggedIn) {
    console.log("Bem-vindo de volta!");
} else {
    console.log("Por favor, faça login.");
}
```

### Exemplo 2: Operações Lógicas
```typescript
let hasPermission: boolean = true;
let isAdmin: boolean = false;

if (hasPermission && isAdmin) {
    console.log("Você tem acesso total.");
} else {
    console.log("Acesso negado.");
}
```

## Explicação
Embora o tipo `boolean` seja simples, alguns desenvolvedores iniciantes podem enfrentar alguns desafios. Um erro comum é tentar atribuir valores que não são booleanos, como strings ou números. Por exemplo:

```typescript
let isOnline: boolean = "sim"; // Isso causará um erro de tipo
```

Além disso, é importante lembrar que em JavaScript (e, consequentemente, em TypeScript), valores como `0`, `""` (string vazia), e `null` são considerados falsos em um contexto booleano. Portanto, ao realizar comparações, tenha cuidado para evitar confusões.

## Resumo em Uma Linha
O tipo `boolean` em TypeScript é um tipo primitivo que representa valores lógicos de verdadeiro ou falso, essencial para o controle de fluxo em aplicações.