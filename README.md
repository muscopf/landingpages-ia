# Deploy De Landing

Este repositório foi preparado para publicar uma landing estática.

Hoje existem dois caminhos possíveis:

- Firebase Hosting
- Locaweb via GitHub Actions ou FTP

## Estrutura

- `site/`: arquivos públicos da landing
- `firebase.json`: configuração do Firebase Hosting
- `.firebaserc.example`: exemplo de vínculo com o projeto Firebase
- `.github/workflows/deploy-locaweb.yml`: workflow de deploy para Locaweb

## Como o deploy no Firebase funciona

1. Você edita ou substitui os arquivos dentro de `site/`
2. Faz login na Firebase CLI
3. Vincula este diretório ao projeto Firebase
4. Executa o deploy

Comandos:

```bash
firebase login
cp .firebaserc.example .firebaserc
# edite o project id dentro do arquivo
firebase deploy --only hosting
```

## Como o deploy na Locaweb funciona

1. Você edita ou substitui os arquivos dentro de `site/`
2. Faz push para a branch `main`
3. O GitHub Actions publica o conteúdo na Locaweb

## Secrets necessários no GitHub para Locaweb

Crie estes secrets no repositório:

- `LOCAWEB_FTP_SERVER`
- `LOCAWEB_FTP_USERNAME`
- `LOCAWEB_FTP_PASSWORD`
- `LOCAWEB_REMOTE_DIR`

Exemplo comum de diretório remoto:

- `public_html/`
- `public_html/landing/`
- `public_html/seu-subdominio/`

## Próximo passo para integração com n8n

Depois que o repositório estiver conectado ao GitHub, o n8n pode:

1. gerar ou editar o HTML da landing
2. atualizar os arquivos dentro de `site/`
3. publicar no Firebase ou na Locaweb

## O que ainda falta

- escolher o projeto Firebase final
- ou regularizar o billing do GitHub para usar o deploy automático da Locaweb
- integrar o n8n para publicar alterações nesse repositório
