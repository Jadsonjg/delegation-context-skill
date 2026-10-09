# Delegation Context Skill

Skill reutilizável para estruturar delegações entre uma IA coordenadora e um executor, separando contexto executivo, recursos necessários, nível de raciocínio recomendado e briefing operacional.

## O que é

A **Delegation Context Skill** foi criada para melhorar a passagem de tarefas entre uma IA que pensa, coordena ou decide e outra IA, agente, Work, ferramenta ou executor que realizará a tarefa.

Ela adiciona uma camada curta e executiva antes do prompt operacional, chamada **Informações adicionais**.

A lógica central é:

> **Informações adicionais = o operador entende a delegação.**  
> **Comando / Briefing = o executor entende como executar.**

Isso evita dois problemas comuns:

1. o operador receber apenas um bloco técnico longo sem entender o que será feito, quais recursos serão necessários ou qual resultado deve esperar;
2. o executor receber apenas um resumo superficial, sem contexto suficiente para executar corretamente.

## Onde se aplica

Use esta skill em fluxos como:

- chat gestor → agente especializado;
- chat coordenador → Work;
- IA planejadora → IA executora;
- humano → agente de execução;
- sistemas multiagente;
- IA → ferramenta de automação;
- IA → navegador/computer use;
- IA → agente de pesquisa;
- IA → agente de desenvolvimento;
- IA → agente de documentos;
- IA → agente financeiro, jurídico, comercial ou operacional;
- qualquer cenário em que uma entidade **decide como a tarefa deve ser conduzida** e outra **executa**.

Ela é especialmente útil quando a tarefa exige arquivos, conectores, permissões, ferramentas específicas, nível de raciocínio adequado ou possui risco relevante de retrabalho se a delegação estiver incompleta.

## Quando não usar

A skill não precisa ser aplicada a toda resposta.

Ela pode ser dispensada quando:

- não existe delegação;
- o próprio chat fará a tarefa imediatamente;
- a tarefa é simples e não há outro executor;
- o usuário pediu apenas uma resposta, opinião ou explicação direta.

## Estrutura padrão

Antes do prompt destinado ao executor, o coordenador apresenta:

### Informações adicionais

Campos centrais:

- **Ação:** resumo executivo do que será feito.
- **Resultado esperado:** o que deve existir, estar concluído, configurado, analisado ou devolvido ao final.

Campos opcionais, somente quando agregarem valor real:

- **Modelo / raciocínio recomendado**
- **Ferramentas / conectores**
- **Arquivos / documentos / pastas**
- **Dependências / pré-requisitos**
- **Permissões / acessos / ação humana**
- **Limitações conhecidas**
- **Cuidados para evitar execução incorreta**

Se nenhum desses campos adicionais for necessário:

> **Informações adicionais: nenhuma.**

Depois vem:

### Comando / Briefing

Aqui ficam as instruções completas destinadas ao executor: contexto, critérios, passos, restrições, validações, entregáveis e regras operacionais.

## Princípio de não duplicação

**Informações adicionais não são um segundo briefing.**

Elas existem para ajudar o operador a entender a delegação. O detalhamento de execução pertence ao briefing.

Inclua um campo apenas se ele mudar a forma como o operador deve interpretar, preparar, autorizar ou executar a delegação.

## Interrupção antes da delegação

A skill também inclui uma regra de qualidade: se o coordenador identificar premissa ruim, dado insuficiente, ferramenta inadequada, dependência não resolvida, risco relevante, conflito de instruções ou alta probabilidade de retrabalho, ele deve **parar antes de produzir o briefing final**.

Fluxo recomendado:

1. explicar objetivamente o problema;
2. indicar por que continuar seria inadequado;
3. propor correção ou alternativa;
4. solicitar decisão humana quando necessário;
5. somente então gerar a delegação corrigida.

A skill não deve transformar uma direção ruim em um briefing bem formatado.

## Modelo e nível de raciocínio

O campo de modelo/raciocínio é **opcional**.

Use quando a escolha alterar materialmente:

- qualidade;
- confiabilidade;
- custo;
- tempo;
- risco de erro;
- capacidade de planejamento.

É especialmente relevante para estratégia, auditoria, arquitetura de informação, análise financeira complexa, planejamento técnico e tarefas com alto custo de retrabalho.

### Portabilidade entre plataformas

Nem toda IA permite alterar tecnicamente o nível de raciocínio.

A skill distingue:

**Modo informativo**  
`Raciocínio recomendado: alto.`

Use quando o coordenador só puder recomendar a configuração ao operador.

**Modo acionável**  
`Defina o esforço de raciocínio como alto antes da execução.`

Use apenas quando a plataforma, API ou ferramenta realmente oferecer um mecanismo para alterar essa configuração.

**Nunca afirme que alterou modelo, modo ou nível de raciocínio se a plataforma não oferecer controle real para isso.**

Atalhos de interface, comandos iniciados por `/` e nomes específicos de modos não devem ser tratados como universais. Eles podem variar entre plataformas, planos e versões.

## Ideia de uso

A skill foi pensada para reduzir perda de contexto, retrabalho e delegações incompletas.

Ela cria uma interface clara entre três papéis:

1. **Coordenador** — pensa, decide, organiza e valida a direção.
2. **Operador** — entende o que será delegado e autoriza ou fornece recursos quando necessário.
3. **Executor** — recebe um briefing completo e realiza a tarefa.

O objetivo é tornar a passagem entre esses papéis previsível e reutilizável, independentemente da IA ou ferramenta utilizada.

## Arquivos do repositório

- `README.md` — conceito, contexto de uso e governança da skill.
- `prompt-mestre.md` — prompt completo para instalar a skill em outro chat ou IA.
- `instalador-curto.md` — instrução curta para ambientes que conseguem acessar este repositório diretamente.
- `exemplos.md` — exemplos práticos de aplicação.
- `CHANGELOG.md` — histórico de versões.

## Fonte oficial

Este repositório deve ser tratado como a fonte oficial da skill.

Cópias em outros locais podem ser usadas para consulta, mas alterações permanentes devem ser consolidadas primeiro aqui e registradas no histórico de versões.
