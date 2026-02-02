# 🔁 Follow-up Automático de Orçamentos (WhatsApp + Chatwoot + n8n)

## ✨ Visão Geral
Este fluxo automatiza o **follow-up inteligente de orçamentos enviados via WhatsApp**, respeitando rigorosamente a **janela de 24h da Meta**, utilizando **Chatwoot + n8n + Google Sheets**.

O objetivo é **aumentar conversão**, reduzir esquecimento do cliente e **eliminar follow-ups manuais**.

---

## 🎯 Objetivo do Fluxo
- Disparar follow-up automático após envio de orçamento
- Respeitar regras da janela de 24h do WhatsApp
- Realizar nova tentativa após 72h caso não haja conversão
- Registrar todo o histórico em planilha
- Evitar mensagens fora do horário comercial

---

## 🧠 Estratégia de Follow-up

### ⏱️ Linha do tempo
| Tempo | Ação |
|-----|-----|
| Envio do PDF | Registro automático |
| +20h | Follow-up **dentro da janela Meta (mensagem comum)** |
| +72h | Follow-up **fora da janela Meta (template oficial)** |
| Venda | Fluxo interrompido automaticamente |

---

## 🧩 Arquitetura do Fluxo

O fluxo é dividido em **três partes principais**, garantindo clareza, manutenção e escalabilidade.

---

## 1️⃣ Criação do Follow-up (Entrada do Orçamento)

📌 **Disparo:**  
Quando um **PDF de orçamento é enviado no Chatwoot**.

📌 **O que acontece:**
1. Webhook recebe o evento
2. PDF é localizado
3. Dados do orçamento são extraídos
4. Campos são normalizados
5. Registro é salvo na planilha de controle

📸 Diagrama:
![Criação da lista de follow-up](../screenshots/cria_lista_followUp.png)

---

## 2️⃣ Follow-up Dentro da Janela de 24h (Mensagem Livre)

📌 **Disparo:**  
Execução agendada a cada 30 minutos.

📌 **Regras aplicadas:**
- Somente **Segunda a Sexta**
- Somente **horário comercial**
- Apenas orçamentos **ainda não vendidos**
- Apenas se **já passaram 20h do envio**

📌 **Ação:**
- Envio de mensagem comum (fora de template)
- Atualização do status na planilha

📸 Diagrama:
![Follow-up dentro da janela 24h](../screenshots/followUp_dentro_janela_24h.png)

---

## 3️⃣ Follow-up Fora da Janela (Template Oficial Meta – 72h)

📌 **Disparo:**  
Execução agendada a cada 30 minutos.

📌 **Regras aplicadas:**
- Cliente não respondeu
- Não houve conversão
- Já se passaram **72h**
- Uso obrigatório de **Template Oficial Meta**

📌 **Ação:**
- Envio de template aprovado
- Registro do novo contato na planilha
- Encerramento automático do ciclo

📸 Diagrama:
![Follow-up fora da janela Meta](../screenshots/followUp_fora_da_janela_templete_Oficial.png)

---

## 📊 Controle e Persistência de Dados

Todos os eventos são registrados na planilha central de follow-up, permitindo:

- Auditoria completa
- Métricas de conversão
- Histórico por cliente
- Base futura para BI ou IA

📸 Exemplo da planilha:
![Planilha de follow-up](../screenshots/planilha_de_followUp.png)

---

## 🔧 Tecnologias Utilizadas
- **n8n** – Orquestração e regras de negócio
- **Chatwoot** – Atendimento e eventos
- **WhatsApp Cloud API (Meta)** – Mensagens e templates
- **Google Sheets** – Persistência e controle
- **JavaScript (Function / IF nodes)** – Lógica temporal

---

## 🛡️ Boas Práticas Implementadas
- Respeito total às regras da Meta
- Prevenção de spam
- Controle de horário comercial
- Fluxo interrompido automaticamente em caso de venda
- Tokens e IDs sensíveis não versionados

---

## 🚀 Resultado Prático
✔ Follow-up automático  
✔ Zero ação manual  
✔ Mais conversões  
✔ Escalável para múltiplas campanhas  
✔ Pronto para evoluir com IA  

---

## 📌 Observação Final
Este fluxo é modular, documentado e pronto para:
- Reuso em outros funis
- Integração com CRM
- Análise de performance
- Evolução com agentes de IA


