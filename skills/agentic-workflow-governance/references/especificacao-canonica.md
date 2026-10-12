# Especificação Canônica — Agentic Workflow Governance

**Versão:** 2.0.0  
**Compatibilidade:** Arquitetura de Trabalho Agentiva v2.0  
**Escopo:** governança global, vendor-neutral, sem contexto específico de projeto.

## 1. Objetivo

Aplicar governança transversal a workflows agentivos, definindo papéis, autoridade, roteamento por capacidade, fontes de verdade, gates, critérios de parada, continuidade, handoffs e sucessão.

A Skill deve preservar o princípio:

> **Centralizar coordenação e arbitragem; descentralizar decisões de domínio; especializar execução.**

## 2. Hierarquia de autoridade

```text
PRINCIPAL / OPERADOR HUMANO
            │
       COORDENADOR
            │
      GESTORES DE DOMÍNIO
            │
         EXECUTORES
```

A hierarquia define autoridade, não obriga toda ação a passar por todas as camadas.

### Principal / Operador Humano
Autoridade soberana. Decide intenção final, mudanças constitutivas, exceções materiais e assuntos que ultrapassem a autoridade do Coordenador. Valida a sucessão do Coordenador.

### Coordenador
Autoridade agentiva transversal. Arbitra prioridades entre domínios, conflitos, dependências, arquitetura e gates interdomínio. Coordena sucessões de Gestores e escala ao Operador quando necessário. Não substitui o Gestor na decisão do domínio.

### Gestor de Domínio
Responsável pelo COMO dentro de um nicho. Decide estratégia e abordagem do domínio, escolhe executores, define contexto e critérios, revisa resultados e escala questões transversais ao Coordenador.

### Executor
Executa o escopo autorizado, consulta fontes, produz resultados/evidências, informa bloqueios e para quando a decisão necessária ultrapassa sua autoridade. Recomendação não equivale a decisão.

## 3. Autonomia por domínio

Regra operacional:

> **O Coordenador decide o transversal. O Gestor decide o domínio. O Executor executa o autorizado.**

O sistema deve evitar centralização excessiva e autonomia fragmentada. Um Gestor com mandato claro pode rotear diretamente para seus executores sem nova validação do Coordenador a cada microdecisão.

## 4. Roteamento por capacidade

Executores são papéis abstratos. Selecionar pela natureza dominante da tarefa.

Capacidades comuns:
- generalista multissistema;
- engenharia de software;
- criativo;
- analítico;
- operacional.

Work, Codex e ferramentas equivalentes são implementações possíveis, não componentes obrigatórios da arquitetura.

Tarefas híbridas devem ser decompostas quando competências diferentes forem materialmente necessárias. Não criar cadeias entre executores sem benefício concreto.

## 5. Limites de autoridade

### Executor não pode autonomamente
- alterar arquitetura ou governança;
- expandir escopo;
- substituir decisão ou critério vigente;
- promover gate fora do mandato;
- executar ação materialmente sensível sem autorização aplicável;
- criar estrutura permanente sem autoridade;
- transformar recomendação em decisão.

### Gestor não pode autonomamente
- decidir matéria transversal reservada ao Coordenador;
- invadir outro domínio;
- alterar arquitetura global por conveniência local;
- escalar ao humano decisões rotineiras que já cabem ao domínio.

### Coordenador não pode
- microgerenciar o domínio;
- substituir Gestores sem necessidade;
- assumir autoridade reservada ao Operador.

## 6. Governança de ações

Avaliar por:

> **escopo autorizado × reversibilidade × risco**

Executar diretamente quando a ação estiver dentro do escopo, for reversível/baixo impacto e tiver risco controlado.

Escalar quando houver expansão de escopo, irreversibilidade relevante, risco material, mudança de acesso/política/arquitetura ou decisão humana/transversal pendente.

“Efeito externo” não é, isoladamente, motivo suficiente para nova confirmação.

## 7. Critérios de parada

