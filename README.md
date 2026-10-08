# Site de convites

Este diretório é a fonte preparada para o repositório público `camana98/camana98.github.io`.
Ele precisa ser publicado na raiz desse repositório com GitHub Pages habilitado.

O link HTTPS será `https://camana98.github.io/?invite=ABC234`. O arquivo
`.well-known/apple-app-site-association` usa o Team ID e Bundle ID do projeto.
Antes de ativar o link HTTPS no app, confira a resposta pública desse arquivo,
inclusive status 200, sem redirecionamento e `Content-Type: application/json`.
GitHub Pages pode servir arquivos sem extensão com outro MIME; nesse caso,
é necessário hospedar a associação em um serviço que permita definir esse
cabeçalho. O site de fallback continua útil no GitHub Pages.

Depois da verificação, compile o app com
`--dart-define=TRONO_INVITE_WEB_ORIGIN=https://camana98.github.io` para
compartilhar a URL HTTPS. Sem essa definição, o app compartilha o link direto
`cagadaremunerada://app/invite/CODIGO` e oferece o código manual no texto.

O ranking online atualmente autentica apenas no iOS. Para Android App Links,
será preciso habilitar autenticação Android e publicar um `assetlinks.json`
com a impressão SHA-256 da chave que assinará o app de produção.
