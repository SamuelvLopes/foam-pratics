# Notas Diárias

As notas diárias permitem que você crie e acesse rapidamente um novo arquivo de notas para cada dia. Esta é uma estratégia surpreendentemente eficaz e cada vez mais comum para organizar notas e gerenciar eventos.

Visualize o arquivo de notas de hoje executando o comando `Foam: Open Daily Note`, usando o atalho `alt+d` (nota: os atalhos podem ser [substituídos](https://code.visualstudio.com/docs/getstarted/keybindings)), ou usando [#snippets](#Snippets). O nome, localização e título dos arquivos de notas diárias são [#configuráveis](#Configuration).

## Notas Diárias Automáticas Estilo Roam

Você pode abrir automaticamente a nota de hoje na inicialização definindo a configuração `Foam › Open Daily Note: On Startup` como `true`.

## Modelos de Notas Diárias

As notas diárias também podem fazer uso de [[Note Templates]], definindo um modelo especial em `.foam/templates/daily-note.md`.

## Snippets

Crie um link para uma nota diária recente usando [snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets). Digite `/today` e pressione `enter` para criar um link para a nota de hoje. Você também pode escrever:

| Snippet      | Data          |
| ------------ | ------------- |
| `/tomorrow`  | amanhã        |
| `/yesterday` | ontem         |
| `/monday`    | próxima segunda-feira |
| `/+1d`       | amanhã        |
| `/-3d`       | há 3 dias     |
| `/+1w`       | em uma semana |
| `/-1m`       | há um mês     |
| `/+1y`       | em um ano     |

## Configuração

Por padrão, as Notas Diárias serão criadas em um arquivo chamado `yyyy-mm-dd.md` na pasta `journals` do espaço de trabalho, com o cabeçalho `yyyy-mm-dd`.

Essas configurações podem ser substituídas no seu arquivo `.vscode/settings.json` do espaço de trabalho ou global, usando a sintaxe de máscara de data [**dateformat**](https://github.com/felixge/node-dateformat#mask-options):

É possível personalizar o caminho e o cabeçalho de suas notas diárias, seguindo a [sintaxe de máscara dateformat](https://github.com/felixge/node-dateformat#mask-options).
As seguintes propriedades podem ser usadas:

```json
  "foam.openDailyNote.directory": "journal",
  "foam.openDailyNote.filenameFormat": "'daily-note'-yyyy-mm-dd",
  "foam.openDailyNote.fileExtension": "mdx",
  "foam.openDailyNote.titleFormat": "'Journal Entry, ' dddd, mmmm d",
```

A configuração acima criaria um arquivo `journal/daily-note-2020-07-25.mdx`, com o cabeçalho `Journal Entry, Sunday, July 25`.

> NOTA: É possível definir o caminho do arquivo de uma nota diária de acordo com a data usando as [[note-properties]] especiais configuráveis para [[Note Templates]]. Especificamente, veja [[note-templates#Example of date-based|Exemplo de caminho baseado em data]]. Usar a propriedade do modelo substituirá qualquer configuração feita através do `.vscode/settings.json`.

## Estender Funcionalidade (Notas Semanais, Mensais, Trimestrais)

Por favor, veja [[note-macros]]

