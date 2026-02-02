# ✅ Critérios de Aceite – Visão de Produto

## 📌 Objetivo

Este documento apresenta exemplos de **critérios de aceite** utilizados em um contexto de **Produto Digital (ERP e E-commerce)**, com foco em garantir que as entregas:

- Atendam às necessidades do usuário
- Possuam clareza funcional
- Sejam testáveis pelo time de QA
- Entreguem valor real ao negócio

Os critérios de aceite servem como **acordo entre Produto, Desenvolvimento e Qualidade**.

---

## 🧠 Boas Práticas Utilizadas

- Escrita clara e objetiva  
- Foco no comportamento esperado, não na implementação  
- Critérios testáveis e verificáveis  
- Linguagem acessível a pessoas técnicas e não técnicas  

---

## 📋 Exemplo 1 – Faturamento de Pedido no ERP

### User Story
Como operador de faturamento,  
quero faturar pedidos integrados de marketplaces,  
para emitir a nota fiscal com agilidade e sem erros.

### Critérios de Aceite

- Dado que o pedido esteja com status **“Aprovado”**,  
  quando o usuário clicar em **“Faturar Pedido”**,  
  então o sistema deve permitir o faturamento.

- O sistema deve validar automaticamente:
  - Dados fiscais obrigatórios
  - Informações do cliente
  - Produtos e valores do pedido

- Caso exista erro de validação:
  - O faturamento não deve ser concluído
  - O sistema deve exibir uma mensagem clara indicando o problema

- Após o faturamento bem-sucedido:
  - A nota fiscal deve ser gerada
  - O status do pedido deve ser atualizado
  - O usuário deve receber uma confirmação visual de sucesso

---

## 📋 Exemplo 2 – Melhoria de Experiência do Usuário (UX)

### User Story
Como usuário do sistema,  
quero visualizar mensagens claras após realizar uma ação,  
para ter certeza de que a operação foi concluída com sucesso.

### Critérios de Aceite

- Sempre que uma ação for concluída com sucesso:
  - O sistema deve exibir uma mensagem de confirmação
  - A mensagem deve ser objetiva e de fácil entendimento

- Em caso de erro:
  - O sistema deve informar o que aconteceu
  - Deve indicar, sempre que possível, como resolver o problema

- O feedback visual deve:
  - Ser exibido imediatamente após a ação
  - Não bloquear a navegação do usuário desnecessariamente

---

## 📋 Exemplo 3 – Integração com Marketplaces

### User Story
Como analista operacional,  
quero visualizar o status da integração com marketplaces,  
para acompanhar se os pedidos estão sendo sincronizados corretamente.

### Critérios de Aceite

- O sistema deve exibir o status da integração para cada marketplace:
  - Ativo
  - Inativo
  - Com erro

- Em caso de erro:
  - Deve ser exibida uma descrição simples do problema
  - O horário da última tentativa de sincronização deve ser informado

- O usuário deve conseguir identificar rapidamente:
  - Se a integração está funcionando
  - Se alguma ação é necessária

---

## 📊 Benefícios dos Critérios de Aceite

- Redução de retrabalho
- Alinhamento entre Produto, Dev e QA
- Facilidade na validação das entregas
- Melhor previsibilidade de resultado

---

## 🚀 Visão como Product Owner

Critérios de aceite bem definidos são fundamentais para transformar **ideias em entregas de valor**.  
Eles ajudam o time a entender **o que realmente importa para o usuário**, evitando ambiguidades e desalinhamentos durante o desenvolvimento.
