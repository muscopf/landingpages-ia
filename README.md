# Deploy De Landing Na Locaweb

Este repositório foi preparado para publicar uma landing estática na Locaweb via GitHub Actions.

## Estrutura

- `site/`: arquivos públicos da landing
- `.github/workflows/deploy-locaweb.yml`: workflow de deploy

## Como o deploy funciona

1. Você edita ou substitui os arquivos dentro de `site/`
2. Faz push para a branch `main`
3. O GitHub Actions publica o conteúdo na Locaweb

## Secrets necessários no GitHub

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
3. fazer commit/push no GitHub
4. deixar o GitHub Actions publicar automaticamente

## O que ainda falta

- conectar este diretório a um repositório GitHub
- configurar os secrets do GitHub
- ajustar o diretório remoto final da Locaweb
- integrar o n8n para publicar alterações nesse repositório
