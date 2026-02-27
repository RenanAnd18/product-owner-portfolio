# 🧠 Prompt de Automação — Criação em Massa de Itens "Release Notes"

## 📌 Contexto

Este prompt é utilizado no Claude Code, conectado ao Azure DevOps via MCP, para automatizar a criação de itens filhos do tipo **Release Notes** para todos os Backlog Items e Bugs da sprint ativa.

A execução acontece normalmente no início da sprint.

---

## 🎯 Objetivo

Criar automaticamente um item filho do tipo **Release Notes** para cada item da sprint que ainda não possua esse vínculo, garantindo:

- Padronização
- Rastreabilidade
- Não duplicação
- Atribuição automática
- Uso de template adequado (Feature ou Bug)

---

## 🧾 Prompt Utilizado

```text
Você está conectado ao Azure DevOps via MCP.

Objetivo:
Criar automaticamente um item filho do tipo "Release Notes" para cada Backlog Item ou Bug da sprint ativa que ainda não possua esse item vinculado.

Passos:

1. Buscar todos os Work Items da sprint atual.
2. Filtrar apenas:
   - Product Backlog Items
   - Bugs
3. Para cada item encontrado:
   - Verificar se já existe um item filho do tipo "Release Notes".
4. Caso não exista:
   - Criar um novo Work Item do tipo "Release Notes"
   - Relacionar como filho do item original
   - Definir o título no padrão:
     "Release Notes - {ID} - {Título do Item Pai}"
   - Atribuir automaticamente para: Renan Andrade
   - Inserir no campo descrição o template correspondente:

Se for Feature (Backlog Item), usar:

"Descrição da melhoria implementada:
Impacto para o negócio:
Área impactada:
Necessita comunicação externa? (Sim/Não)"

Se for Bug, usar:

"Problema corrigido:
Causa raiz:
Impacto para usuários:
Necessita comunicação externa? (Sim/Não)"

Regras:
- Não criar duplicados.
- Manter rastreabilidade hierárquica.
- Garantir padronização do título.
- Ao final, informar quantos itens foram criados.
