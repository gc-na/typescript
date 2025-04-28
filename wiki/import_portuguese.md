<!--
Meta Description: # Importação em TypeScript: Guia Completo para Entender e Usar ## Sinopse A importação em TypeScript é uma funcionalidade fundamental que permite incl...
Meta Keywords: typescript, import, log, que, arquivo
-->

# Importação em TypeScript: Guia Completo para Entender e Usar

## Sinopse
A importação em TypeScript é uma funcionalidade fundamental que permite incluir módulos e bibliotecas em seu código, promovendo a reutilização de código e a organização eficiente de projetos.

## Documentação
A palavra-chave `import` em TypeScript é utilizada para trazer funcionalidades de outros arquivos ou módulos para o arquivo atual. Isso é essencial para modularizar o código, permitindo que diferentes partes de uma aplicação interajam entre si de maneira clara e organizada.

### Propósito
O principal objetivo da importação é facilitar a manutenção e a escalabilidade do código, permitindo que os desenvolvedores dividam suas aplicações em componentes menores e mais gerenciáveis.

### Uso
A sintaxe básica para importação em TypeScript é a seguinte:

```typescript
import { NomeDaFuncao } from './caminhoDoArquivo';
```

Você também pode importar o módulo inteiro ou renomear imports, dependendo das suas necessidades. 

### Importações Padrão
Quando um módulo exporta um único valor padrão, você pode importá-lo assim:

```typescript
import NomeDoModulo from './caminhoDoArquivo';
```

### Importações de Módulos Comuns
Se um módulo exporta múltiplas funcionalidades, você pode importar várias delas de uma só vez:

```typescript
import { Funcao1, Funcao2 } from './caminhoDoArquivo';
```

### Importando Tudo
Para importar todas as exportações de um módulo como um único objeto, utilize o asterisco:

```typescript
import * as NomeDoModulo from './caminhoDoArquivo';
```

## Exemplos

### Exemplo 1: Importando uma Função Específica
```typescript
// arquivo: matematica.ts
export function somar(a: number, b: number): number {
    return a + b;
}

// arquivo: app.ts
import { somar } from './matematica';

const resultado = somar(5, 10);
console.log(resultado); // Saída: 15
```

### Exemplo 2: Importando Módulo Inteiro
```typescript
// arquivo: utilidades.ts
export default function log(mensagem: string) {
    console.log(`Log: ${mensagem}`);
}

// arquivo: app.ts
import log from './utilidades';

log('Aplicação iniciada'); // Saída: Log: Aplicação iniciada
```

### Exemplo 3: Importando Tudo
```typescript
// arquivo: constantes.ts
export const PI = 3.14;
export const E = 2.71;

// arquivo: app.ts
import * as Constantes from './constantes';

console.log(Constantes.PI); // Saída: 3.14
```

## Explicação
Alguns dos desafios comuns ao usar importações em TypeScript incluem:

- **Caminhos Relativos**: Certifique-se de que os caminhos dos arquivos estão corretos. Um erro comum é esquecer o `./` ou usar um caminho incorreto.
- **Tipo de Exportação**: Confundir exportações padrão com exportações nomeadas pode levar a erros. Lembre-se de que você não pode usar chaves `{}` ao importar uma exportação padrão.
- **Ambientes de Execução**: Certifique-se de que o ambiente de execução (como Node.js ou navegadores) suporte a sintaxe de importação que você está utilizando.

## Resumo em Uma Linha
A importação em TypeScript permite a inclusão de módulos e bibliotecas, promovendo a organização e a reutilização de código de forma eficiente.