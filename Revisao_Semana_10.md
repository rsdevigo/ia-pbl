# Revisão — Semana 10

**Tema:** Minimax e Busca Adversarial
**Módulo:** 4 — Como derrotar um adversário inteligente? (parte 1)
**Documentos revisados:** Plano de Aula (Semana 10) e Slides (Semana 10)
**Tutorial:** não existe tutorial nesta disciplina (nenhuma semana possui esse artefato até o momento); item 3 dos critérios de coerência é, portanto, não aplicável.
**Referência de verdade:** Apostila — Parte V, Capítulo 11, seções 11.1 a 11.3 (com 11.3.1 a 11.3.3) e 11.6 (jogo da velha); CLAUDE.md — seção "Micro Games — Exemplos de Implementação" (Módulo 4: Conecta 4 Reduzido); Cronograma (Semana 10 e nota de fonte); Plano de Aula da Semana 11 (para verificar a fronteira de conteúdo).

---

## Resumo Geral

A Semana 10 abre a Unidade IV com um Plano de Aula tecnicamente correto e bem ancorado na Apostila: a sequência conceitual (ambientes cooperativo/reativo/competitivo → soma zero → árvore de jogo → profundidade/ramificação → utilidade × avaliação → algoritmo Minimax → jogo da velha → horizonte) reproduz fielmente a ordem das seções 11.1 a 11.3 e 11.6, os dois encontros fecham exatamente em 90 minutos, e a fronteira com a Semana 11 (nada de 11.3.4, 11.4 ou 11.5 antecipado) está corretamente delimitada e reafirmada pelo próprio Plano da Semana 11. Os Slides seguem a mesma ordem do Plano com boa fidelidade de vocabulário, sem vazamento de notas de produção no PDF exportado (21 páginas, verificado integralmente). O ponto que impede uma avaliação mais alta é de escopo do Micro Game: a Semana 10 inicia o Board Game AI inteiramente sobre o jogo da velha e nunca menciona "Conecta 4 Reduzido" — o exemplo fixado pelo CLAUDE.md para o Módulo 4 — nem mesmo como destino declarado; e um slide introduz uma tabela de mapeamento técnica↔ambiente que não está sustentada pela Apostila e pode plantar uma concepção equivocada exatamente no objetivo que deveria testar o oposto.

---

## Pontos Fortes

- **Sequência didática fiel à Apostila.** O Plano segue exatamente a ordem 11.1 (problema e tipos de ambiente) → 11.2 (soma zero, árvore de jogo, profundidade/ramificação, utilidade/avaliação) → 11.3–11.3.3 (algoritmo, camadas, profundidade, horizonte) → 11.6 (jogo da velha), sem pular nem antecipar nada, e sinaliza explicitamente o que fica reservado para a Semana 11 (11.3.4 e 11.4) e o que nunca deve ser apresentado (11.5, MCTS).
- **Exemplo numérico idêntico ao da Apostila.** O traçado A→(3,5), B→(6,2), C→(1,8), com raiz = 3 e jogada A escolhida, reproduz exatamente o exemplo da seção 11.3, inclusive o destaque de que a folha 8 (maior valor da árvore) é inalcançável — o mesmo exemplo será retomado com poda alfa-beta na Semana 11, dando continuidade pedagógica real entre as duas semanas.
- **Tempos batendo com exatidão.** Encontro 1 soma 5+15+20+10+20+10+5+5 = 90 minutos; Encontro 2 soma 10+10+45+15+10 = 90 minutos. Nenhuma etapa "sobra" ou "falta" tempo no papel.
- **Justificativa de ferramentas correta e consistente com o padrão do Módulo 3.** A ausência de solução oficial da Unity para Minimax é corretamente situada (seção 11.9) e comparada explicitamente ao precedente já estabelecido com Utility AI, evitando que a implementação própria pareça uma workaround improvisada.
- **PDF exportado limpo.** Ao contrário do problema já corrigido na Semana 8, nenhuma nota de produção ("FIGURA A PRODUZIR", instruções de diagrama) vaza para o PDF final — as 21 páginas foram inspecionadas integralmente.
- **Fechamento de semana com ponte clara.** Tanto o Plano quanto o slide final de preparação antecipam corretamente o tema, as quatro entregas e o encerramento do Módulo 4 na Semana 11, e o Plano da Semana 11 de fato retoma o mesmo exemplo numérico e a mesma implementação — a continuidade entre as duas semanas é sólida.

