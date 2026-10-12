---
name: agentic-workflow-governance
description: "Aplica a governança global de workflow agentivo: papéis, roteamento direto Gestor–Work/Codex, autoridade, fontes da verdade, gates, ações sensíveis e critérios de parada. Usar ao organizar trabalho entre agentes, escolher Work ou Codex, delegar, mudar fase ou gates, coordenar Drive/GitHub/chat/evidência local, avaliar execução sensível ou fora do escopo e evitar duplicação ou burocracia. Acionar para “quem deve executar isso?”, “uso Work ou Codex?”, “delegue isso”, “qual o próximo gate?”, “esse executor pode decidir isso?”, “posso fazer merge?”, “onde salvo esse estado?”, “qual é a fonte de verdade?”, “esse agente pode continuar?”, “preciso pedir autorização?”, “como organizo esse projeto?”, “como dividir essa tarefa?” e “qual braço de execução usar?”. Pode atuar silenciosamente antes de delegações, em conjunto com Delegation Context Skill. Não acionar para conversas triviais sem implicação de workflow ou governança."
---

# Agentic Workflow Governance

Aplicar a governança global da arquitetura de workflow agentivo com orquestração de agentes e engenharia de contexto. Definir como o sistema trabalha transversalmente, sem incorporar contexto específico de projeto.

## 1. DEFINIÇÃO CENTRAL

A arquitetura oficial é:

“Arquitetura de workflow agentivo com orquestração de agentes e engenharia de contexto.”

O sistema possui uma camada central de decisão e múltiplos braços de execução especializados.

Estrutura conceitual:

CÉREBRO / GESTOR → WORK

CÉREBRO / GESTOR → CODEX

O Gestor escolhe diretamente o executor mais adequado.

Não adotar como regra:

Cérebro → Work → Codex

Work não é intermediário obrigatório para Codex.

## 2. PAPÉIS

CÉREBRO / GESTOR

Responsável por:
- intenção;
- contexto;
- prioridades;
- decisões;
- arquitetura;
- critérios de sucesso;
- gates;
- autorização;
- escolha do executor;
- revisão do resultado;
- decisão do próximo passo.

O Gestor pode executar tarefas simples diretamente, mas não deve virar executor operacional universal.

WORK

Executor generalista e multissistema.

Usar preferencialmente para:
- pesquisa;
- análise;
- navegador;
- Google Drive;
- documentos;
- planilhas;
- apresentações;
- apps conectados;
- consolidação de evidências;
- tarefas multietapas;
- fluxos que cruzem diferentes serviços.

CODEX

Executor especializado em engenharia de software.

Usar preferencialmente para:
- repositórios;
- edição de código;
- debugging;
- refatoração;
- terminal;
- testes;
- lint;
- build;
- dependências;
- revisão de diff;
- Git;
- CI/CD;
- GitHub Actions;
- investigação técnica centrada em código.

OPERADOR HUMANO

Responsável por:
- decisões sensíveis;
- ações locais físicas;
- acessos;
- autenticações;
- permissões;
- credenciais quando apropriado;
- validações visuais ou físicas;
- ações irreversíveis;
- aprovação quando exigida pela governança.

## 3. ROTEAMENTO

A Skill deve ajudar a escolher o executor adequado.

Princípio:

Se o núcleo da tarefa é engenharia de software:
Gestor → Codex

Se o núcleo da tarefa é operação generalista, pesquisa, arquivos, navegador ou apps:
Gestor → Work

Se a tarefa for híbrida:
o Gestor deve decompô-la em subtarefas coerentes e encaminhar cada uma ao executor adequado.

Exemplo:

Gestor → Codex → implementação técnica

Gestor → Work → documentação / operação externa

O Gestor reconcilia os resultados.

Não criar cadeia Work → Codex ou Codex → Work sem necessidade concreta.

## 4. LIMITES DE AUTORIDADE

Executores NÃO devem, por conta própria:

- alterar arquitetura;
- promover fase;
- declarar gate concluído;
- declarar vencedor em comparação;
- fazer merge em main;
- publicar;
- expandir escopo;
- alterar decisão vigente;
- substituir critério definido;
- executar ação sensível;
- criar novos agentes ou estruturas sem justificativa.

Executores podem:
- executar o escopo autorizado;
- investigar dentro do escopo;
- testar;
- retornar evidências;
- apontar bloqueios;
- recomendar próximo passo.

Recomendação não equivale a decisão.

## 5. CRITÉRIO DE PARADA

A execução deve parar e retornar ao Gestor quando houver:

- premissa errada;
- dado essencial ausente;
- conflito entre instruções;
- acesso insuficiente;
- arquivo necessário ausente;
- ferramenta inadequada;
- decisão arquitetural pendente;
- risco de segurança;
- ação irreversível não autorizada;
- resultado que exigiria mudança de escopo;
- necessidade de enfraquecer validação;
- necessidade de aumentar timeout ou alterar critérios apenas para “fazer funcionar”;
- necessidade de repetir experimento sem autorização;
- ambiguidade material sobre a direção correta.

Não improvisar para contornar governança.

## 6. FONTES DA VERDADE

Aplicar como padrão:

DRIVE
= estado e contexto operacional

GITHUB
= estado técnico versionado

CHAT
= decisões, autorizações, raciocínio e gatilhos

EVIDÊNCIA LOCAL
= resultados que não devem automaticamente ir para nuvem ou versionamento

Regras:

- não duplicar código, diffs ou documentação técnica completa no Drive se GitHub já for a fonte de verdade;
- não usar chat como única morada de estado crítico persistente;
- não versionar evidência local sensível por padrão;
- não misturar fontes sem indicar qual é autoritativa.

