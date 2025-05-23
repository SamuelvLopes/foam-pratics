# Comandos do Foam

O Foam tem vários comandos que você pode explorar chamando a paleta de comandos e digitando "Foam".

Em particular, alguns comandos podem ser muito personalizáveis e podem ajudar com fluxos de trabalho e casos de uso personalizados.

## Comando foam-vscode.create-note

Este comando cria uma nota.
Embora funcione bem por si só, ele pode ser personalizado para alcançar vários casos de uso.
Aqui estão as configurações disponíveis para o comando:

- `notePath`: O caminho da nota a ser criada. Se for relativo, será resolvido em relação à raiz do espaço de trabalho.
- `templatePath`: O caminho do modelo a ser usado. Se for relativo, será resolvido em relação à raiz do espaço de trabalho.
- `title`: O título da nota (ou seja, a variável `FOAM_TITLE`)
- `text`: O texto a ser usado para a nota. Se um modelo também for fornecido, o modelo tem precedência
- `variables`: Variáveis a serem usadas no texto ou modelo
- `date`: A data usada para resolver as variáveis FOAM*DATE*\*. no formato `YYYY-MM-DD`
- `onFileExists?: 'overwrite' | 'open' | 'ask' | 'cancel'`: O que fazer caso o arquivo de destino já exista

Para personalizar um comando e associar uma tecla de atalho a ele, abra as configurações de teclas de atalho e adicione a configuração apropriada, aqui estão alguns exemplos:

- Criar uma nota chamada `test note.md` com algum texto. Se a nota já existir, perguntar por um novo nome

```
{
  "key": "alt+f",
  "command": "foam-vscode.create-note",
  "args": {
    "text": "test note ${FOAM_DATE_YEAR}",
    "notePath": "test note.md",
    "onFileExists": "ask"
  }
}
```

- Criar uma nota seguindo o modelo `weekly-note.md`. Se a nota já existir, abri-la

```
{
  "key": "alt+g",
  "command": "foam-vscode.create-note",
  "args": {
    "templatePath": ".foam/templates/weekly-note.md",
    "onFileExists": "open"
  }
}
```

## Comando foam-vscode.open-resource

Este comando abre um recurso.

Normalmente ele recebe um `URI`, que identifica o recurso a ser aberto.

Também é possível passar um filtro, que será executado contra os recursos do espaço de trabalho para encontrar uma ou mais correspondências.

- Se houver uma correspondência, ela será aberta
- Se houver mais de uma correspondência, um seletor rápido será exibido permitindo que o usuário selecione o recurso desejado

Exemplos:

```
{
  "key": "alt+f",
  "command": "foam-vscode.open-resource",
  "args": {
    "filter": {
      "title": "Weekly Note*"
    }
  }
}
```
