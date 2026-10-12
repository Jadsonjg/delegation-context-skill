# Changelog

Registrar todas as mudanças relevantes das Skills geridas neste repositório.

## Agentic Workflow Governance [2.0.0] — 2026-10-11

### Alterado
- Separada a antiga camada única `Cérebro/Gestor` em uma hierarquia multinível: `Operador / Principal Humano → Coordenador → Gestor de Domínio → Executor`.
- Coordenador passou a responder por arbitragem transversal, prioridades entre domínios, arquitetura, dependências e gates interdomínio; Gestores preservam autonomia para decidir o COMO dentro do próprio nicho.
- Executores passaram a ser definidos por capacidade abstrata, com Work, Codex e equivalentes tratados como implementações possíveis, não requisitos conceituais.
- Fontes de verdade passaram a ser descritas por categorias portáveis, mantendo Drive e GitHub apenas como exemplos de implementação.
- Governança de ações deixou de usar “efeito externo” como critério automático de confirmação e passou a avaliar `escopo autorizado × reversibilidade × risco`.
- Formalizados Handoff, auditoria de sucessor e sucessão como mecanismos normais de continuidade operacional.
- Definido que sucessão de Gestor é validada pelo Coordenador e sucessão do próprio Coordenador é validada pelo Operador/Principal Humano.
- Removida a duplicação do template interno da Delegation Context Skill; Agentic Workflow Governance mantém a interface de autoridade/roteamento/gates e a Delegation Context Skill mantém o formato vigente de delegação.
- Revisada a precedência de autoridade para respeitar segurança/sistema, Operador, governança oficial do projeto, Coordenador e Gestor de Domínio.
- A especificação canônica deixou de ser o anexo histórico imutável e passou a ser uma especificação versionada alinhada à Arquitetura de Trabalho Agentiva v2.0.
- Atualizados metadados de interface, inventário `skills.json` e README.

### Compatibilidade
- Compatível com **Arquitetura de Trabalho Agentiva v2.0**.
- Delegation Context Skill permanece em **1.1.0**; sua lógica interna não foi alterada nesta revisão.

## Delegation Context Skill [1.1.0] — 2026-10-11

### Alterado
- Raciocínio recomendado passou a ser obrigatório, ao lado de Ação e Resultado esperado, inclusive em tarefas simples.
- Definidos exatamente cinco níveis: Low, Medium, High, Extra High e Maximum; usar o menor nível suficiente, com justificativa curta.
- Modelo recomendado permanece opcional e separado de raciocínio.
- Retirada a alternativa “Informações adicionais: nenhuma”.
- Preservados os dois blocos, não duplicação, portabilidade, papéis, limites de autoridade e critérios de parada; incluídas as determinações explícitas do usuário sobre segurança, arquitetura prematura e anti-burocracia.
- Atualizados prompt mestre, instalador e exemplos para eliminar divergências com a instalação nativa.
- Incluídos SKILL.md, metadados de interface e ícone da Skill instalada.

## Agentic Workflow Governance [1.0.0] — 2026-10-11

### Adicionado
- Skill nativa e especificação canônica integral na pasta `skills/agentic-workflow-governance/`.
- Gestor como autoridade central; Work e Codex como braços paralelos, com roteamento direto.
- Limites de autoridade, critérios de parada, fontes da verdade, ações reversíveis/sensíveis, contexto e anti-burocracia.
- Complementaridade com Delegation Context Skill, preservando a precedência e os critérios de acionamento da fonte.
- Registro da proveniência do conteúdo recebido em `Texto colado.txt`, convertido em Markdown sem alteração de conteúdo.

## Gestão das Skills — 2026-10-11

### Decisão do usuário
- Atribuída a este chat a função de Gestor de Skills para criação e gestão das alterações.
- GitHub adotado como fonte oficial; não criar documento de gestão no Drive.
- Mantido o endereço do repositório existente; as duas Skills são geridas aqui.
- Atualizadas as referências de fonte nas instalações nativas; regras operacionais preservadas.

### Validação
- Estrutura nativa das duas Skills validada.
- Comportamentos já conferidos: delegação simples com Low, parada por arquivo essencial ausente, roteamento híbrido e interrupção de experimento sem autorização.
- Nesta atualização, apenas as referências de fonte das instalações foram alteradas; a lógica operacional permaneceu igual.

## [1.0.0] — 2026-10-09

### Adicionado
- Estrutura `Informações adicionais` → `Comando / Briefing`.
- Campos centrais `Ação` e `Resultado esperado`.
- Campos opcionais para modelo/raciocínio, ferramentas, arquivos, dependências, permissões, limitações e cuidados.
- Princípio de não duplicação entre contexto executivo e briefing operacional.
- Regra de interrupção antes da delegação quando houver premissa, ferramenta, dado ou direção inadequada.
- Critério para recomendar executor separado apenas quando houver especialização, recorrência, volume, complexidade ou continuidade.
- Distinção entre recomendação semântica de raciocínio e configuração técnica acionável.
- Regra de portabilidade entre plataformas.
- Prompt Mestre reutilizável.
- Instalador curto para ambientes com acesso ao repositório.
- Exemplos de aplicação.