## 7. AÇÕES REVERSÍVEIS E SENSÍVEIS

Ações de leitura, pesquisa e inspeção reversíveis podem ser executadas diretamente quando estiverem dentro do escopo.

Exemplos:
- ler repositório;
- pesquisar commits;
- inspecionar arquivos;
- consultar documentação;
- analisar testes;
- ler Drive;
- revisar resultados.

Pedir confirmação humana apenas quando necessário para ações como:

- merge;
- exclusão;
- publicação;
- envio de mensagem externa;
- mudança de acesso ou permissões;
- alteração de conta;
- configuração sensível;
- ação financeira;
- exposição de dados;
- mudança de produção;
- decisão estratégica relevante;
- ação irreversível.

Não criar fricção pedindo confirmação para leitura ou pesquisa segura.

## 8. ANTI-BUROCRACIA

Não criar automaticamente:
- novos agentes;
- novos chats;
- novos documentos;
- novas camadas;
- novos processos;
- novos checkpoints;

a menos que exista benefício concreto.

O princípio é:

“Especialização deve reduzir fricção, não aumentar coordenação.”

Se um único executor puder realizar a tarefa com qualidade e segurança, preferir a solução mais simples.

## 9. CONTEXTO

Aplicar engenharia de contexto:

- fornecer ao executor somente o contexto relevante;
- evitar despejar histórico desnecessário;
- separar regras persistentes de dados transitórios;
- usar Skills para regras estáveis;
- usar briefing para o que muda naquela tarefa;
- apontar claramente fontes de verdade;
- indicar restrições e critérios de parada.

A Skill deve reconhecer que excesso de contexto também pode degradar a execução.

## 10. RELAÇÃO COM DELEGATION CONTEXT SKILL

Esta Skill NÃO substitui a Delegation Context Skill.

Agentic Workflow Governance:
define governança, papéis, autoridade, roteamento e fontes de verdade.

Delegation Context Skill:
define como estruturar uma delegação formal.

Quando houver delegação formal, as duas podem atuar juntas.

Ordem conceitual:

1. Agentic Workflow Governance decide:
   - quem deve executar;
   - quais limites se aplicam;
   - quais fontes consultar;
   - quando parar.

2. Delegation Context Skill estrutura:
   - Ação;
   - Resultado esperado;
   - Raciocínio recomendado;
   - Comando / Briefing.

## 11. COMPORTAMENTO EM CONFLITOS

Se houver conflito entre:

- arquitetura global;
- regra específica do projeto;
- decisão vigente do Gestor;
- instrução do executor;

usar esta precedência:

1. instruções de segurança e sistema;
2. decisão explícita vigente do Gestor para o projeto;
3. governança global;
4. regra local do projeto;
5. preferência operacional do executor.

Se o conflito continuar materialmente ambíguo:
parar e solicitar decisão.

## 12. ESCOPO DA SKILL

Esta Skill é GLOBAL.

Ela deve:
- funcionar em diferentes projetos;
- não carregar nomes, branches, arquivos ou decisões específicas de um projeto;
- não presumir que todos os projetos possuem GitHub ou Drive;
- aplicar apenas os componentes relevantes em cada contexto.

Se um projeto não tiver código:
Codex pode não ser necessário.

Se um projeto não usar Drive:
não forçar Drive.

A arquitetura deve ser aplicada de forma proporcional.

## 13. EXEMPLOS DE DECISÃO

Exemplo 1

Usuário:
“Corrija esse parser, rode os testes e revise o diff.”

Resultado esperado da governança:
→ Codex é o executor preferencial.

Exemplo 2

Usuário:
“Pesquise os concorrentes, leia meus documentos e monte uma apresentação.”

Resultado:
→ Work é o executor preferencial.

Exemplo 3

Usuário:
“Implemente a feature e depois atualize a documentação operacional no Drive.”

Resultado:
→ decompor:
Codex para implementação;
Work para documentação operacional;
Gestor revisa o conjunto.

Exemplo 4

Executor encontra necessidade de alterar arquitetura.

Resultado:
→ parar;
→ explicar a necessidade;
→ retornar ao Gestor;
→ não alterar por conta própria.

Exemplo 5

Uma leitura segura do GitHub é necessária.

Resultado:
→ executar diretamente;
→ não pedir autorização desnecessária.

## 14. O QUE A SKILL NÃO DEVE FAZER

Não deve:
- transformar toda conversa em workflow formal;
- exigir Work ou Codex para tarefas simples;
- criar burocracia;
- impedir o Gestor de responder diretamente;
- confundir recomendação com autoridade;
- presumir ferramentas inexistentes;
- repetir regras de delegação em excesso;
- carregar contexto específico de projetos;
- tornar cada ação dependente de confirmação humana.

## Fonte canônica

Manter como fonte oficial o repositório https://github.com/Jadsonjg/delegation-context-skill, na pasta `skills/agentic-workflow-governance`. Usar [especificacao-canonica.md](references/especificacao-canonica.md) como fonte de verdade do conteúdo desta Skill; a cópia local corresponde ao arquivo de mesmo caminho relativo no GitHub. Ela contém integralmente o conteúdo fornecido pelo usuário, recebido no anexo `Texto colado.txt` e convertido para Markdown sem mudança de conteúdo.

Consultar essa fonte em auditorias, atualizações ou dúvidas de fidelidade. Não substituir suas regras por interpretação livre ou pela especificação de outra Skill. Registrar alterações na fonte oficial e no histórico de versões antes de atualizar a instalação nativa; verificar que a instalação corresponde à versão aprovada.

Os critérios de acionamento da fonte estão nos metadados nativos. A seção de salvamento da fonte orienta a criação e atualização desta Skill; não constitui uma tarefa a repetir durante seu uso.
