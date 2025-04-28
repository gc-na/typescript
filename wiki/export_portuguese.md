<!--
Meta Description: # Exportação em TypeScript: Entenda Como Usar o Comando "export" ## Sinopse O comando `export` em TypeScript permite que variáveis, funções, classes e...
Meta Keywords: export, typescript, exportação, que, padrão
-->

# Exportação em TypeScript: Entenda Como Usar o Comando "export"

## Sinopse
O comando `export` em TypeScript permite que variáveis, funções, classes e interfaces sejam disponibilizadas para serem importadas em outros módulos, promovendo a reutilização de código e a organização de projetos.

## Documentação
O `export` é uma funcionalidade fundamental do sistema de módulos do TypeScript, que é baseado no padrão ECMAScript. Ele permite que você defina o que pode ser acessado fora do módulo atual. Existem duas formas principais de usar o `export`:

1. **Exportação Nomeada**: Permite exportar múltiplos itens de um módulo. Você pode exportar variáveis, funções ou classes com nomes específicos.
   ```typescript
   export const minhaVariavel = 42;
   export function minhaFuncao() {
       console.log('Olá, TypeScript!');
   }
   ```

2. **Exportação Padrão**: Permite que um único valor ou entidade seja exportado como a exportação principal do módulo. Ao usar a exportação padrão, você pode importar o valor sem usar chaves.
   ```typescript
   export default class MinhaClasse {
       constructor() {
           console.log('Instância de MinhaClasse criada!');
       }
   }
   ```

Para importar os itens exportados em outro arquivo, você pode usar a sintaxe apropriada:

```typescript
import { minhaVariavel, minhaFuncao } from './meuModulo';
import MinhaClasse from './meuModulo';
```

## Exemplos
### Exemplo de Exportação Nomeada
```typescript
// arquivo: mathUtils.ts
export const PI = 3.14;
export function soma(a: number, b: number): number {
    return a + b;
}

// arquivo: app.ts
import { PI, soma } from './mathUtils';

console.log(PI); // 3.14
console.log(soma(2, 3)); // 5
```

### Exemplo de Exportação Padrão
```typescript
// arquivo: greeter.ts
export default function saudacao(nome: string): string {
    return `Olá, ${nome}!`;
}

// arquivo: app.ts
import saudacao from './greeter';

console.log(saudacao('Maria')); // Olá, Maria!
```

## Explicação
Ao utilizar o `export`, é importante estar atento a alguns pontos:

1. **Conflito de Nomes**: Ao exportar múltiplos itens, certifique-se de que os nomes estejam claros para evitar conflitos ao importar.
2. **Importação de Exportações Padrão**: Ao importar uma exportação padrão, você pode nomear o item como quiser, mas deve lembrar que apenas uma exportação padrão pode existir por módulo.
3. **Tipos e Interfaces**: Você também pode exportar tipos e interfaces, garantindo que sejam acessíveis em outros módulos.

## Resumo em Uma Linha
O comando `export` em TypeScript é usado para tornar variáveis, funções, classes e interfaces acessíveis em outros módulos, facilitando a organização e reutilização do código.