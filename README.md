# Guia Interativo PGDP/UNEB — MVP (Django)

Este repositório contém um **protótipo** do aplicativo web para o Manual/Guia Interativo da PGDP/UNEB.

## Como rodar (local)
1. Crie um virtualenv e instale dependências:
   ```bash
   python -m venv .venv && source .venv/bin/activate
   pip install -r requirements.txt
   ```
2. Inicie o projeto (SQLite):
   ```bash
   python manage.py migrate
   python manage.py loaddata guia/fixtures/initial_data.json
   python manage.py runserver
   ```
3. Acesse: http://127.0.0.1:8000

## Credenciais de admin
- Crie um superuser:
  ```bash
  python manage.py createsuperuser
  ```

## O que vem pronto
- Modelos de **Procedimento**, **Base Legal**, **Documentos**, **Passos**, **Fluxo**, **Links para o SEI** e **FAQ**.
- Página inicial com **busca** e **filtro por eixo**.
- Página de detalhe do procedimento com botão **“Abrir no SEI”** e **“Gerar PDF”** (via impressão do navegador).
- **Django Admin** configurado para edição do conteúdo.
- **Tailwind** via CDN para estilização rápida.
- Exemplo de 2 procedimentos: **Licença Maternidade** e **Abono Permanência**.

## Produção (esboço)
- `gunicorn` + `whitenoise` + `nginx` (Docker recomendado).
- Habilitar SSO (OIDC/SAML) e analytics (Matomo/Umami) conforme política da UNEB.

> **Importante:** Substitua as URLs de exemplo do SEI pelas URLs reais providas pela equipe técnica do SEI/UNEB.
