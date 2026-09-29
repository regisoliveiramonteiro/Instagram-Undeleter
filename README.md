# Arquivo / Instagram

Aplicativo estático para pesquisar conversas presentes na exportação de dados da própria conta do Instagram. A leitura acontece no navegador; nenhum login é solicitado e os arquivos não são enviados a um servidor.

## Usar

Abra `index.html` em uma versão atualizada do Microsoft Edge ou Google Chrome. Importe o ZIP original da exportação, a pasta já extraída ou os arquivos JSON de mensagens. O app reconhece os arquivos `message_*.json` dentro de `messages/inbox` e permite pesquisar o conteúdo carregado na sessão. Use **Limpar arquivo** ou feche a página para remover os dados da sessão.

A exportação deve estar no formato JSON para que as mensagens possam ser lidas. A leitura de ZIP usa `DecompressionStream` do navegador; se o navegador não oferecer suporte, extraia o ZIP e escolha a pasta extraída.

## Limites

Este app apenas exibe mensagens que estejam presentes nos dados exportados. Não recupera mensagens que não foram incluídas pela Meta, não restaura mensagens na conta e não acessa servidores do Instagram. Anexos binários não são exibidos; quando identificáveis, aparecem como marcadores como `[Foto]` ou `[Áudio]`.

Não há build nem instalação de dependências: o projeto usa HTML, CSS e JavaScript nativos.

## Publicar no GitHub Pages

O workflow `.github/workflows/deploy-pages.yml` publica `index.html` automaticamente quando há push para `main` ou `master` (ou quando iniciado manualmente em Actions). Depois de enviar o projeto para um repositório GitHub:

1. Abra **Settings > Pages** no repositório.
2. Em **Build and deployment > Source**, selecione **GitHub Actions**.
3. Aguarde a execução do workflow em **Actions**; o endereço publicado aparece no ambiente `github-pages` da execução.

O workflow publica apenas o app. Os dados importados continuam no navegador de cada visitante.
