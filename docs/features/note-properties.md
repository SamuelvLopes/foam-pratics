---
type: feature
keywords: hello world, bonjour
tags: [hello, bonjour]
---

# Propriedades de Notas

No topo do arquivo você pode ter uma seção onde define suas propriedades. Esta seção é conhecida como [Front-Matter](https://learn.cloudcannon.com/jekyll/introduction-to-jekyll-front-matter/) do documento e usa [formatação YAML](https://www.codeproject.com/Articles/1214409/Learn-YAML-in-five-minutes).

> Esteja ciente de que esta seção YAML precisa estar no topo do arquivo para ser válida.

Por exemplo, para este arquivo, temos:

```markdown
---
type: feature
keywords: hello world, bonjour
---
```

Isso define o `type` deste documento como `feature` e define **três** palavras-chave para o documento: `hello`, `world` e `bonjour`. O analisador YAML tratará tanto espaços quanto vírgulas como separadores para essas propriedades YAML. Se você quiser usar valores com múltiplas palavras para essas propriedades, precisará combinar as palavras com hífens ou sublinhados (ou seja, em vez de `hello world`, use `hello_world` ou `hello-world`).

> Você pode definir quantas propriedades personalizadas quiser para um documento, mas existem algumas [propriedades especiais](#propriedades-especiais) definidas pelo Foam.

## Propriedades Especiais

Algumas propriedades têm significado especial para o Foam:

| Nome    | Descrição                                                                                                                                                                      |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `title` | atribuirá o nome à nota que você verá no grafo, independentemente do nome do arquivo ou do primeiro cabeçalho (veja também como [[write-notes-in-foam]])                       |
| `type`  | pode ser usado para estilizar notas de forma diferente no grafo (veja também [[graph-visualization]]). O tipo padrão para um documento é `note` a menos que seja especificado de outra forma com esta propriedade. |
| `tags`  | pode ser usado para adicionar tags a uma nota (veja [[tags]])                                                                                                                                 |
| `alias` | pode ser usado para adicionar aliases à nota. um alias aparecerá no autocompletar de links                                                                                         |

Por exemplo:

```markdown
---
title: "Título da Nota"
type: "daily-note"
tags: daily, funny, planning
alias: alias1, alias2
---
```

## Propriedades de Modelos do Foam

Também existem propriedades que são ainda mais específicas para modelos do Foam, veja [[note-templates#Metadata]] para mais informações.

