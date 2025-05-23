# Definições de Referência de Links

Quando você usa `[[wikilinks]]`, a extensão [foam-vscode](https://github.com/foambubble/foam/tree/main/packages/foam-vscode) pode gerar automaticamente [Definições de Referência de Links em Markdown](https://spec.commonmark.org/0.29/#link-reference-definitions) no final do arquivo. Isso não é necessário para navegar em seu espaço de trabalho com o foam-vscode, mas é útil para que os arquivos permaneçam compatíveis com várias ferramentas Markdown (por exemplo, analisadores, geradores de sites estáticos, plugins do VS Code etc.), que não suportam `[[wikilinks]]`.

## Exemplo

O seguinte exemplo:

```md
- [[wikilinks]]
- [[github-pages]]
```

...gera as seguintes definições de referência de links no final do arquivo:

```md
[wikilinks]: wikilinks 'Wikilinks'
[github-pages]: github-pages 'GitHub Pages'
```

Você pode abrir o [markdown bruto](https://foambubble.github.io/foam/features/link-reference-definitions.md) para vê-las no final deste arquivo
Você pode abrir o [markdown bruto](https://foambubble.github.io/foam/user/features/link-reference-definitions.md) para vê-las no final deste arquivo

## Especificação

Os três componentes de uma definição de referência de link são `[rótulo-do-link]: destino-do-link "Título do Link"`

- **rótulo do link:** O texto do link para corresponder no documento markdown circundante. Isso corresponde ao colchete interno da notação `[[wikilink]]` de colchetes duplos
- **destino do link** O destino do link correspondente
  - Por padrão, geramos links sem extensão. Isso pode ser substituído, veja [Configuração](#configuração) abaixo
- **"Título do Link"** Título opcional para o link (O modelo do Foam tem um trecho de JavaScript para substituir isso no site em tempo de execução)

## Configuração

Você pode escolher gerar definições de referência de links com ou sem extensões de arquivo, dependendo do destino, ou desabilitar a geração completamente. Como regra geral:

- Links com extensões de arquivo funcionam melhor com ferramentas padrão baseadas em markdown, como a interface web do GitHub.
- Links sem extensões de arquivo funcionam melhor com certas ferramentas de publicação web que tratam links como urls literais e não os transformam automaticamente, como a instalação padrão do GitHub pages.

Por padrão, o Foam gera links sem extensões de arquivo por motivos de legado, mas isso pode mudar em versões futuras.

Você pode substituir esta configuração no `settings.json` do seu espaço de trabalho Foam:

- `"foam.edit.linkReferenceDefinitions": "withoutExtensions"` (padrão)
- `"foam.edit.linkReferenceDefinitions": "withExtensions"`
- `"foam.edit.linkReferenceDefinitions": "off"`

### Ignorando arquivos

Às vezes, você pode querer ignorar certos arquivos ou pastas, para que o Foam não gere definições de referência de links para eles.

Existem três opções para excluir arquivos do seu projeto Foam:

1. `files.exclude` (do VSCode) impedirá que a pasta apareça no explorador de arquivos.

   > "Configure padrões glob para excluir arquivos e pastas. Por exemplo, o explorador de arquivos decide quais arquivos e pastas mostrar ou ocultar com base nesta configuração. Consulte a configuração Search: Exclude para definir exclusões específicas de pesquisa."

2. `files.watcherExclude` (do VSCode) impede que o VSCode monitore constantemente os arquivos em busca de alterações.

   > "Configure caminhos ou padrões glob para excluir do monitoramento de arquivos. Caminhos ou padrões glob básicos que são relativos (por exemplo `build/output` ou `*.js`) serão resolvidos para um caminho absoluto usando o espaço de trabalho atualmente aberto. Padrões glob complexos devem corresponder a caminhos absolutos (ou seja, prefixo com `**/` ou o caminho completo e sufixo com `/**` para corresponder a arquivos dentro de um caminho) para corresponder corretamente (por exemplo `**/build/output/**` ou `/Users/name/workspaces/project/build/output/**`). Quando você perceber que o processo do observador de arquivos está consumindo muito CPU, certifique-se de excluir pastas grandes que são de menor interesse (como pastas de saída de compilação)."

3. `foam.files.ignore` (do Foam) ignora arquivos de serem adicionados ao grafo do Foam.

   > "Especifica a lista de globs que serão ignorados pelo Foam (por exemplo, eles não serão considerados ao criar o grafo). Para ignorar todo o conteúdo de uma determinada pasta, use `<nomeDaPasta>/**/*`" (requer recarregar o VSCode para ter efeito).

Por exemplo, se você estiver usando uma instância local do [Jekyll](https://jekyllrb.com/), você pode descobrir que ele escreve cópias de cada arquivo `.md` em um diretório `_site`, o que pode levar o Foam a gerar referências para eles em vez das notas fonte originais.

Você pode ignorar o diretório `_site` adicionando qualquer uma das seguintes configurações ao seu arquivo `.vscode/settings.json`:

```json
  "files.exclude": {
    "**/_site": true
  },
  "files.watcherExclude": {
    "**/_site": true
  },
  "foam.files.ignore": [
    "_site/**/*"
  ]
```

Após alterar a configuração em seu espaço de trabalho, você pode executar o comando [[workspace-janitor]] para converter todas as definições existentes.

Veja [[link-reference-definition-improvements]] para mais discussões sobre problemas atuais e possíveis soluções.

