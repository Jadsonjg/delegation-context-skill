# Instalador curto — Delegation Context Skill

Use esta instrução quando a IA ou o chat tiver acesso à web ou ao GitHub e puder consultar este repositório diretamente.

---

Adote a **Delegation Context Skill** disponível neste repositório.

Fonte oficial:

- Repositório: `Jadsonjg/delegation-context-skill`
- Arquivo principal: `prompt-mestre.md`

Leia integralmente `prompt-mestre.md` antes de aplicar a skill.

Depois de carregá-lo, passe a usá-lo sempre que você estiver preparando uma tarefa que será executada por outro chat, agente, Work, ferramenta, automação, sistema multiagente ou executor humano.

Preserve especialmente estas regras:

1. apresentar **Informações adicionais** antes do **Comando / Briefing**;
2. usar **Ação** e **Resultado esperado** como campos centrais;
3. incluir modelo/raciocínio, ferramentas, arquivos, dependências, permissões, limitações e cuidados somente quando forem realmente necessários;
4. não duplicar o briefing dentro de Informações adicionais;
5. interromper antes da delegação quando houver premissa inadequada, informação insuficiente, ferramenta errada, dependência não resolvida, risco relevante ou alta probabilidade de retrabalho;
6. recomendar nível de raciocínio somente quando isso afetar materialmente a qualidade da execução;
7. nunca afirmar que alterou modelo ou esforço de raciocínio se a plataforma não oferecer um controle técnico real para isso.

Se você não conseguir acessar o repositório ou ler `prompt-mestre.md`, informe isso claramente e solicite que o conteúdo do Prompt Mestre seja fornecido no chat. Não tente reconstruir a skill parcialmente por suposição.
