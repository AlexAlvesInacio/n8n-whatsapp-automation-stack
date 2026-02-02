# 🔗 Automação WhatsApp com n8n, Chatwoot e Evolution API

Projeto real de automação para atendimento e campanhas via WhatsApp, utilizando n8n, Chatwoot, Evolution API e infraestrutura em VPS.

## 🧠 Problema resolvido
- Atendimento manual e desorganizado via WhatsApp
- Falta de controle de follow-up
- Campanhas sem rastreabilidade
- Dados espalhados em planilhas

## ⚙️ Solução
Criação de uma stack completa com:
- Automação de mensagens via n8n
- CRM com Chatwoot
- Integração WhatsApp via Evolution API
- Controle de campanhas via Google Sheets
- Banco de dados PostgreSQL
- Cache e controle com Redis

## 🧱 Arquitetura
- VPS Ubuntu 24.04 (Hostinger)
- Docker + EasyPanel
- n8n (automação)
- Chatwoot (CRM)
- Evolution API (WhatsApp)
- PostgreSQL + Redis

## 🔄 Fluxos implementados
- Envio automático de campanhas por horário comercial
- Controle de mensagens já enviadas
- Follow-up automático
- Atualização de status em planilhas
- Delay inteligente entre mensagens
- Fallback para humano

## 📸 Evidências
Veja a pasta `/screenshots` para prints reais do sistema em produção.

## 🧠 Aprendizados
- Orquestração de automações reais
- Integrações REST
- Tratamento de erros
- Escalabilidade
- Observabilidade básica

## 🚀 Próximos passos
- IA para classificação de leads
- Embeddings para histórico de conversa
- Dashboard analítico
