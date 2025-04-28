<!--
Meta Description: # Tipos de Dados em TypeScript: O Tipo "number" ## Sinopse O tipo "number" em TypeScript é utilizado para representar valores numéricos, tanto inteiro...
Meta Keywords: number, tipo, typescript, para, nan
-->

# Tipos de Dados em TypeScript: O Tipo "number"

## Sinopse
O tipo "number" em TypeScript é utilizado para representar valores numéricos, tanto inteiros quanto flutuantes, permitindo que os desenvolvedores manipulem dados numéricos de forma segura e eficiente.

## Documentação
O tipo "number" é um dos tipos primitivos em TypeScript, derivado do JavaScript. Ele é utilizado para armazenar valores numéricos, incluindo inteiros, números de ponto flutuante, e números especiais como `NaN` (Not a Number) e `Infinity`.

### Propósito
O tipo "number" serve para operações matemáticas e manipulação de dados numéricos, proporcionando uma forma eficiente de lidar com cálculos e representações numéricas em aplicações web.

### Uso
Para declarar uma variável do tipo "number", você pode usar a seguinte sintaxe:

```typescript
let idade: number = 30;
let salario: number = 2500.50;
```

### Detalhes
- **Operações**: O tipo "number" suporta todas as operações matemáticas padrão, como adição (+), subtração (-), multiplicação (*), e divisão (/).
- **Conversões**: TypeScript permite conversões automáticas entre tipos, mas é importante garantir que as operações realizadas sejam válidas para evitar erros.
- **Valores Especiais**: Além de números normais, o tipo "number" pode representar `NaN`, `Infinity`, e `-Infinity`.

## Exemplos
### Declaração de Variáveis
```typescript
let a: number = 5;
let b: number = 10.5;
```

### Operações Matemáticas
```typescript
let soma: number = a + b; // soma é 15.5
let produto: number = a * b; // produto é 52.5
```

### Verificação de Valores Especiais
```typescript
let resultado: number = 0 / 0; // resultado é NaN
let infinito: number = 1 / 0; // infinito é Infinity
```

## Explicação
Embora o tipo "number" seja bastante flexível, existem algumas armadilhas comuns que os desenvolvedores podem encontrar:

- **Precisão**: Números de ponto flutuante podem sofrer de problemas de precisão. Por exemplo, operações como `0.1 + 0.2` podem não resultar exatamente em `0.3`.
- **Tipo Inferido**: Ao atribuir um valor a uma variável sem especificar o tipo, TypeScript pode inferir o tipo como "number", mas é sempre bom definir explicitamente para maior clareza.
- **NaN e Comparações**: O valor `NaN` não é igual a ele mesmo (`NaN === NaN` retorna false). Para verificar se um valor é `NaN`, utilize a função `isNaN()`.

## Resumo em Uma Linha
O tipo "number" em TypeScript é utilizado para representar e manipular valores numéricos, oferecendo suporte a operações matemáticas e representações especiais.