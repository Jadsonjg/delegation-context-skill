# Exemplos — Delegation Context Skill

## Exemplo 1 — Pesquisa profunda

### Informações adicionais

**Ação:** delegar uma pesquisa comparativa sobre três fornecedores de software.

**Resultado esperado:** relatório comparativo com critérios, evidências, riscos, custos e recomendação final.

**Modelo / raciocínio recomendado:** alto, porque a tarefa exige síntese de múltiplas fontes e comparação de trade-offs.

**Ferramentas / conectores:** acesso à web.

### Comando / Briefing

Pesquise os fornecedores A, B e C. Compare preço, segurança, integrações, suporte, limitações e adequação ao cenário descrito abaixo...

---

## Exemplo 2 — Produção de documento

### Informações adicionais

**Ação:** transformar conteúdo aprovado em documento final.

**Resultado esperado:** PDF pronto para apresentação ao cliente.

**Arquivos / documentos:** usar o modelo visual aprovado e o texto final anexado.

**Cuidados:** não alterar o conteúdo aprovado; mudanças devem ser apenas de diagramação.

### Comando / Briefing

Crie o documento final a partir dos arquivos anexos...

---

## Exemplo 3 — Tarefa simples

**Informações adicionais: nenhuma.**

### Comando / Briefing

Converta a lista abaixo para CSV com as colunas Nome, E-mail e Telefone...

---

## Exemplo 4 — Interrupção antes da delegação

O coordenador identifica que o executor precisaria acessar uma planilha ainda não fornecida.

Resposta correta:

> Não vou gerar o briefing final ainda porque a planilha é necessária para a execução e sua ausência obrigaria o executor a inferir dados. Envie o arquivo ou autorize o uso da fonte alternativa X. Depois disso preparo a delegação completa.

A skill impede que um prompt incompleto seja enviado apenas para seguir adiante.

---

## Exemplo 5 — Raciocínio recomendado, mas não configurável

### Informações adicionais

**Ação:** revisar arquitetura de um processo complexo.

**Resultado esperado:** proposta de arquitetura com riscos, dependências e alternativas.

**Modelo / raciocínio recomendado:** alto. A plataforma atual não permite que eu altere tecnicamente esse nível; selecione-o manualmente antes da execução, se disponível.

### Comando / Briefing

Revise a arquitetura descrita abaixo...

---

## Exemplo 6 — Raciocínio configurável via sistema/API

### Informações adicionais

**Ação:** executar análise de cenário.

**Resultado esperado:** comparação quantitativa e qualitativa entre três alternativas.

**Modelo / raciocínio recomendado:** alto.

**Dependências / pré-requisitos:** configurar o parâmetro nativo de esforço de raciocínio para nível alto antes da chamada.

### Comando / Briefing

Analise os três cenários...
