# Filtros de Recursos

Filtros de recursos podem ser passados para alguns comandos do Foam para limitar seu escopo.

Um filtro suporta os seguintes parâmetros:

- `tag`: inclui um recurso se ele tiver a tag especificada (ex: `{"tag": "#research"}`)
- `type`: inclui um recurso se ele for do tipo especificado (ex: `{"type": "daily-note"}`)
- `path`: inclui um recurso se seu caminho corresponder à regex especificada (ex: `{"path": "/projects/*"}`). **Note que este parâmetro suporta regex e não globs.**
- `expression`: inclui um recurso se ele tornar a expressão especificada `true`, onde `resource` representa o recurso sendo avaliado (ex: `{"expression": "resource.type ==='weekly-note'"}`)
- `title`: inclui um recurso se o título corresponder à regex especificada (ex: `{"title": "Team meeting:*"}`)

Um filtro também suporta alguns operadores lógicos:

- `and`: inclui um recurso se ele corresponder a todos os sub-parâmetros (ex: `{"and": [{"tag": "#research"}, {"title": "Paper *"}]}`)
- `or`: inclui um recurso se ele corresponder a qualquer um dos sub-parâmetros (ex: `{"or": [{"tag": "#research"}, {"title": "Paper *"}]}`)
- `not`: inverte o resultado do filtro aninhado (ex: `{"not": {"type": "daily-note"}}`)

Aqui está um exemplo de um filtro complexo, por exemplo para mostrar o grafo do Foam apenas de um subconjunto do espaço de trabalho:

```
{
  "key": "alt+f",
  "command": "foam-vscode.show-graph",
  "args": {
    "filter": {
      "and": [
        {
          "or": [
            { "type": 'daily-note' },
            { "type": 'weekly-note' },
            { "path": '/projects/*' },
          ],
          "not": {
            { "tag": '#b' },
          },
        },
      ],
    }
  }
}
```
