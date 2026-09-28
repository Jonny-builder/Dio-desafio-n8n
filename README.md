# Dio-desafio-n8n
# 📦 Desafio Criativo DIO: Automação Logística com N8N

## 🎯 Passo 1: Automação Desejada
Quero criar uma automação no N8N para **validar automaticamente a disponibilidade de insumos em estoque sempre que uma ordem de produção for criada**.

* **Público ou responsável:** Equipe de Logística, Planejamento de Produção (PCP) e Compras.
* **Resultado esperado:** Identificar a falta de materiais antecipadamente, alertar a equipe de Compras via e-mail com a data limite de entrega (5 dias antes) e avisar a Produção no Slack.

---

## ⚙️ Passo 2: Contexto e Regras
* **Ferramentas envolvidas:** Google Sheets, Slack e Gmail.

* **Fluxo desejado:**
1. Detectar nova ordem de produção inserida no Google Sheets.
2. Consultar o saldo atual de matéria-prima no estoque (Google Sheets).
3. Validar via condição lógica se a quantidade disponível atende à ordem.
4. **Se faltar insumo:** Enviar e-mail (Gmail) ao setor de Compras com a lista de materiais e data limite (5 dias antes do início da produção), marcar a planilha como "Pendente" e alertar no Slack da Logística.
5. **Se houver estoque suficiente:** Marcar a planilha como "Aprovado" e notificar o canal de Produção no Slack.

* **Regras importantes:**
  * A entrega do insumo deve ocorrer no mínimo 5 dias antes do início da fabricação.
  * O status da linha no Google Sheets deve ser sempre atualizado para manter o histórico centralizado.

---

## 🚀 Passo 3: Prompt Final

```text
Atue como um especialista em N8N e automação de processos.

Crie uma automação para validar a disponibilidade de estoque de matérias-primas antes do início da produção de um produto.

Público:
Equipes de Logística, Produção e Compras.

Ferramentas envolvidas:
Google Sheets, Gmail e Slack.

Fluxo:
1. Disparar quando uma nova ordem de produção for inserida na planilha do Google Sheets.
2. Buscar o estoque atual dos insumos necessários.
3. Avaliar se o estoque é suficiente:
   - Se insuficiente: Enviar e-mail (Gmail) para Compras solicitando aquisição com prazo limite de até 5 dias antes da produção, atualizar status na planilha para "Pendente" e emitir alerta no Slack.
   - Se suficiente: Atualizar status na planilha para "Aprovado" e notificar a equipe de Produção no Slack.

Regras:
- O prazo limite de reposição deve considerar a antecedência mínima de 5 dias da data de produção.
- Manter o status sempre atualizado no Google Sheets.

Explique detalhadamente quais nós do N8N devem ser utilizados (Triggers, Nodes de leitura/escrita, IF e nós de comunicação) e forneça um passo a passo simples de configuração da lógica do workflow.
