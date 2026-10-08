# Site de convites

Este diretório é a fonte preparada para o repositório público `camana98/camana98.github.io`.
Ele precisa ser publicado na raiz desse repositório com GitHub Pages habilitado.

O link HTTPS será `https://camana98.github.io/?invite=ABC234`. O arquivo
`.well-known/apple-app-site-association` usa o Team ID e Bundle ID do projeto.
O app compartilha essa URL HTTPS por padrão. Se a hospedagem mudar, compile
com `--dart-define=TRONO_INVITE_WEB_ORIGIN=https://novo-dominio` e atualize o
domínio associado em `ios/Runner/Runner.entitlements`.

GitHub Pages serve o arquivo de associação como `application/octet-stream`.
Em 8 de outubro de 2026, a CDN da Apple conseguiu buscá-lo e o entregou como
JSON. Ainda é preciso validar a abertura direta em um build instalado no iOS.
Se a verificação falhar, use uma hospedagem que permita responder ao arquivo
sem redirecionamento e com `Content-Type: application/json`.

O ranking online atualmente autentica apenas no iOS. Para Android App Links,
será preciso habilitar autenticação Android e publicar um `assetlinks.json`
com a impressão SHA-256 da chave que assinará o app de produção.
