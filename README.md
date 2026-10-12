# Gestão de Skills

Fonte oficial das Skills **Delegation Context Skill** e **Agentic Workflow Governance**.
O endereço histórico do repositório foi mantido para preservar os links existentes.

## Inventário

| Skill | Versão | Fonte oficial | Instalação nativa |
| --- | --- | --- | --- |
| Delegation Context Skill | 1.1.0 | [SKILL.md](SKILL.md) | [ChatGPT](https://chatgpt.com/skills?skill_id=6acbd243c8088191b2e61b170ec6779c) |
| Agentic Workflow Governance | 1.0.0 | [Especificação canônica](skills/agentic-workflow-governance/references/especificacao-canonica.md) e [SKILL.md](skills/agentic-workflow-governance/SKILL.md) | [ChatGPT](https://chatgpt.com/skills?skill_id=6acbe3f484b48191a13bc6797c8b6bf1) |

[skills.json](skills.json) registra caminhos e versões para conferência.

## Autoridade e gestão

Em 11/10/2026, o usuário atribuiu a este chat a função de **Gestor de Skills**, responsável por criar, manter e gerir alterações destas habilidades.

- GitHub é a fonte oficial versionada das especificações, pacotes nativos e histórico de alterações.
- ChatGPT mantém as instalações nativas utilizadas nas conversas.
- Não há necessidade de documento, índice ou cópia de gestão no Drive.
- O usuário mantém a autoridade sobre decisões sensíveis e mudanças de intenção. A função de Gestor de Skills não concede autoridade sobre outros projetos.
- As alterações de Skills são executadas dentro das instruções e autorizações vigentes do usuário; conflitos materiais são apresentados antes de mudar a lógica.
- O salvamento no GitHub não atualiza automaticamente a instalação no ChatGPT. As duas etapas devem ser verificadas.

## Como as Skills se complementam

**Agentic Workflow Governance** define papéis, roteamento direto Gestor → Work/Codex, limites de autoridade, fontes da verdade, ações sensíveis e critérios de parada. É global e não contém contexto operacional de projeto específico.

**Delegation Context Skill** estrutura a delegação formal, nesta ordem:

### Informações adicionais

**Ação:** descrição executiva.

**Resultado esperado:** resultado final esperado.

**Raciocínio recomendado:** Low, Medium, High, Extra High ou Maximum — justificativa curta e prática.

### Comando / Briefing

Instruções completas necessárias ao executor.

Os três campos são sempre obrigatórios, inclusive em tarefas simples. Modelo, ferramentas, arquivos, dependências, permissões, limitações e cuidados continuam opcionais. Usar o menor nível suficiente; não duplicar passos e validações nas Informações adicionais; não gerar briefing final enquanto existir bloqueio relevante.

As Skills não substituem uma à outra e não precisam transformar conversas triviais em workflow formal.

## Fluxo de manutenção

1. Ler a fonte canônica e a decisão vigente do usuário.
2. Preparar a alteração mínima, preservando regras obrigatórias, autoridade e critérios de parada.
3. Validar estrutura, coerência das referências, exemplos e eventuais mudanças de comportamento.
4. Salvar a fonte no GitHub, atualizar versão quando necessário e registrar a alteração no [CHANGELOG.md](CHANGELOG.md).
5. Atualizar a Skill nativa existente, sem criar uma instalação duplicada.
6. Conferir os arquivos salvos nos dois ambientes e informar resultado ou bloqueio com precisão.

Não prometer acompanhamento automático de mudanças externas sem uma automação configurada.

## Estrutura e compatibilidade

A Delegation Context Skill permanece na raiz, com `SKILL.md`, metadados em `agents/` e ícone em `assets/`.

A Agentic Workflow Governance fica em `skills/agentic-workflow-governance/`, com sua especificação canônica completa em `references/`.

`prompt-mestre.md` é uma exportação do corpo do `SKILL.md` da Delegation Context Skill para uso em outros chats. Deve ser regenerado junto com a fonte, sem manter lógica divergente. O [instalador-curto.md](instalador-curto.md) aponta para a fonte vigente; [exemplos.md](exemplos.md) demonstra o comportamento.

A especificação canônica da governança preserva o conteúdo integral do anexo original. Sua seção de salvamento se refere à criação/manutenção da habilidade, e não a uma tarefa a repetir toda vez que a Skill é usada.
