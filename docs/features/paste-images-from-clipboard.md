# Colar Imagens do Clipboard

Ao instalar a extensão [vscode-paste-image](https://github.com/mushanshitiancai/vscode-paste-image), você pode colar uma imagem do clipboard com `cmd+alt+v`.

As imagens são automaticamente copiadas para a pasta `/attachments` e uma referência é adicionada no arquivo onde você as colou.

Um prompt perguntará para confirmar o nome da imagem, para desativá-lo defina `"pasteImage.showFilePathConfirmInputBox": false,` nas configurações.

Para alterar o local onde a imagem é criada, altere a propriedade `pasteImage.path`, por exemplo:

- `${currentFileDir}`: salva a imagem ao lado do arquivo
- `${currentFileDir}/images`: cria um diretório `images` ao lado do arquivo e salva a imagem lá
