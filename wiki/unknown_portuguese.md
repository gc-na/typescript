<!--
Meta Description: # Tipo `unknown` em TypeScript: Compreendendo e Utilizando ## Sinopse O tipo `unknown` em TypeScript é uma forma segura de representar valores que pod...
Meta Keywords: tipo, unknown, uma, que, typescript
-->

# Tipo `unknown` em TypeScript: Compreendendo e Utilizando

## Sinopse
O tipo `unknown` em TypeScript é uma forma segura de representar valores que podem ser de qualquer tipo, mas que exigem verificação antes de serem utilizados. Ele proporciona uma maneira de lidar com valores desconhecidos enquanto mantém a segurança de tipos.

## Documentação
O tipo `unknown` foi introduzido no TypeScript 3.0 como uma alternativa mais segura ao tipo `any`. Enquanto `any` permite que você faça qualquer operação em uma variável sem restrições, `unknown` exige que você faça uma verificação de tipo antes de realizar qualquer operação com o valor. Essa característica ajuda a evitar erros em tempo de execução e torna o código mais robusto.

### Propósito
O propósito principal do tipo `unknown` é fornecer um tipo seguro para valores que podem ser de qualquer tipo, mas que não são conhecidos até que uma verificação de tipo seja realizada. Isso é especialmente útil em situações onde os dados vêm de fontes externas, como APIs ou entradas do usuário.

### Uso
Para usar o tipo `unknown`, você o declara da mesma forma que outros tipos em TypeScript. Aqui está um exemplo básico de como declarar uma variável do tipo `unknown`:

```typescript
let valorDesconhecido: unknown;
```

Para utilizar um valor do tipo `unknown`, você deve primeiro fazer uma verificação de tipo:

```typescript
if (typeof valorDesconhecido === 'string') {
    console.log(valorDesconhecido.toUpperCase()); // Uso seguro após verificação
}
```

## Exemplos
### Exemplo 1: Uso básico do tipo `unknown`

```typescript
let dado: unknown;

dado = "Uma string";
if (typeof dado === "string") {
    console.log(dado.toLowerCase()); // Saída: uma string
}
```

### Exemplo 2: Verificação com diferentes tipos

```typescript
let valor: unknown;

valor = 42;

if (typeof valor === "number") {
    console.log(valor + 10); // Saída: 52
} else if (typeof valor === "string") {
    console.log(valor.length);
}
```

## Explicação
Uma armadilha comum ao usar o tipo `unknown` é tentar acessar propriedades ou métodos de uma variável sem a devida verificação de tipo. Isso resultará em um erro de compilação, pois o TypeScript não permite operações inseguras em valores do tipo `unknown`. Portanto, sempre verifique o tipo antes de usar o valor.

Outra consideração é que, ao usar `unknown`, você deve sempre realizar checagens de tipo, o que pode aumentar a quantidade de código em algumas situações. No entanto, isso traz segurança, prevenindo erros que poderiam ocorrer com o uso do tipo `any`.

## Resumo em Uma Linha
O tipo `unknown` em TypeScript oferece uma maneira segura de trabalhar com valores desconhecidos, exigindo verificações de tipo antes do uso.