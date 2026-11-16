# Sig-bot Filter

Middleware do Sig Bot.

## Arquitetura

Evolution API
↓
Betalandia Filter
↓
n8n
↓
Google Gemini
↓
Evolution API

## Função

O filtro recebe eventos da Evolution API e verifica:

- Evento `messages.upsert`
- Mensagem não enviada pelo próprio bot
- Mensagem pertence ao grupo Betalandia
- Mensagem começa com `sig`

Somente mensagens aprovadas são encaminhadas para o n8n.

## Variáveis de ambiente

### N8N_WEBHOOK_URL

URL de produção do webhook do n8n.

### GROUP_JIDS

JID dos grupo.

Valor padrão:

Grupo de Teste 120363431774163794@g.us

### PORT

A Railway fornece automaticamente essa variável.

## Executar localmente

```bash
npm install
npm start