---

## Problemas Encontrados

**Problema 1**
- **Documento:** Plano de Aula (seções "Micro Game", "Preparação do Professor" e "Preparação para a Próxima Semana")
- **Local:** Descrição do Micro Game Board Game AI e do cenário previsto para a Semana 11
- **Descrição:** O CLAUDE.md fixa, para o Módulo 4, o exemplo "Board Game AI — Conecta 4 Reduzido: grade menor que o padrão; a IA avalia jogadas futuras" como o Micro Game a ser usado em todo material de demonstração, exatamente como o Módulo 1 usa "Criatura de Ambiente" e o Módulo 3 usa "Seleção de Alvo". A Semana 10 constrói o Board Game AI inteiramente sobre o jogo da velha (o que é pedagogicamente correto como primeiro exemplo, pois a própria Apostila o usa como caso introdutório na seção 11.6) — mas em nenhum momento o Plano indica que o destino final do Micro Game é Conecta 4 Reduzido. A seção "Preparação para a Próxima Semana" fala apenas em "uma variante simplificada de damas ou um jogo de tabuleiro com árvore maior", sem citar Connect Four. Ao ler apenas os materiais da Semana 10, um professor não saberia que o Micro Game do módulo deveria convergir para Conecta 4 Reduzido.
- **Prioridade:** Alta

**Problema 2**
- **Documento:** Plano de Aula da Semana 11 (verificado por continuidade, pois herda diretamente o escopo aberto pela Semana 10)
- **Local:** Seção "Micro Game" e "Preparação do Professor" (cena Unity)
- **Descrição:** Mesmo na semana de consolidação do módulo, o Plano da Semana 11 trata "damas simplificada" e "Connect Four em grade reduzida" como alternativas equivalentes ("por exemplo"), nunca comprometendo-se com Conecta 4 Reduzido como exemplo fixo. Como a Semana 10 é o ponto de partida da cadeia, a ambiguidade nasce aqui: nada nos materiais da Semana 10 orienta o professor a preservar a opção certa entre as citadas na Semana 11.
- **Prioridade:** Alta

**Problema 3**
- **Documento:** Slides (Semana 10), slide "Três tipos de ambiente" (página 6)
- **Local:** Tabela com colunas Ambiente / Característica / Técnicas já vistas
- **Descrição:** A tabela atribui FSM e BT especificamente ao ambiente "Cooperativo" e NavMesh/Utility AI ao ambiente "Reativo". A seção 11.1 da Apostila não faz essa atribuição: ela situa as técnicas dos Módulos 1 a 3 coletivamente no território **reativo** (um inimigo que patrulha e ataque via FSM/BT é hostil, mas não estratégico — exatamente o exemplo de F.E.A.R./Halo dado pela Apostila), e reserva "cooperativo" para um caso distinto (um aliado controlado por IA, como Ellie em The Last of Us), que não corresponde a nenhum Micro Game construído nesta disciplina. O próprio Plano de Aula da Semana 10 usa a formulação mais correta e mais próxima da Apostila ("situando as técnicas dos Módulos 1 a 3 no território reativo/cooperativo"), sem comprometer uma técnica a uma categoria única. A tabela do slide, ao fixar uma correspondência 1:1 que a Apostila não sustenta, corre o risco de ensinar aos estudantes que "FSM/BT = cooperativo" e "NavMesh/Utility AI = reativo" são fatos da técnica, quando na verdade a categoria depende da relação entre o NPC e o agente, não do algoritmo usado — indo direto contra o Objetivo de Aprendizagem 2 ("diferenciar ambientes... situando corretamente exemplos de jogos", não exemplos de técnicas).
- **Prioridade:** Alta

**Problema 4 (descartado após verificação)**
- Investigação adicional confirmou que o slide "✏ EXERCÍCIO — Erro comum" com a classe `exercise` é o **padrão fixo** usado como penúltimo slide em todas as semanas do curso (verificado nas Semanas 1–9, 11–16), sempre reservado para o recapitulativo final de erro comum antes do resumo. Não é uma inconsistência da Semana 10; é o template do curso. Item removido da lista de problemas.

