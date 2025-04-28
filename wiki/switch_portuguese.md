<!--
Meta Description: # Estrutura de Controle "switch" em TypeScript: Guia Completo ## Sinopse A estrutura de controle `switch` em TypeScript permite a execução de diferent...
Meta Keywords: switch, break, expressão, case, uma
-->

# Estrutura de Controle "switch" em TypeScript: Guia Completo

## Sinopse
A estrutura de controle `switch` em TypeScript permite a execução de diferentes blocos de código com base no valor de uma expressão, proporcionando uma alternativa mais legível ao uso de múltiplos `if-else`.

## Documentação
O `switch` é uma construção de controle de fluxo que facilita a seleção de um bloco de código a ser executado com base no valor de uma expressão. É especialmente útil quando se precisa comparar uma variável contra várias opções possíveis, tornando o código mais limpo e fácil de entender.

### Estrutura Básica

A sintaxe básica do `switch` é a seguinte:

```typescript
switch (expressão) {
    case valor1:
        // bloco de código a ser executado se expressão === valor1
        break;
    case valor2:
        // bloco de código a ser executado se expressão === valor2
        break;
    default:
        // bloco de código a ser executado se nenhum caso anterior for correspondente
}
```

### Componentes Principais
- **expressão**: A expressão que será avaliada.
- **case**: Cada `case` especifica um valor a ser comparado com o resultado da expressão.
- **break**: A instrução `break` é usada para sair da estrutura `switch` após a execução do bloco correspondente. Sem o `break`, a execução continuará nos casos subsequentes (comportamento chamado de "fall-through").
- **default**: O bloco `default` é opcional e será executado se nenhum dos casos corresponder ao valor da expressão.

## Exemplos

### Exemplo 1: Uso Básico do `switch`

```typescript
let dia: number = 2;

switch (dia) {
    case 1:
        console.log("Domingo");
        break;
    case 2:
        console.log("Segunda-feira");
        break;
    case 3:
        console.log("Terça-feira");
        break;
    default:
        console.log("Outro dia");
}
```
Saída: `Segunda-feira`

### Exemplo 2: Fall-through no `switch`

```typescript
let cor: string = "vermelho";

switch (cor) {
    case "vermelho":
    case "azul":
        console.log("Cor primária");
        break;
    case "verde":
        console.log("Cor secundária");
        break;
    default:
        console.log("Outra cor");
}
```
Saída: `Cor primária`

## Explicação

### Armadilhas Comuns
- **Falta de `break`**: Um erro comum é esquecer de adicionar a instrução `break`. Isso pode levar ao comportamento inesperado de execuções "fall-through", onde múltiplos blocos de código são executados.
- **Comparação de Tipos**: O `switch` utiliza a comparação estrita (`===`), portanto, tipos diferentes não serão considerados iguais. Por exemplo, `0` (número) e `"0"` (string) são diferentes.
- **Complexidade Excessiva**: Em casos onde há muitos casos ou lógica complexa, considere usar um objeto ou uma estrutura de dados para mapear valores, que pode ser mais legível e eficiente.

## Resumo em Uma Linha
A estrutura `switch` em TypeScript permite a seleção de blocos de código a serem executados com base no valor de uma expressão, oferecendo uma alternativa legível ao uso de múltiplos `if-else`.