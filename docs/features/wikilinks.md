# Wikilinks

Wikilinks são os links internos que conectam os arquivos em sua base de conhecimento. (Também chamados de links `[[MediaWiki]]`).

## Criando e navegando por wikilinks

Para criar um wikilink, digite `[[` e então comece a digitar o nome de outra nota em seu repositório. Uma vez que a nota desejada seja selecionada, pressione a tecla `tab` para autocompletar. Por exemplo: [[graph-visualization]].

`Cmd` + `Click` (`Ctrl` + `Click` no Windows) em um wikilink para navegar até aquela nota (`F12` também funciona enquanto seu cursor estiver no wikilink). Se o arquivo não existir, ele será criado em seu espaço de trabalho com base nas suas configurações padrão de [[note-templates]].

## Placeholders

Você também pode criar um [[placeholder]]. <!--NOTE: this placeholder link should NOT have an associated file. This is to demonstrate the concept-->
Um placeholder é um wikilink que não tem um arquivo de destino e um link para um placeholder é estilizado de forma diferente para que você possa facilmente diferenciá-los.
Eles ainda podem ser úteis para destacar conexões.

Abra o grafo com o comando `Foam: Show Graph` e observe o nó do placeholder.

Lembre-se, com `CTRL/CMD+click` em um wikilink você pode navegar até a nota ou criá-la (se o link for um placeholder).

## Suporte para seções

O Foam suporta autocompletar, navegação, incorporação e diagnósticos para seções de notas. Basta usar a sintaxe wiki padrão de `[[recurso#Título da Seção]]`. 
- Se for um arquivo externo, `[seu link precisará do nome do arquivo](outro-arquivo.md#aquela-secao-que-quero-linkar)`, mas
- se for uma âncora dentro do mesmo documento, `[você só precisa de uma cerquilha e o nome da seção](#aquela-secao-acima)`.  
- Não importa qual o nível do cabeçalho da âncora; seja você esteja linkando para um `H1` como `# HOMENS ANDAM NA LUA` ou um `H2` como `## Astronautas Pousam na Planície`, a sintaxe do link usa uma única cerquilha: `[Andar!](#homens-andam-na-lua)` e `[Pousar!](#astronautas-pousam-na-planicie)`. O autocompletar é seu amigo aqui.

## Compatibilidade com Markdown

A extensão [Foam for VSCode](https://marketplace.visualstudio.com/items?itemName=foam.foam-vscode) gera automaticamente [[link-reference-definitions]] no final do arquivo para tornar os wikilinks compatíveis com outras ferramentas e analisadores de Markdown.

## Leia mais

- [[foam-file-format]]
- [[note-templates]]
- Veja [[link-reference-definition-improvements]] para mais discussões sobre problemas atuais e possíveis soluções.

