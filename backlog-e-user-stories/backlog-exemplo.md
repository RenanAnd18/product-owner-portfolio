# Backlog de Produto – Exemplo (ERP + E-commerce)

Este backlog representa um **exemplo prático**, baseado em demandas reais do
dia a dia de um Product Owner atuando com sistemas ERP e integrações com
e-commerce e marketplaces.

---

## 📌 Contexto do Produto
ERP utilizado por lojistas para gestão de pedidos, estoque, faturamento
e integrações com plataformas de e-commerce.

---

## 🗂️ Backlog Priorizado

### 🔥 Prioridade: Alta

#### 1️⃣ Sincronização automática de status de pedidos
- **Tipo:** Feature
- **Usuário:** Lojista
- **Objetivo:** Evitar divergências entre ERP e e-commerce
- **Valor de Negócio:** Redução de chamados e retrabalho operacional
- **Status:** Em análise

**Critérios de Aceite:**
- Status atualizado em até 2 minutos
- Cancelamentos sincronizados corretamente
- Registro de logs em caso de falha

---

### 🔥 Prioridade: Alta

#### 1️⃣ Ajustar as tags da Reforma Tributária (IBS e CBS)
- **Tipo:** Feature
- **Usuário:** Lojista
- **Objetivo:** Adequar o ERP para as novas normas fiscais
- **Valor de Negócio:** Obrigações fiscais atualizadas no ERP
- **Status:** Em análise

**Critérios de Aceite:**
- No XML, adicionar as tags IBS e CBS de acordo com a norma técnica da SEFAZ
- Autorizar a NF-e na SEFAZ

---

#### 2️⃣ Correção de divergência de estoque
- **Tipo:** Bug
- **Usuário:** Lojista
- **Objetivo:** Garantir estoque confiável
- **Valor de Negócio:** Evitar vendas indevidas
- **Status:** Priorizado

**Critérios de Aceite:**
- Estoque refletido corretamente após venda
- Tratamento de concorrência entre pedidos
- Log de inconsistência gerado

---

### ⚠️ Prioridade: Média

#### 3️⃣ Dashboard de monitoramento de integrações
- **Tipo:** Melhoria
- **Usuário:** Time de suporte / PO
- **Objetivo:** Visualizar falhas de integração
- **Valor de Negócio:** Agilidade na resolução de incidentes
- **Status:** Backlog

**Critérios de Aceite:**
- Exibição de integrações com erro
- Filtro por período
- Indicação clara do tipo de falha

---

### 🧊 Prioridade: Baixa

#### 4️⃣ Exportação de pedidos em CSV
- **Tipo:** Melhoria
- **Usuário:** Lojista
- **Objetivo:** Facilitar análises externas
- **Valor de Negócio:** Conveniência para o cliente
- **Status:** Backlog
