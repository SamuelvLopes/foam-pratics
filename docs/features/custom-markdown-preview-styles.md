# Estilos Personalizados de Visualização Markdown

O Visual Studio Code permite que você use seu próprio CSS na aba de visualização Markdown.

## Instruções

CSS personalizado para a visualização Markdown pode ser implementado usando a configuração `"markdown.styles": []` no `settings.json`. As folhas de estilo podem ser URLs https ou caminhos relativos para arquivos locais no espaço de trabalho atual.

Por exemplo, para carregar uma folha de estilo chamada `Style.css`, podemos atualizar o `settings.json` com a seguinte linha:

```
{
  "markdown.styles": ["Style.css"]
}
```

## Elementos do Foam

### Links de notas e placeholders do Foam

É possível personalizar o estilo dos links para uma nota ou placeholder. Os links são uma tag `<a>`. Para notas, use a classe `foam-note-link`, para placeholders use `foam-placeholder-link`.

### Avisos de inclusão cíclica

O Foam oferece a funcionalidade de incluir outras notas em sua nota. Isso será exibido na aba de visualização. O Foam reconhece uma inclusão cíclica de notas e exibirá um aviso quando detectado. O seguinte HTML é usado e pode ser estilizado usando a classe `foam-cyclic-link-warning`.

```html
<div class="foam-cyclic-link-warning">
  Cyclic link detected for wikilink: ${wikilink}
</div>
```