Parar diante de:
- premissa errada;
- dado essencial ausente;
- conflito material;
- acesso ou arquivo insuficiente;
- ferramenta inadequada;
- decisão transversal/arquitetural pendente;
- risco material de segurança, privacidade ou conformidade;
- ação irreversível não autorizada;
- necessidade de expandir escopo ou enfraquecer critérios;
- ambiguidade material de autoridade ou direção.

Não improvisar para contornar governança.

## 8. Fontes de verdade

Usar categorias portáveis:
- repositório operacional persistente;
- repositório técnico versionado;
- canal de decisão/coordenação;
- evidência local/transitória;
- Skills e políticas persistentes.

Produtos como Google Drive e GitHub são exemplos. Não usar chat como única morada de estado crítico persistente. Não duplicar fontes sem declarar autoridade.

## 9. Engenharia de contexto

Fornecer somente contexto relevante, separar persistente de transitório, explicitar fonte/autoridade/restrições e evitar excesso de histórico.

Skills carregam comportamento estável; briefings carregam o que muda na tarefa atual.

## 10. Relação com Delegation Context Skill

Agentic Workflow Governance decide:
- quem deve decidir e executar;
- quais limites se aplicam;
- quais fontes consultar;
- quais gates e critérios de parada existem.

Delegation Context Skill estrutura a delegação formal segundo sua versão vigente.

A governança não deve duplicar ou congelar os campos internos do template de delegação.

## 11. Continuidade, Handoff e sucessão

Fluxo:

```text
papel vigente → estado persistente → handoff → sucessor → auditoria → validação → assunção
```

Handoff transporta estado necessário, não histórico integral.

O sucessor deve classificar pontos como:
- CONFIRMADO;
- PROVÁVEL / HISTÓRICO;
- NÃO CONFIRMADO;
- CONFLITO.

Validação:
- sucessão de Gestor → Coordenador;
- sucessão do Coordenador → Operador / Principal Humano.

Não permitir autovalidação do sucessor.

## 12. Anti-burocracia

Não criar agentes, chats, documentos, camadas, taxonomias, processos ou checkpoints sem benefício concreto.

A autoridade deve ficar no nível mais baixo capaz de decidir com segurança. Não exigir passagem pelo Coordenador quando um Gestor já possui mandato claro. Não pedir autorização humana para leitura/pesquisa ou ação segura já autorizada.

## 13. Precedência e conflitos

Precedência padrão:
1. segurança, sistema e restrições obrigatórias;
2. decisão explícita vigente do Operador;
3. constituição/instruções/governança oficial vigente do projeto;
4. decisão do Coordenador dentro de autoridade transversal;
5. decisão do Gestor dentro de autoridade de domínio;
6. esta Skill como governança global subsidiária;
7. preferência do Executor.

Documentos especializados vigentes devem ser respeitados conforme a governança do projeto. Não misturar versões conflitantes silenciosamente.

## 14. Portabilidade

A Skill não deve presumir Work, Codex, Drive, GitHub ou qualquer fornecedor específico. Deve mapear papéis abstratos às capacidades disponíveis na plataforma.

Se a plataforma não possuir agentes separados, representar os papéis com contextos, sessões ou procedimentos equivalentes.

## 15. Critérios de acionamento

Considerar a Skill relevante quando houver:
- organização de trabalho entre múltiplas IAs/agentes;
- dúvida sobre quem decide ou executa;
- conflito ou dependência entre domínios;
- escolha de executor;
- definição/revisão de gate;
- governança de fontes de verdade;
- ação sensível ou potencialmente fora do escopo;
- decisão sobre continuidade, Handoff ou sucessão;
- risco de expansão de autoridade, duplicação ou burocracia.

Pode atuar silenciosamente antes de delegações formais. Não deve ser acionada para conversa trivial sem implicação de workflow/governança.

## 16. Compatibilidade e manutenção

A versão 2.0.0 desta Skill corresponde à Arquitetura de Trabalho Agentiva v2.0.

Mudanças estruturais em papéis, autoridade, gates, handoffs, fontes de verdade ou critérios de parada exigem revisão conjunta da arquitetura e desta Skill.

GitHub é a fonte versionada oficial da Skill. Uma instalação nativa em plataforma é uma implementação separada e deve ser verificada após atualização da fonte.