**Problema 5**
- **Documento:** Cronograma (verificado por referência cruzada, não é material da Semana 10 propriamente)
- **Local:** Linha da Semana 11 na tabela "Ancoragem no Calendário Acadêmico" / seção Unidade IV
- **Descrição:** O Cronograma indica a Apostila da Semana 11 como "Parte VI, Cap. 13 — Heurísticas e Algoritmos Genéticos (parte de heurísticas de avaliação)". No entanto, tanto o Plano da Semana 10 (que reserva 11.3.4 e 11.4 explicitamente para a Semana 11) quanto o próprio Plano da Semana 11 (que cita 11.3.4 e 11.4 como conteúdo central, e a seção 13.1 apenas como reforço terminológico secundário) deixam claro que o conteúdo de heurísticas de avaliação e poda alfa-beta pertence ao Capítulo 11, não ao Capítulo 13. A referência do Cronograma está imprecisa e pode induzir um professor que consulte só essa tabela a preparar a leitura errada. Não é um problema da Semana 10 em si, mas vale registrar para correção antes de tratar a Semana 11 como definitivamente encerrada.
- **Prioridade:** Baixa

---

## Ajustes Realizados

- **Problema 1 e 2 (Micro Game).** O Plano da Semana 10 agora declara explicitamente, na seção "Micro Game" e em "Preparação do Professor"/"Preparação para a Próxima Semana", que o jogo da velha é apenas o exemplo introdutório do algoritmo (seção 11.6 da Apostila) e que o Board Game AI converge para **Conecta 4 Reduzido**, o exemplo fixado pelo CLAUDE.md para o Módulo 4. O Plano da Semana 11 foi ajustado nos mesmos pontos (Preparação do Professor, Encontro 1, Encontro 2, Micro Game, Atividade de Laboratório e Objetivo 9) para se comprometer com Conecta 4 Reduzido em vez de tratá-lo como uma alternativa equivalente a "damas simplificada".
- **Problema 3 (tabela de ambientes).** A tabela "Três tipos de ambiente" do slide (página 6) foi reformulada: a coluna "Técnicas já vistas" foi substituída por "Exemplo de jogo", usando os próprios exemplos da Apostila (aliado cooperativo à la Ellie em *The Last of Us*; inimigo reativo de *Halo*/*F.E.A.R.*; xadrez/damas/jogo da velha como competitivo), e os Módulos 1–3 passam a ser citados coletivamente no território reativo, sem atribuir uma técnica específica a uma categoria fixa.
- **Problema 4 (descartado).** Verificação adicional mostrou que o slide de classe `exercise` com o recapitulativo de "Erro comum" é o padrão fixo usado em todas as semanas do curso — não era, de fato, uma inconsistência da Semana 10.
- **Problema 5 (Cronograma).** Não alterado nesta rodada — está fora do escopo dos dois documentos revisados (Plano de Aula e Slides da Semana 10) e não foi solicitado.

**Observação técnica:** não foi possível regenerar o PDF e o PPTX da Semana 10 a partir do `slides.md` atualizado neste ambiente, pois o Marp CLI depende de um navegador Chromium que o sandbox não conseguiu baixar (bloqueio de rede no download do binário). O `slides.md` — fonte de verdade do deck — já está corrigido; o PDF/PPTX serão regenerados automaticamente pelo pipeline do GitHub Actions (`.github/workflows/marp-slides.yml`) no próximo push para `main`, ou podem ser gerados manualmente com `marp slides.md --pdf --pptx` em uma máquina com Chromium disponível.

---

## Parecer Final

**Pronta com pequenos ajustes — ajustes já aplicados nesta revisão.**

**Justificativa:** A Semana 10 tinha fundamentos sólidos desde a primeira leitura — sequência fiel às seções 11.1 a 11.3 e 11.6, tempos batendo exatamente com os 90 minutos de cada encontro, exemplo numérico idêntico ao da Apostila e reaproveitado com continuidade real na Semana 11, justificativa de ferramentas correta, e nenhuma repetição do vazamento de notas de produção corrigido desde a Semana 8. Os dois problemas reais de prioridade Alta (escopo do Micro Game não declarado como Conecta 4 Reduzido; tabela de ambientes no slide sem lastro na Apostila) eram ajustes textuais localizados, não uma reestruturação de conteúdo ou de sequência, e já foram corrigidos no Plano de Aula (Semanas 10 e 11) e no `slides.md` da Semana 10. Falta apenas a regeneração do PDF/PPTX pelo pipeline de build, que não pôde ser executada neste ambiente por indisponibilidade de Chromium.
