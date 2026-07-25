# Revisão Crítica da Disciplina

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** Apostila (rsdevigo/apostila-ia), CLAUDE.md, Plano de Ensino, Cronograma, Rubrica de Avaliação, Critérios de Notas, Formulários de Avaliação, Modelos de Entrega do Aluno, Manual/Guia do Professor, 17 Planos de Aula, 17 conjuntos de Slides (fontes `.md`, PDFs e PPTX gerados), README, `_sidebar.md`, `index.html` e workflow de geração de slides.
**Perspectiva:** revisão simultânea como professor universitário de IA para Jogos, designer instrucional, Game AI Engineer, especialista em Unity, revisor pedagógico e revisor técnico.
**Data:** julho de 2026

---

## Resumo Executivo

Esta é uma documentação didática de qualidade acima da média para um curso de graduação tecnológica. A disciplina foi projetada como sistema, não como coleção de arquivos: a sequência didática obrigatória (problema → fundamentos → aplicações → ferramentas → Micro Game) é reconhecível em todos os 17 planos de aula e em todos os 17 decks; a terminologia é estável entre documentos; a estrutura interna dos planos é idêntica de ponta a ponta; e as citações à Apostila são precisas — a verificação automática de **todas** as referências de seção feitas nos planos, slides, Cronograma e Manual do Professor contra o sumário real da Apostila não encontrou **nenhuma** citação inexistente. Isso é raro e merece registro.

O problema não está na qualidade individual dos artefatos, e sim em **três costuras que não fecharam**.

A primeira e mais séria é a **costura da avaliação**. Os Critérios de Notas definem quatro instrumentos por módulo, sendo o Micro Game 50% da nota do módulo — mas o Cronograma, cinco dos seis planos de encerramento de módulo e os slides correspondentes anunciam consistentemente "**três** entregas" por módulo, omitindo justamente o Micro Game. Além disso, os critérios da Rubrica atribuídos a cada instrumento divergem entre a Rubrica (§5), os Formulários de Avaliação e a tabela de pesos dos Critérios de Notas (§4). Na prática, um professor que siga os planos de aula e os formulários produzirá notas diferentes das previstas na fórmula oficial.

A segunda é a **costura com a Apostila**. Em dois pontos concretos os documentos operacionais contradizem a fonte da verdade: (a) o Cronograma, o Manual do Professor e o plano da Semana 9 afirmam que Utility AI "não possui capítulo dedicado" e mandam buscar bibliografia externa, quando a Apostila trata o tema na §6.7, sintetiza-o na §6.8 e o indexa no Glossário e no Apêndice C — e o plano da Semana 4 **reconhece** a existência da §6.7, contradizendo o plano da Semana 9; (b) a Semana 9 escolhe *F.E.A.R.* como caso de Engenharia Reversa de mapas de influência e Utility AI, enquanto a Apostila (§15.2) documenta *F.E.A.R.* como caso canônico de **GOAP**, marcado explicitamente como `[Documentado]` — e GOAP não é estudado em nenhum momento do semestre. Isso põe o exercício em rota de colisão com a própria disciplina metodológica de separar fato documentado de inferência que a disciplina ensina.

A terceira é a **costura entre planejamento e sala de aula**. Três encontros somam 100 minutos em blocos de 90 (Semanas 8, 9 e 10 — verificado somando as durações das tabelas). O checkpoint da Semana 8 (10% da nota) tem 35 minutos para todos os grupos, e a apresentação final da Semana 17 (20% da nota, oito critérios, seis Micro Games por grupo) tem 50 minutos para toda a turma. Nenhum documento fixa tamanho de turma, número de grupos ou tempo por grupo. E o material entregue tem um defeito de produção verificável: as instruções internas de produção de figuras (`[!FIGURA] … Como produzir … Krita`) são **renderizadas dentro dos PDFs e PPTX** distribuídos — confirmado na página 13 de `semana_2_slides.pdf`, e presente em todos os 17 decks.

Nenhum desses problemas é estrutural. São correções pontuais, de escopo delimitado, em documentos que já estão bem escritos. Com uma rodada de acertos, a disciplina fica pronta para aplicação.

---

## Pontos Fortes

**1. Coerência filosófica real, não declarada.** A regra "nunca apresentar ferramenta antes do conceito" não aparece só no CLAUDE.md e no Manual do Professor — ela é verificável na estrutura dos encontros. Em todas as semanas, o bloco de ferramenta (Animator, Unity Behavior, AI Navigation, ML-Agents, Sentis, A* Pathfinding Project) vem depois dos blocos de fundamentação, e vários planos explicitam o que **não** deve ser antecipado (ex.: Semana 4, §Conteúdos: GOAP e IA de Utilidade não devem ser antecipados; Semana 1: nada de máquinas de estado).

**2. Precisão de citação à Apostila.** Verificação programática de todas as referências de seção (`seção X.Y`, `seções X.Y a Z.W`) nos 17 planos, 17 decks, Cronograma e Manual do Professor contra os 171 cabeçalhos numerados reais da Apostila: **zero** citações inválidas. Em material didático produzido em volume, isso é excepcional.

**3. Rastreabilidade da progressão entre Micro Games.** Cada plano tem um campo "Relação com módulos anteriores" que amarra explicitamente o Micro Game da semana ao anterior (FSM → HFSM → BT no Módulo 1; NavMesh → A* → JPS+ no Módulo 2). O Manual do Professor (§3.2) reforça o reaproveitamento de cena e agente entre módulos. O AI Playground é, de fato, um projeto único, e não seis miniprojetos.

**4. Engenharia Reversa realmente distribuída.** O critério do CLAUDE.md ("não deve ficar restrita ao final do semestre") é cumprido: seis momentos formais (Semanas 4, 7, 9, 11, 13, 16) mais a síntese integrada da Semana 17, com a metodologia (Cap. 14) apresentada logo na Semana 4 e reutilizada com roteiro completo a partir da Semana 7. Os rótulos `[Documentado]` / `[Inferência]` / `[Especulação]` são reaplicados em todos os momentos. É um dos aspectos mais bem executados do projeto.

**5. Rubrica de qualidade profissional.** Oito critérios, quatro níveis, descritores acionáveis (não "bom/regular/ruim", mas comportamentos observáveis), com um critério — Evolução ao Longo do Semestre — que captura exatamente o que uma avaliação PBL precisa capturar e que a maioria das rubricas ignora. A orientação de uso formativo (§6: "o que seria necessário para alcançar o nível seguinte") é pedagogicamente correta.

**6. Instrumentalização completa da avaliação.** Formulários do professor (9 fichas), modelos do aluno (4 modelos) e planilha de acompanhamento multimódulo. É o tipo de material que normalmente não existe e que torna a rubrica aplicável na prática, e não apenas declarativa.

**7. Conformidade institucional verificada.** Os Critérios de Notas §2 (escala 0,0–10,0, nota mínima 6,0, frequência mínima 75%, frequência como condição independente da nota) conferem com o Regulamento da Organização Didático-Pedagógica do IFMS vigente.

**8. Antecipação técnica realista nas semanas de ML-Agents.** O Cronograma e os planos das Semanas 14–16 anteciparam corretamente os dois riscos operacionais clássicos: instalação do ambiente Python antes da aula de treino, e um modelo `.onnx` de reserva para grupos cujo treinamento falhar. Poucos materiais didáticos preveem isso.

**9. Manual do Professor com foco correto.** Explica o *porquê* e não repete conteúdo dos outros documentos (declara isso explicitamente em "Como Utilizar Este Manual" e cumpre). A tabela de dificuldades frequentes (§11) é concreta e utilizável.

**10. Automação de slides.** O workflow Marp gera PDF e PPTX, renderiza diagramas Mermaid como imagens e atualiza o `_sidebar.md` automaticamente, com regeneração seletiva por arquivo alterado. É infraestrutura sólida para manutenção do material ao longo dos semestres.

---

## Problemas Encontrados

### P1 — O Micro Game, que vale 50% da nota do módulo, não é anunciado como entrega

> ✅ **Corrigido** (julho/2026, via S1). Registro mantido para rastreabilidade.

- **Local:** Cronograma (campo **Entrega** das Semanas 4, 7, 9, 11 e 16); Planos de Aula 04, 07, 09, 11 e 16 (§Entregas, "esta semana encerra o Módulo X com **três** entregas"); Slides das Semanas 4 (l. 319), 7 (l. 281), 8 (l. 273), 10 (l. 276) e 15 (l. 259). Contraposto a: Critérios de Notas §4.
- **Descrição:** Os Critérios de Notas definem quatro instrumentos por módulo — Micro Game (50%), AI Design Log (25%), Desafio de Escolha Tecnológica (15%) e Engenharia Reversa (10%). Cronograma, planos e slides anunciam apenas três, sempre omitindo o Micro Game, que é tratado como algo que "permanece no AI Playground de cada grupo". A Semana 13 é a única exceção: lista o Micro Game Genetic Lab como entrega, ficando com quatro itens e divergindo do padrão das outras cinco.

  Pior: dentro de um mesmo plano, "as três entregas" designam conjuntos diferentes. Nos Planos 07 (l. 160), 09 (l. 165) e 11 (l. 165), a **Atividade de Laboratório** manda "reunir as três entregas do módulo (**Micro Game consolidado**, Desafio de Escolha Tecnológica, Engenharia Reversa) **junto ao AI Design Log**" — aqui o Micro Game conta e o AI Design Log não —, enquanto a seção **Entregas** do mesmo arquivo lista Desafio, AI Design Log e Engenharia Reversa, excluindo o Micro Game. São dois conjuntos incompatíveis, ambos chamados de "as três entregas", separados por 20 linhas.
- **Impacto:** O instrumento de maior peso da disciplina não tem data, formato nem condição de entrega comunicados ao estudante. Grupos podem chegar ao encerramento do módulo sem consolidar o Micro Game por não o entenderem como entrega, e o professor não terá base documental para exigi-lo. Compromete metade da nota de cinco dos seis módulos.
- **Prioridade:** **Alta**

### P2 — Divergência entre a Rubrica, os Formulários e a tabela de pesos dos Critérios de Notas

> ✅ **Corrigido** (julho/2026, via S1), adotando a **Rubrica seção 5 como fonte normativa**. Registro mantido para rastreabilidade.

- **Local:** Rubrica §5; Formulários de Avaliação, fichas 1, 2 e 3; Critérios de Notas §4.
- **Descrição:** Três divergências no mapeamento instrumento → critérios:

  | Instrumento | Rubrica §5 e Formulários | Critérios de Notas §4 |
  |---|---|---|
  | Micro Game | Compreensão Conceitual, Aplicação Prática, Uso da Unity, Qualidade Técnica (4) | Aplicação Prática, Uso da Unity, Qualidade Técnica (3) |
  | AI Design Log | AI Design Log, Tomada de Decisão, Compreensão Conceitual (3) | AI Design Log (1) |
  | Desafio de Escolha Tecnológica | Tomada de Decisão, Compreensão Conceitual, Uso da Unity (3) | Tomada de Decisão, Compreensão Conceitual (2) |

  Há ainda uma inconsistência interna no próprio §4 dos Critérios de Notas: o texto após a tabela afirma que Comunicação Técnica "é avaliado nos instrumentos em que há apresentação oral ou defesa técnica (Desafio de Escolha Tecnológica, checkpoint e apresentação final), sendo incorporado à nota desses instrumentos", mas a linha do Desafio na tabela não inclui esse critério.
- **Impacto:** Como a nota de cada instrumento é a média aritmética dos critérios aplicáveis (Critérios §3), o conjunto de critérios muda o resultado numérico. Um professor que preencha a Ficha 2 (três critérios) e depois aplique a fórmula do §4 (um critério) obtém notas diferentes para a mesma observação. A divergência é silenciosa: nada no fluxo de trabalho alerta o professor.
- **Prioridade:** **Alta**

### P3 — Utility AI é declarado inexistente na Apostila, mas existe (§6.7)

> ✅ **Corrigido** (julho/2026, via S2). Registro mantido para rastreabilidade.

- **Local:** Cronograma, "Nota de fonte" do cabeçalho e Semana 9; Manual do Professor §5.3; Plano de Aula da Semana 9, §Conteúdos e §Preparação do Professor; Slides da Semana 9 ("Ferramentas para Utility AI"). Contraposto a: Apostila §6.7, §6.8, Apêndice A (verbetes "IA de utilidade" e "Curva de utilidade", ambos remetendo ao Cap. 6), Apêndice B.1 e Apêndice C.1/C.2; e ao próprio Plano de Aula da Semana 4.
- **Descrição:** Os documentos afirmam que Utility AI "não possui capítulo dedicado, sendo tratado como extensão do Capítulo 10 e complementado pela bibliografia básica", e o plano da Semana 9 encaminha o estudante a MILLINGTON e BOURG/SEEMANN. A Apostila, porém, dedica ao tema a seção **6.7 — Aprofundamento: IA de utilidade (Utility AI)**, inclui-a no quadro comparativo da **6.8**, indexa-a no Glossário (com remissão "*Ver:* Cap. 6; Cap. 15") e a mapeia nas tabelas dos Apêndices B e C. O Plano de Aula da Semana 4 cita a §6.7 nominalmente ao instruir que ela **não** seja antecipada — ou seja, o projeto sabe que a seção existe na Semana 4 e afirma que ela não existe na Semana 9.
- **Impacto:** Contradição interna entre planos e desalinhamento com a fonte da verdade declarada. O estudante é enviado a bibliografia externa para um conteúdo que já está na Apostila, em prejuízo da coerência conceitual (a Apostila apresenta Utility AI como parente das árvores de comportamento; o Cronograma a apresenta como extensão dos mapas de influência) e do princípio de que a Apostila prevalece em caso de conflito.
- **Prioridade:** **Alta**

### P4 — *F.E.A.R.* é usado como caso de mapa de influência / Utility AI, mas a Apostila o documenta como GOAP

> ✅ **Corrigido** (julho/2026, via S2). Registro mantido para rastreabilidade.

- **Local:** Plano de Aula da Semana 9, §Engenharia Reversa; Slides da Semana 9. Contraposto a: Apostila §15.2 e Slides da Semana 1 (l. 202).
- **Descrição:** O terceiro momento de Engenharia Reversa propõe analisar *F.E.A.R.* e pergunta se o comportamento é "mais compatível com uma avaliação espacial (mapa de influência/EQS) ou com uma avaliação de ações concorrentes (IA de utilidade)". A Apostila §15.2 responde a essa pergunta de outro modo e com rótulo explícito: **`[Documentado]` *F.E.A.R.* usa GOAP**, com base na palestra de Jeff Orkin (GDC 2006) — a mesma palestra que o plano cita como fonte. Os próprios slides da Semana 1 já apresentaram *F.E.A.R.* como "planejamento (GOAP)". GOAP (§6.6 da Apostila) não é estudado em nenhuma semana.
- **Impacto:** O exercício conduz o estudante a formular hipóteses que a Apostila já refuta com documentação, contrariando frontalmente a disciplina metodológica de separar `[Documentado]` de `[Inferência]` que o Capítulo 14 e a própria atividade pretendem treinar. Perde-se o caso mais bem documentado do material, e a Apostila oferece dois casos que casam exatamente com o Módulo 3 e não são usados: **§15.7 Age of Empires / Civilization** (mapas de influência) e **§15.4 The Sims** (IA de utilidade).
- **Prioridade:** **Alta**

### P5 — Instruções internas de produção são impressas nos slides entregues

> ✅ **Corrigido** (julho/2026, via S3). Registro mantido para rastreabilidade.

- **Local:** Todos os 17 `slides.md` (18 blocos `> [!FIGURA]`) e, por consequência, todos os `semana_N_slides.pdf` e `.pptx`. Verificado na página 13 de `Slides/Semana 2/semana_2_slides.pdf`.
- **Descrição:** Os blocos de especificação de figura usam sintaxe de *alert* do GitHub (`> [!FIGURA]`), que o Marp não interpreta: o conteúdo é renderizado como citação normal. O slide projetado exibe literalmente `[!FIGURA]`, "Objetivo didático", "Arquivo sugerido", o caminho `assets/animator-fsm-guarda.webp` e "Como produzir — Screenshot direto do editor Unity […] com anotações simples adicionadas no Krita".
- **Impacto:** Falha visível de acabamento no artefato que vai ao projetor e às mãos dos estudantes, em todas as semanas do semestre. Ocupa o espaço onde deveria estar a figura, deixando a aula sem o apoio visual planejado justamente nos slides de correspondência conceito ↔ ferramenta, que são os mais dependentes de imagem.
- **Prioridade:** **Alta**

### P6 — Planos de aula remetem ao CLAUDE.md como especificação normativa das entregas

> ✅ **Corrigido** (julho/2026, via S4). Registro mantido para rastreabilidade.

- **Local:** Planos de Aula 04 (l. 181), 07 (l. 184), 09 (l. 189), 11 (l. 189) — "conforme especificado no CLAUDE.md do projeto"; Plano 13 (l. 185) — "Retomar os critérios do Desafio (seção […] do CLAUDE.md)".
- **Descrição:** O CLAUDE.md é o arquivo de configuração interna do projeto de autoria, não um documento didático. Ele não consta do `_sidebar.md`, não é citado pelo README como leitura, e não é o lugar onde a especificação do AI Design Log deve estar. O documento correto — **Modelos de Entrega do Aluno**, que traz o modelo completo do AI Design Log com os oito campos — **não é citado por nenhum dos 17 planos de aula**, nem por nenhum slide.
- **Impacto:** Um professor que assuma a disciplina será remetido a um arquivo de configuração para saber o que exigir do aluno, enquanto o documento oficialmente preparado para isso fica invisível no fluxo de trabalho. Fragiliza a cadeia documental exatamente no ponto que o README promete resolver ("qualquer professor deve conseguir conduzir o semestre").
- **Prioridade:** **Alta**

### P7 — Tempo de apresentação incompatível com o peso avaliativo

> ✅ **Corrigido** (julho/2026, via S5). Registro mantido para rastreabilidade.

- **Local:** Plano de Aula 08, Encontro 2, etapa 4 (35 min); Plano de Aula 17, Encontro 2, etapa 2 (50 min); Critérios de Notas §5.
- **Descrição:** O checkpoint da Semana 8 vale 10% da nota final e tem 35 minutos para todos os grupos. A apresentação final da Semana 17 vale 20%, é avaliada pelos **oito** critérios da Rubrica e exige que cada grupo demonstre e defenda **seis** Micro Games — em 50 minutos para a turma inteira. Nenhum documento do projeto informa tamanho de turma, número esperado de grupos ou tempo por grupo; o Plano de Ensino apenas define grupos de 2 a 3 estudantes.
- **Impacto:** Para uma turma de 20 estudantes (7 a 10 grupos), a apresentação final daria 5 a 7 minutos por grupo — menos de um minuto por Micro Game, sem espaço para as perguntas técnicas que o Manual do Professor (§9.5) e a Rubrica exigem. Na prática, ou a avaliação de maior peso vira demonstração sem defesa técnica, ou o encontro estoura. O mesmo vale, em menor grau, para o checkpoint.
- **Prioridade:** **Alta**

### P8 — Três encontros de 1h30 planejados com 100 minutos

> ✅ **Corrigido** (julho/2026, via S6). Registro mantido para rastreabilidade.

- **Local:** Planos de Aula 08, 09 e 10, Encontro 1.
- **Descrição:** A soma das durações das etapas resulta em 100 minutos nos três casos (Semana 8: 5+15+15+20+15+15+10+5; Semana 9: 5+15+20+15+15+15+5+10; Semana 10: 10+15+20+15+20+10+5+5). Os outros 31 encontros somam exatamente 90 minutos.
- **Impacto:** Excesso de 11% em três encontros consecutivos, todos de fundamentação teórica densa. Na prática, o professor cortará o bloco final — que nas três semanas é justamente o de encerramento/transição, elemento que o Manual do Professor (§4.5) considera obrigatório. Também aumenta o risco de o conteúdo transbordar para o Encontro 2, comprimindo o laboratório.
- **Prioridade:** **Média**

### P9 — Módulo 3 é o mais sobrecarregado e o mais curto em laboratório

> ✅ **Corrigido** (julho/2026, via S6). Registro mantido para rastreabilidade.

- **Local:** Cronograma, Unidade III (Semanas 8–9); Planos de Aula 08 e 09.
- **Descrição:** O Módulo 3 cobre **três** técnicas (árvores de decisão, mapas de influência e Utility AI), **duas delas sem solução oficial da Unity** — exigindo implementação própria em C# — em **duas** semanas. O único encontro de laboratório da Semana 8 divide 90 minutos entre 30 de desenvolvimento e 35 de checkpoint; somados aos 35 minutos de implementação guiada da Semana 9, o Micro Game Tactical AI dispõe de cerca de **65 minutos** de laboratório no total. Para comparação: o Módulo 1 tem 4 semanas para três técnicas, todas com ferramenta oficial; o Módulo 5 tem 2 semanas para uma única técnica.
- **Impacto:** Desequilíbrio de carga cognitiva na semana em que o estudante enfrenta, pela primeira vez, implementação própria sem ferramenta oficial de apoio. É o ponto de maior risco de os grupos entregarem um Micro Game funcional sem compreensão consolidada — exatamente o erro que o Manual do Professor (§7.4) identifica como mais frequente.
- **Prioridade:** **Média-Alta**

### P10 — Conteúdo relevante da Apostila sem qualquer uso

> ✅ **Corrigido** (julho/2026, via S7). Registro mantido para rastreabilidade.

- **Local:** Apostila — Encerramentos das Partes II, III, V, VI e VII; "Exercícios de fixação" ao final de cada capítulo; Apêndices A a D integralmente. Verificado: nenhuma ocorrência de "Exercícios de fixação", "Questões de Revisão", "Exercícios Conceituais", "Exercícios de Integração", "Tabela-decisão" ou "Checklist para o professor" em qualquer plano, slide, Cronograma ou Manual do Professor.
- **Descrição:** Os Encerramentos de Parte contêm Resumo Geral, Principais Conceitos, Questões de Revisão, Exercícios Conceituais, Exercícios de Integração e tabelas comparativas consolidadas (ex.: "Representações do Espaço", "Algoritmos de Busca", "Minimax × Alfa-Beta × MCTS", "Q-Learning × Deep RL × Algoritmos Genéticos"). O Apêndice C.1 traz uma **Tabela-decisão "dado este problema de jogo, qual técnica usar?"** — que é, literalmente, o instrumento de apoio do Desafio de Escolha Tecnológica. O Apêndice C.4 é um **Checklist para o professor**. O Apêndice B.1 mapeia conceito → ferramenta Unity. Nada disso é acionado em nenhum ponto do semestre. Apenas o Encerramento da Parte I é indicado como leitura (Semana 1).
- **Impacto:** Perda direta de material pronto, alinhado e de alto valor. As Questões de Revisão e Exercícios Conceituais são exatamente o que falta na seção "Verificação da Aprendizagem" dos planos, que hoje se apoia quase só em observação informal. A Tabela-decisão do Apêndice C.1 resolveria, sem custo, a orientação do Desafio de Escolha Tecnológica em seis semanas.
- **Prioridade:** **Média**

### P11 — Inversões de ordem de leitura da Apostila não sinalizadas

> ✅ **Corrigido** (julho/2026, via S8). Registro mantido para rastreabilidade.

- **Local:** Cronograma, Semanas 8, 12–13 e 14–16.
- **Descrição:** Duas inversões: (a) o **Cap. 5 (Árvores de Decisão, Parte II)** é lecionado na Semana 8, depois do Cap. 6 (Semana 4) — a Parte II é "encerrada" na Semana 4 e reaberta quatro semanas depois; (b) dentro da **Parte VI**, o **Cap. 13** (Semanas 12–13) vem antes do **Cap. 12** (Semanas 14–16). O Cronograma sinaliza corretamente o desdobramento do Cap. 13 em duas passagens não consecutivas, e o Manual do Professor (§5.3) instrui o professor a avisar a turma nesse caso, mas nenhuma das duas inversões é mencionada.
- **Impacto:** Estudantes que leiam a Apostila linearmente, como o Manual do Professor recomenda (§5.1, leitura prévia), encontrarão os capítulos fora da sequência da aula sem explicação. O caso da Parte VI é o mais confuso, porque a Apresentação e o Encerramento da Parte enquadram os dois capítulos em ordem inversa à do curso.
- **Prioridade:** **Média**

### P12 — Erro factual no documento entregue ao aluno

> ✅ **Corrigido** (julho/2026, via S4). Registro mantido para rastreabilidade.

- **Local:** Modelos de Entrega do Aluno, §1 (Modelo de AI Design Log).
- **Descrição:** "Entregue ao final de cada módulo, junto com o respectivo Micro Game (Semanas 4, 7, 9, 11, 13 e **17**, conforme Cronograma)". O sexto AI Design Log é entregue na **Semana 16**, junto ao encerramento do Módulo 6; a Semana 17 recebe o **AI Design Log consolidado**, que é outro documento. O §2 do mesmo arquivo lista corretamente "4, 7, 9, 11, 13 e 16" para o Desafio.
- **Impacto:** Erro de data em um documento normativo para o estudante, no único ponto do projeto em que ele lê o cronograma de entregas do seu próprio artefato.
- **Prioridade:** **Média**

### P13 — Plano de Ensino e Rubrica não reconhecem os Critérios de Notas

> ✅ **Corrigido** (julho/2026, via S9). Registro mantido para rastreabilidade.

- **Local:** Plano de Ensino, §Avaliação (último parágrafo); Rubrica §1 (último parágrafo) e §5 (último parágrafo).
- **Descrição:** Ambos afirmam que pesos, notas e fórmulas "serão realizados em documento próprio, posterior a este Plano de Ensino" / "permanecem a cargo da instituição". Esse documento já existe — os Critérios de Notas —, que inclusive cita textualmente essa promessa como sua justificativa. Nem o Plano de Ensino nem a Rubrica remetem a ele.
- **Impacto:** Um professor que leia o Plano de Ensino na ordem sugerida pelo README conclui que a definição de notas ainda não foi feita. A cadeia de referências é unidirecional: os Critérios de Notas apontam para trás, mas nada aponta para eles a partir dos dois documentos que os originaram.
- **Prioridade:** **Média**

### P14 — Ampliação da ementa institucional sem justificativa registrada

> ✅ **Corrigido** (julho/2026, via S10). Registro mantido para rastreabilidade.

- **Local:** Plano de Ensino, §Ementa; Cronograma, Semanas 4, 5 e 9.
- **Descrição:** A ementa transcrita do PPC lista: árvores de decisão, máquinas de estado, HFSM, mapa de influência, JPS+ e A*, Minimax, aprendizagem por reforço, heurísticas/algoritmos genéticos, estudo de caso e engenharia reversa. Todos são cobertos — isso é um acerto. Mas o curso também ensina **Árvores de Comportamento e Blackboard** (Semana 4), **grafos e representação do espaço / NavMesh** (Semana 5) e **Utility AI** (Semana 9), que não constam da ementa e ocupam cerca de quatro das dezessete semanas. A Justificativa do Plano de Ensino não menciona a ampliação.
- **Impacto:** Risco institucional em revisão de PPC ou em questionamento formal, e ausência de argumento pronto para o professor defender a escolha — que é tecnicamente correta (Behavior Trees são hoje o padrão de fato da indústria e o pacote oficial da Unity; grafos são pré-requisito de A*).
- **Prioridade:** **Média**

### P15 — Nenhuma versão de Unity, ML-Agents, Sentis ou Python é fixada

> ✅ **Corrigido** (julho/2026, via S11). Registro mantido para rastreabilidade.

- **Local:** Plano de Ensino, §Recursos Didáticos ("Unity — versão vigente utilizada pela disciplina"); Planos de Aula 14, 15 e 16; Manual do Professor §14; `Links de referencias.txt`.
- **Descrição:** Nenhum documento fixa versão de engine, de pacote ou do ambiente Python. As Semanas 14–16 dependem de uma cadeia versionada e frágil: pacote ML-Agents ↔ ambiente Python ↔ formato `.onnx` ↔ componente de inferência. O `Links de referencias.txt` aponta o ML-Agents para `unity-technologies.github.io/ml-agents/`, cuja documentação web a Unity depreciou em favor da documentação do pacote, e **não contém nenhum link do Sentis / Inference Engine**, apesar de a Semana 16 ser integralmente dedicada a ele. Registre-se ainda que o pacote passou a ter o identificador `com.unity.ai.inference` (o nome de exibição "Sentis" foi retomado a partir da versão 2.4), o que afeta a busca no Package Manager.
- **Impacto:** Risco operacional concentrado nas três últimas semanas de conteúdo. O Manual do Professor (§14) reconhece a necessidade de revisão periódica, mas sem uma versão de referência registrada não há como saber o que revisar nem detectar quando o material quebrou.
- **Prioridade:** **Média**

### P16 — Semana 15: 55 minutos para implementar, configurar, treinar e diagnosticar

> ✅ **Corrigido** (julho/2026, via S11). Registro mantido para rastreabilidade.

- **Local:** Plano de Aula 15, Encontro 2, etapa 2; §Atividade de Laboratório (seis etapas).
- **Descrição:** O laboratório pede, em 55 minutos: implementar o script de Agent em C# com observações, ações e recompensa; configurar o YAML com quatro hiperparâmetros; iniciar o treino por linha de comando; acompanhar a curva no TensorBoard; diagnosticar e ajustar; e preservar o `.onnx`. A Semana 16 depende integralmente desse `.onnx`.
- **Impacto:** Alta probabilidade de que parte dos grupos termine a Semana 15 sem modelo treinado. O plano da Semana 16 prevê o fallback correto (modelo de exemplo pronto), mas o grupo que o usar perde a ligação entre o próprio planejamento da Semana 14 e a inferência da Semana 16 — que é justamente o fio condutor do Módulo 6.
- **Prioridade:** **Média**

### P17 — Cronograma de 17 semanas sem folga nem ancoragem no calendário acadêmico

> ✅ **Corrigido** (julho/2026, via S12). Registro mantido para rastreabilidade.

- **Local:** Cronograma (todo); `Links de referencias.txt` (referencia o calendário acadêmico IFMS 2026, sem uso posterior).
- **Descrição:** As 17 semanas estão integralmente ocupadas, sem semana de reserva, e nenhum documento mapeia semanas a datas do calendário acadêmico do IFMS. Cada módulo depende do anterior (o Micro Game evolui em cadeia), e três módulos têm apenas duas semanas.
- **Impacto:** Um feriado, uma semana de atividade institucional ou uma aula perdida em qualquer ponto propaga o atraso até a Semana 17, sem mecanismo de absorção. O risco é maior nas Unidades III, IV e V (dois encontros úteis por módulo).
- **Prioridade:** **Média**

### P18 — Semana 10 é o único plano sem a seção Engenharia Reversa

> ✅ **Corrigido** (julho/2026, via S13). Registro mantido para rastreabilidade.

- **Local:** Plano de Aula 10.
- **Descrição:** Os outros 16 planos têm as mesmas 14 seções na mesma ordem, incluindo "Engenharia Reversa" mesmo quando o conteúdo é "não aplicável nesta semana". A Semana 10 tem 13 seções: a de Engenharia Reversa foi omitida.
- **Impacto:** Quebra do padrão estrutural que sustenta a navegabilidade do conjunto. Um professor que consulte os planos em sequência pode interpretar a ausência como esquecimento e não saber se há atividade prevista.
- **Prioridade:** **Baixa**

### P19 — Cabeçalho do Cronograma inclui a Semana 17 entre as de Desafio de Escolha Tecnológica

> ✅ **Corrigido** (julho/2026, via S13). Registro mantido para rastreabilidade.

- **Local:** Cronograma, nota de cabeçalho: "🔴 Desafio de Escolha Tecnológica + Engenharia Reversa nas semanas: 4, 7, 9, 11, 13, 16 **e 17**".
- **Descrição:** A Semana 17 tem Engenharia Reversa integrada, mas não tem Desafio de Escolha Tecnológica — como o próprio corpo do Cronograma e o Plano de Aula 17 afirmam explicitamente ("Não há Desafio de Escolha Tecnológica […]; já foram concluídos ao final do Módulo 6").
- **Impacto:** Contradição entre o cabeçalho e o corpo do mesmo documento, no primeiro elemento que o leitor encontra.
- **Prioridade:** **Baixa**

### P20 — Manual do Professor × Guia do Professor: dois nomes para o mesmo documento

> ✅ **Corrigido** (julho/2026, via S13). Registro mantido para rastreabilidade.

- **Local:** Pasta `Guia do Professor/`, arquivo `Guia_do_Professor_IA.md`, título interno "# Manual do Professor"; README e `_sidebar.md` ("Guia do Professor"); Modelos de Entrega do Aluno ("Manual do Professor"); CLAUDE.md (lista "Manual do Professor" entre os materiais).
- **Descrição:** O documento circula com dois nomes, inclusive dentro de si mesmo (título "Manual do Professor", rodapé "Este Manual do Professor…", caminho e navegação "Guia do Professor").
- **Impacto:** Ruído terminológico em um projeto que é, no restante, terminologicamente muito consistente.
- **Prioridade:** **Baixa**

### P21 — Logotipo institucional é um marcador externo de teste

> ✅ **Corrigido** (julho/2026, via S13). Registro mantido para rastreabilidade.

- **Local:** Todos os 17 `slides.md`, slide de capa: `![logo](https://dummyimage.com/280x90/ffffff/3b2f68&text=IFMS)`.
- **Descrição:** A capa de todos os decks usa uma imagem gerada por um serviço externo de *placeholder*, com a palavra "IFMS" em texto, no lugar da marca institucional. Depende de rede no momento da geração e não corresponde à identidade visual do Instituto.
- **Impacto:** Material de apresentação institucional sem a marca correta; risco de capa quebrada se o serviço estiver indisponível durante a execução do workflow.
- **Prioridade:** **Baixa-Média**

### P22 — Atribuição incorreta no Manual do Professor

> ✅ **Corrigido** (julho/2026, via S9). Registro mantido para rastreabilidade.

- **Local:** Manual do Professor §10.2.
- **Descrição:** "priorizando os critérios de Compreensão Conceitual e Tomada de Decisão — que, segundo os **Critérios de Notas**, orientam prioritariamente o processo de recuperação". Essa priorização está na **Rubrica §7**, não nos Critérios de Notas, cujo §8 trata apenas do cálculo (substituição da nota do módulo).
- **Impacto:** Referência cruzada incorreta em documento que se apresenta como guia de navegação entre os demais.
- **Prioridade:** **Baixa**

### P23 — Site de documentação sem porta de entrada e sem link para a Apostila

> ✅ **Corrigido** (julho/2026, via S13). Registro mantido para rastreabilidade.

- **Local:** `_sidebar.md`; `index.html`.
- **Descrição:** O `_sidebar.md` começa direto em "Cronograma": não há entrada "Início" apontando para o README (a Apostila, por comparação, tem), nem link para a Apostila, que é a fonte da verdade declarada. O `index.html` tem `meta name="description" content="Description"` e `repo: ''`.
- **Impacto:** Quem chega pelo site publicado não encontra o texto de orientação inicial nem o caminho para a Apostila, e a página não tem descrição para busca/compartilhamento.
- **Prioridade:** **Baixa**

### P24 — GOAP: presente na Apostila e no CLAUDE.md, ausente do semestre

> ✅ **Corrigido** (julho/2026, via S11). Registro mantido para rastreabilidade.

- **Local:** Apostila §6.6 e §15.2; CLAUDE.md (CrashKonijn GOAP, ReGoap listados entre as soluções do ecossistema a apresentar); Slides da Semana 1 (l. 202). Ausente de todo o Cronograma e dos 17 planos.
- **Descrição:** GOAP é apresentado aos estudantes na Semana 1 como a técnica de *F.E.A.R.*, aparece no quadro comparativo da §6.8 (usado na Semana 4) e nomeia dois dos assets de terceiros que o CLAUDE.md pede para apresentar — mas nunca é estudado. A Semana 4 instrui explicitamente a não antecipá-lo, sem indicar quando ele seria tratado (resposta: nunca).
- **Impacto:** Conteúdo mencionado três vezes e nunca resolvido, deixando uma lacuna perceptível para o estudante atento. Como a §6.6 é marcada como "aprofundamento", excluí-la é defensável — mas a exclusão deve ser uma decisão registrada, não um silêncio.
- **Prioridade:** **Baixa-Média**

---

## Sugestões de Melhoria

As sugestões estão ordenadas por relação entre impacto e esforço. As cinco primeiras resolvem a maior parte dos problemas de prioridade Alta.

### S1 — Unificar a matriz instrumento × critério em uma única tabela normativa

> ✅ **Implementado em julho/2026**, com a **Rubrica seção 5** adotada como fonte normativa da composição de critérios. Ver "Registro de implementação — S1" ao final deste relatório.

Resolve **P1** e **P2**. Definir, em um único lugar — sugestão: uma tabela nos **Critérios de Notas §4**, referenciada pela Rubrica §5 e pelos Formulários — quais critérios da Rubrica compõem cada instrumento e com que peso, e então propagar essa tabela para o campo **Entrega** do Cronograma, para a seção **Entregas** dos seis planos de encerramento de módulo e para os slides correspondentes. Em todos esses pontos, passar a anunciar **quatro** entregas por módulo, com o Micro Game em primeiro lugar e com o percentual explícito. A Semana 13 já está no formato correto e pode servir de modelo para as outras cinco.

Recomendo, ao decidir a matriz, manter **Compreensão Conceitual** entre os critérios do Micro Game (como estão a Rubrica e a Ficha 1): sem ela, o critério mais importante da disciplina fica restrito a instrumentos que somam apenas 25% da nota do módulo, o que contraria a filosofia declarada de "valorizar a compreensão conceitual antes da execução técnica".

### S2 — Corrigir o tratamento de Utility AI e realinhar os casos de Engenharia Reversa à Apostila

> ✅ **Implementado em julho/2026.**

Resolve **P3** e **P4**. Três ajustes:

1. Substituir a "Nota de fonte" do Cronograma e o §5.3 do Manual do Professor por: *Utility AI é tratado na Apostila na §6.7 (aprofundamento do Cap. 6) e sintetizado no quadro da §6.8; a Semana 9 retoma essa seção conectando-a aos mapas de influência do Cap. 10.* Atualizar a leitura recomendada da Semana 9 para incluir §6.7 e §6.8, mantendo a bibliografia básica como complemento, e não como fonte principal.
2. Trocar o caso da Semana 9 de *F.E.A.R.* para **Age of Empires ou Civilization (§15.7)** para o eixo de mapas de influência, ou **The Sims (§15.4)** para o eixo de Utility AI — ambos já analisados na Apostila, ambos com comportamento observável, ambos casando com o conteúdo do módulo.
3. Aproveitar o mesmo passe para nomear casos alinhados nas Semanas 13 e 16, hoje deixadas a critério do professor: **§15.5 Left 4 Dead** (Diretor de IA, ritmo adaptativo) e **§15.8 Black & White** (aprendizado) são os candidatos naturais para o Módulo 6.

Se houver interesse em manter *F.E.A.R.*, ele funciona muito bem em outro lugar: como caso de contraste na Semana 4 ou na Semana 17, precisamente por ser o exemplo em que a hipótese intuitiva (coordenação de esquadrão) é refutada pela documentação — o que é uma aula de método em si.

### S3 — Corrigir a renderização dos blocos de figura nos slides

> ✅ **Implementado em julho/2026.**

Resolve **P5**. A sintaxe `> [!FIGURA]` não é interpretada pelo Marp. Duas saídas, ambas de baixo custo:

- **Imediata:** converter os 18 blocos em comentários HTML (`<!-- FIGURA: … -->`), que o Marp ignora na renderização e que permanecem visíveis no `.md` para quem for produzir a figura; ou movê-los para as notas de apresentador do Marp (`<!-- nota -->` após o conteúdo do slide), onde ficam disponíveis no modo apresentador sem irem para a tela.
- **Definitiva:** produzir as figuras especificadas e substituir os blocos pelas imagens. Os 18 blocos já trazem descrição, nome de arquivo sugerido e método de produção — o trabalho de especificação está feito.

Vale um passe de verificação no PDF gerado após a correção, já que o defeito atravessou a geração de 17 decks sem ser notado.

### S4 — Redirecionar as referências de entrega para os Modelos de Entrega do Aluno

> ✅ **Implementado em julho/2026.**

Resolve **P6**. Substituir as cinco ocorrências de "conforme especificado no CLAUDE.md do projeto" por remissão ao documento **Modelos de Entrega do Aluno** (com indicação da seção: §1 para o AI Design Log, §2 para o Desafio, §3 para a Engenharia Reversa, §4 para os planos de apresentação). Aproveitar para citar esse documento também nos planos das Semanas 8 e 17, que envolvem apresentações e hoje não o mencionam. Corrigir, no mesmo passe, a lista de semanas do §1 dos Modelos (P12: 16, não 17).

### S5 — Fixar parâmetros de turma e reequilibrar os tempos de apresentação

> ✅ **Implementado em julho/2026.**

Resolve **P7** e, parcialmente, **P9**. Registrar, no Manual do Professor, uma premissa explícita de turma (por exemplo, "planejado para turmas de até 24 estudantes, 8 a 12 grupos") e derivar dela o tempo por grupo em cada apresentação. Com esse parâmetro em mãos, duas alternativas para a Semana 17, que é o caso crítico:

- **Apresentação em dois encontros:** usar também o Encontro 1 da Semana 17 para apresentações, reduzindo a revisão integrada do Cap. 15 para 45 minutos. Isso dobra o tempo disponível sem alterar o Cronograma.
- **Apresentação seletiva:** cada grupo demonstra dois Micro Games à escolha do professor, sorteados no início do encontro, defendendo os demais pelo AI Design Log consolidado. Preserva a avaliação dos oito critérios e reduz o tempo, com o efeito colateral desejável de desestimular a preparação de apenas um Micro Game "de vitrine".

Para o checkpoint da Semana 8, a solução mais simples é trocá-lo de posição com a discussão técnica e reduzir o bloco de laboratório, ou realizar as apresentações do checkpoint em rodízio ao longo do Encontro 2 enquanto os demais grupos trabalham — formato que o Manual do Professor já favorece ao recomendar circulação entre grupos.

### S6 — Ajustar os três encontros de 100 minutos e a carga do Módulo 3

> ✅ **Implementado em julho/2026.**

Resolve **P8** e **P9**. Nas Semanas 8, 9 e 10, cortar 10 minutos do Encontro 1. Sugestões concretas, preservando a fundamentação:

- **Semana 8:** fundir os blocos 6 e 7 ("Transição: do como chegar ao onde ir" 15 min + "Campo escalar" 10 min) em um único bloco de 15 minutos — o aprofundamento é retomado integralmente na Semana 9.
- **Semana 9:** reduzir o bloco 8 ("Encerramento e preparação do Encontro 2") de 10 para 5 minutos e o bloco 5 ("Vantagens, limitações e ferramentas") de 15 para 10.
- **Semana 10:** reduzir o bloco 1 ("Abertura da Unidade IV") de 10 para 5 minutos e o bloco 4 ("Profundidade, ramificação e utilidade") de 15 para 10.

Quanto ao desequilíbrio estrutural do Módulo 3, a intervenção de menor custo é **mover o checkpoint da Semana 8 para a Semana 7**, onde o Módulo 2 se encerra e o Encontro 2 já é de consolidação — o checkpoint passaria a fechar naturalmente os Módulos 1 e 2, em vez de interromper a abertura do Módulo 3, e devolveria 35 minutos de laboratório ao Tactical AI. Isso exige ajuste no Cronograma, nos Critérios de Notas §5 e nas fichas 5 dos Formulários, mas é uma correção localizada. Alternativa de custo zero: manter a Semana 8 como está e explicitar no plano que o Tactical AI da Semana 8 deve ficar deliberadamente mínimo (duas condições, três ações), com o grosso do trabalho na Semana 9.

### S7 — Incorporar os Encerramentos de Parte e os Apêndices da Apostila ao fluxo semanal

> ✅ **Implementado em julho/2026.**

Resolve **P10**. É a sugestão de maior retorno sobre esforço do relatório, porque o material já existe e está alinhado:

- **Nas semanas de encerramento de módulo (4, 7, 9, 11, 13, 16):** indicar o Encerramento da Parte correspondente como leitura de consolidação, e usar suas **Questões de Revisão** e **Exercícios Conceituais** na seção "Verificação da Aprendizagem" dos planos, que hoje se apoia quase só em observação informal.
- **Nas semanas de Desafio de Escolha Tecnológica:** indicar o **Apêndice C.1 (Tabela-decisão "dado este problema de jogo, qual técnica usar?")** como instrumento de apoio, e o **C.2** para a comparação de alternativas exigida pelo modelo de entrega. É exatamente o andaime que o descritor "Proficiente" do critério Tomada de Decisão pressupõe.
- **No Manual do Professor:** referenciar o **Apêndice C.4 (Checklist para o professor)** e o **Apêndice B.1 (conceito → ferramenta Unity)**, que dialogam diretamente com os capítulos 6 e 9 do Manual.
- **Na Semana 1:** apresentar o **Apêndice A (Glossário)** como referência permanente, dado que a disciplina depende fortemente de consistência terminológica.

Vale também uma decisão sobre o **"Projeto Integrador Final — Engenharia Reversa de um Jogo à sua Escolha"** do Encerramento da Parte VII: é um roteiro de seis etapas completo e bem construído, que hoje coexiste sem articulação com o AI Playground. Ou ele é incorporado (por exemplo, como formato do sexto momento de Engenharia Reversa, na Semana 16), ou o Manual do Professor deve registrar por que a disciplina optou por não usá-lo.

### S8 — Sinalizar as inversões de ordem da Apostila

> ✅ **Implementado em julho/2026.**

Resolve **P11**. Acrescentar à "Nota de fonte" do Cronograma, ao lado da observação já existente sobre o Cap. 13, duas linhas equivalentes: (a) o Cap. 5 é lecionado na Semana 8, após o Cap. 6, porque a disciplina organiza o conteúdo por problema (decisão de NPC × escolha tática) e não pela ordem da Apostila; (b) dentro da Parte VI, o Cap. 13 precede o Cap. 12, porque otimização automática é pré-requisito conceitual mais leve que aprendizagem por reforço. O Manual do Professor §5.3 já contém a instrução genérica de avisar a turma nesses casos — basta estendê-la a estes dois.

### S9 — Fechar a cadeia de referências dos documentos de avaliação

> ✅ **Implementado em julho/2026.**

Resolve **P13** e **P22**. No Plano de Ensino §Avaliação, substituir a promessa por remissão explícita aos **Critérios de Notas**, mantendo o texto que descreve o que a avaliação privilegia. Na Rubrica §1 e §5, substituir "permanecem a cargo da instituição" por remissão ao mesmo documento. No Manual do Professor §10.2, corrigir a atribuição de "Critérios de Notas" para "Rubrica §7".

### S10 — Registrar a justificativa da ampliação da ementa

> ✅ **Implementado em julho/2026.**

Resolve **P14**. Acrescentar um parágrafo à **Justificativa** do Plano de Ensino explicando que o conteúdo da ementa é integralmente coberto e que três temas complementares são incorporados por necessidade técnica e pedagógica: **grafos e representação do espaço** como pré-requisito formal de A* e JPS+; **Árvores de Comportamento e Blackboard** por serem o padrão de fato da indústria e a solução oficial da Unity para o problema de decisão de NPC previsto na ementa; **Utility AI** como extensão natural dos mapas de influência, já contemplada na Apostila. Esse parágrafo é a defesa institucional pronta caso a diferença seja questionada, e custa cinco linhas.

### S11 — Fixar versões e completar as referências técnicas

> ✅ **Implementado em julho/2026.**

Resolve **P15**, **P16** e parcialmente **P24**. Registrar, em um bloco de "Ambiente técnico de referência" no Manual do Professor (§6 ou §14), a versão do Unity, do pacote ML-Agents, do pacote de inferência (`com.unity.ai.inference`) e do ambiente Python usados no semestre, com a data da verificação. Acrescentar ao `Links de referencias.txt` a documentação do pacote de inferência e substituir o link do ML-Agents pela documentação de pacote atualmente mantida pela Unity. Aproveitar para uma decisão registrada sobre GOAP: ou incluí-lo como panorama de 10 minutos na Semana 4 (a §6.8 já o compara), ou registrar no Manual do Professor que é conteúdo de aprofundamento deliberadamente fora do escopo — e, nesse caso, remover CrashKonijn GOAP e ReGoap da lista de ferramentas a apresentar do CLAUDE.md.

Para a Semana 15, reduzir o risco de bloqueio adiantando a implementação do script de Agent para o Encontro 2 da Semana 14 (que hoje é de planejamento apenas), deixando a Semana 15 com YAML, treino e diagnóstico. Isso não altera o Cronograma e aumenta substancialmente a chance de todos os grupos chegarem à Semana 16 com `.onnx` próprio.

### S12 — Ancorar o Cronograma no calendário acadêmico e prever contingência

> ✅ **Implementado em julho/2026.**

Resolve **P17**. Acrescentar ao Cronograma uma coluna ou nota com as datas previstas das 17 semanas conforme o calendário acadêmico do IFMS do semestre, e identificar de antemão quais encontros colidem com feriados ou atividades institucionais. Registrar no Manual do Professor uma orientação de contingência: quais conteúdos são compressíveis sem perda (as Semanas 5 e 12 têm fundamentação mais folgada) e quais não podem ser cortados (Semanas 4, 9, 11, 15). Sem semana de reserva disponível, essa priorização prévia é o que substitui a folga.

### S13 — Acertos editoriais menores

> ✅ **Implementado em julho/2026.**

Resolve **P18**, **P19**, **P20**, **P21** e **P23**. Acrescentar a seção "Engenharia Reversa" ao Plano da Semana 10 no formato "não aplicável", como nos demais. Remover "e 17" da nota de cabeçalho do Cronograma, ou desdobrá-la em duas linhas (Desafio: 4, 7, 9, 11, 13, 16; Engenharia Reversa: as mesmas mais a 17). Padronizar o nome do documento do professor — recomendo "Manual do Professor", que é o título interno e o termo do CLAUDE.md — renomeando pasta, arquivo, README e `_sidebar.md`. Substituir o logotipo de *placeholder* pela marca oficial do IFMS, versionada em `Slides/themes/` para não depender de rede. Acrescentar ao `_sidebar.md` uma entrada "Início" para o README e um link externo para a Apostila, e preencher `description` e `repo` no `index.html`.

---

## Conclusão

**A disciplina não está pronta para aplicação em sala de aula, mas está perto — e o que falta é delimitado.**

O que está pronto: a arquitetura pedagógica, a progressão dos seis módulos, a estrutura dos encontros, a Rubrica, os instrumentos de avaliação, os 17 planos de aula e os 17 decks. É base suficiente para conduzir o semestre, e a qualidade do conjunto está acima do que normalmente se encontra em documentação de disciplina.

O que impede a aplicação imediata são **seis itens**, todos de correção pontual:

1. **A definição do que o aluno entrega e de como isso vira nota está inconsistente** (P1, P2). Este é o bloqueador real: sem resolvê-lo, o professor não consegue exigir o Micro Game com respaldo documental nem calcular nota de forma reprodutível. É o único item que afeta diretamente a validade da avaliação.
2. **Dois desalinhamentos com a Apostila** (P3, P4). Utility AI declarado inexistente quando está na §6.7, e *F.E.A.R.* usado contra a documentação que a própria Apostila apresenta. Ambos violam a regra de que a Apostila prevalece, e o segundo compromete pedagogicamente a atividade que mais bem executada está no projeto.
3. **Os slides entregues contêm instruções internas de produção** (P5). Defeito visível em todas as 17 semanas, em material que vai ao projetor.
4. **Os planos remetem o professor a um arquivo de configuração interna** (P6), enquanto o documento correto para o aluno fica fora do fluxo.
5. **Os dois momentos de apresentação com maior peso avaliativo não cabem no tempo previsto** (P7).
6. **Três encontros estão planejados com 11% mais conteúdo do que a duração permite** (P8).

Esses seis itens correspondem às sugestões **S1 a S6**. São correções de texto e de tabela em documentos existentes — nenhuma exige reescrita, produção de novo material ou mudança de arquitetura. O item mais trabalhoso é a produção das 18 figuras especificadas (S3), e mesmo esse tem uma saída imediata de baixo custo que já torna os decks apresentáveis.

Resolvidos, a disciplina pode ser aplicada com segurança. As demais sugestões (**S7 a S13**) elevam a qualidade — em especial **S7**, que incorpora ao semestre um volume expressivo de material da Apostila hoje ocioso e que resolveria, sem custo de produção, a fragilidade da verificação de aprendizagem e a orientação dos Desafios de Escolha Tecnológica — mas não são pré-condição para o primeiro semestre de aplicação.

Uma observação final sobre nível: **o material está adequado a um curso Superior de Tecnologia**, e em alguns pontos acima do mínimo esperado — a exigência de justificativa técnica comparativa, a documentação de decisões em AI Design Log e a disciplina metodológica de separar fato documentado de inferência formam um conjunto que a maioria dos cursos de graduação em jogos não alcança. A recomendação, aqui, é de vigilância na direção oposta: as Semanas 9, 11 e 14 concentram densidade conceitual alta em pouco tempo, e o professor precisará dos instrumentos de verificação sugeridos em S7 para detectar cedo os estudantes que ficarem para trás — porque, em um projeto integrador encadeado como o AI Playground, uma lacuna na Semana 9 se paga com juros na Semana 16.

---

## Registro de Implementação — S2 a S13 (julho/2026)

Todas as treze sugestões deste relatório foram implementadas. Os **24 problemas** identificados estão resolvidos. As decisões de projeto tomadas ao longo da implementação estão registradas abaixo, porque várias delas admitiam mais de uma solução.

### Parâmetros de turma adotados (S5)

Definidos pelo professor responsável e registrados no Manual do Professor (§4.6), no Plano de Ensino e nos Planos de Aula das Semanas 1, 8 e 17:

- **Turma:** até 40 estudantes, podendo operar com cerca de 30.
- **Grupos:** de **2 a 4** integrantes, preferencialmente 3 ou 4 (antes: 2 a 3).
- **Resultado prático:** 10 a 14 grupos por turma.

Esse número inviabiliza apresentações seriadas, e os dois momentos de apresentação foram redesenhados:

| Momento | Formato anterior | Formato adotado |
|---|---|---|
| Checkpoint (Semana 8, 10%) | 35 min de apresentações seriadas | **Rodízio durante o laboratório** — 60 min de laboratório do Tactical AI com o professor circulando e arguindo cada grupo por 4 a 5 min na bancada |
| Apresentação final (Semana 17, 20%) | 50 min de apresentações seriadas | **Feira do AI Playground** — estações por grupo, turma circulando em dois turnos, professor arguindo cada grupo por 4 a 5 min; o professor escolhe na hora dois Micro Games para demonstração |

O rodízio da Semana 8 resolve, de quebra, a sobrecarga do Módulo 3 (P9): o laboratório do Tactical AI passa de 30 para 60 minutos, porque deixa de ser interrompido por apresentações seriadas. Somado à Semana 9, o Micro Game passa de ~65 para ~95 minutos de laboratório.

Para a apresentação final, o plano registra explicitamente que 4 a 5 minutos não produzem sozinhos evidência dos oito critérios: a nota combina a defesa na feira, o AI Design Log consolidado e o acompanhamento contínuo do semestre. Isso torna o registro contínuo do Manual (§9.3) uma exigência, e não uma recomendação.

### Figuras como notas de slide (S3)

Conforme solicitado, os 18 blocos `> [!FIGURA]` foram convertidos em **comentários HTML**, que o Marp trata como notas do apresentador: ficam invisíveis no slide projetado e no PDF, e vão para o campo de anotações do PPTX. Oito deles ocupavam slides isolados e foram fundidos ao slide anterior, para não gerarem páginas em branco. A especificação de cada figura (objetivo didático, arquivo sugerido, descrição, modo de produção) foi integralmente preservada.

### Realinhamento com a Apostila (S2)

- **Utility AI** passa a ser tratado como o que é na Apostila: a **seção 6.7**, com o quadro comparativo da **6.8**. Corrigidos o Cronograma, o Manual (§5.3) e o plano da Semana 9, que agora explica por que a seção foi deliberadamente adiada da Semana 4 para cá. A bibliografia externa vira complemento, não fonte principal.
- **Casos de Engenharia Reversa realinhados ao Capítulo 15.** A Semana 9 troca *F.E.A.R.* por **Age of Empires/Civilization (§15.7)** ou **The Sims (§15.4)**; a Semana 16 passa a indicar **Black & White (§15.8)** ou **Left 4 Dead (§15.5)**. A Semana 13 registra que não há caso correspondente na Apostila — o único momento sem fonte, o que torna a análise inteiramente `[Inferência]` e é, em si, uma lição metodológica.
- ***F.E.A.R.* foi reposicionado**, não descartado: vira o caso de contraste da Semana 17, justamente por ser o exemplo em que a hipótese intuitiva do observador é refutada pela documentação.
- Como os novos casos estão analisados na Apostila, a **etapa 5 do roteiro (validação)** deixa de ser a mais frágil: o professor pode confrontar as hipóteses da turma com fonte publicada.

### GOAP — exclusão registrada (S11)

GOAP aparecia três vezes no material sem nunca ser estudado. A exclusão foi **mantida e justificada** (Manual, §6.5), não revertida: a seção 6.6 é marcada como aprofundamento na própria Apostila, e não cabe um sétimo problema de decisão em 17 semanas. O plano da Semana 4 agora distingue os dois casos — Utility AI *será* estudado na Semana 9; GOAP *não será* —, e CrashKonijn GOAP e ReGoap foram removidos da lista de ferramentas a apresentar do `CLAUDE.md`, permanecendo como aprofundamento voluntário.

### Ajustes de tempo (S6)

Semanas 8, 9 e 10 voltaram a 90 minutos no Encontro 1, sem perda de conteúdo:

- **Semana 8** — fusão dos blocos "do como chegar ao onde ir" e "campo escalar" em um único bloco de 15 min (o aprofundamento é integralmente retomado na Semana 9).
- **Semana 9** — "vantagens, limitações e ferramentas" de 15 para 10 min; encerramento de 10 para 5 min.
- **Semana 10** — abertura da Unidade IV de 10 para 5 min; "profundidade, ramificação e utilidade" de 15 para 10 min.

Todos os 34 encontros do semestre fecham agora exatamente em 90 minutos.

### Material da Apostila incorporado (S7)

Encerramentos de Parte e Apêndices deixaram de ser material morto:

| Onde | O que foi incorporado |
|---|---|
| Semanas 4, 7, 8, 9, 11, 13, 16, 17 | Encerramento da Parte correspondente na leitura recomendada, respeitando a regra de só indicá-lo quando todos os capítulos da Parte já foram estudados |
| Mesmas semanas, seção Verificação da Aprendizagem | Bloco novo indicando os **Exercícios de fixação** do capítulo e as **Questões de Revisão / Exercícios Conceituais / Exercícios de Integração** do Encerramento como instrumentos de verificação formativa |
| Semanas com Desafio | **Apêndice C.1** (tabela-decisão "qual técnica usar?") e **C.2** como andaime do Desafio de Escolha Tecnológica |
| Semana 1 e Semana 17 | **Apêndice A** (Glossário) como referência permanente e de fechamento |
| Manual do Professor | Novo §5.4 dedicado a Encerramentos e Apêndices; §6.4 remete ao Apêndice B.1; §9.6 remete ao C.1; §13.4 novo |

O **Projeto Integrador Final** do Encerramento da Parte VII foi objeto de decisão explícita: **não** é adotado como instrumento avaliativo (o Projeto Integrador da disciplina é o AI Playground), mas o Manual passa a indicá-lo como fonte de estrutura para o sexto momento de Engenharia Reversa e como aprofundamento voluntário.

### Ambiente técnico e cadeia de dependências (S11)

O Manual ganhou o §6.0 com uma **tabela de ambiente técnico de referência** a ser preenchida e datada a cada oferta (Unity, AI Navigation, Unity Behavior, ML-Agents pacote e Python, Python, pacote de inferência). Registrados três pontos práticos: o identificador do pacote de inferência é hoje **`com.unity.ai.inference`** (o nome de exibição oscilou entre "Sentis" e "Inference Engine" — buscar pelo identificador); a documentação web do ML-Agents foi depreciada em favor da documentação de pacote; e o par ML-Agents ↔ Python é o ponto frágil da cadeia. O `Links de referencias.txt` foi atualizado de acordo.

Para reduzir o risco da Semana 15 (P16), o **esqueleto do script de `Agent`** foi antecipado para o Encontro 2 da Semana 14, com justificativa registrada no plano: é atividade conceitual (traduzir estado, ação e recompensa em três métodos), não uso de ferramenta, e portanto não fere a sequência didática. A Semana 15 começa direto na configuração e no treinamento.

### Demais implementações

- **S4** — as cinco remissões ao `CLAUDE.md` foram substituídas pelos **Modelos de Entrega do Aluno**, com indicação de seção; o documento passa a ser distribuído e lido na Semana 1; corrigida a data do AI Design Log (Semana 16, não 17).
- **S8** — as duas inversões de ordem da Apostila (Cap. 5 depois do Cap. 6; Cap. 13 antes do Cap. 12) ganharam nota própria no Cronograma, ao lado da já existente sobre o desdobramento do Cap. 13.
- **S9** — Plano de Ensino e Rubrica agora remetem aos Critérios de Notas; corrigida a atribuição equivocada no Manual §10.2 (a priorização da recuperação está na Rubrica §7).
- **S10** — acrescentado ao Plano de Ensino um bloco justificando a ampliação da ementa (grafos, Behavior Trees/Blackboard, Utility AI), com o argumento técnico de cada inclusão e o registro de que nenhum item da ementa foi suprimido.
- **S12** — o Cronograma ganhou tabela de ancoragem no calendário acadêmico (a preencher) e um **plano de contingência** que classifica os encontros entre compressíveis e não compressíveis, com orientação para o caso de perda de aula.
- **S13** — seção Engenharia Reversa acrescentada à Semana 10 (único plano sem ela); cabeçalho do Cronograma desdobrado em duas linhas, separando Desafio de Engenharia Reversa; documento do professor padronizado como **Manual do Professor** (pasta, arquivo, README e `_sidebar.md`); logotipo de *placeholder* externo substituído por `Slides/themes/logo-ifms.svg`, versionado e sem dependência de rede, com instrução embutida para troca pela marca oficial; `_sidebar.md` ganhou entradas de Início e da Apostila; `index.html` teve `description` e `repo` preenchidos.

### Verificação realizada

- Os 34 encontros somam exatamente 90 minutos.
- Os 17 planos mantêm as mesmas 14 seções.
- Zero slides em branco; zero blocos `[!FIGURA]` renderizáveis; zero referências a `dummyimage.com`.
- Zero ocorrências de "três entregas", "2 a 3 estudantes", "sem capítulo dedicado" ou remissões ao `CLAUDE.md` no material didático.
- Zero tabelas Markdown irregulares em todo o repositório.

### Pendências conhecidas

1. **Regenerar os PDFs e PPTX.** Os 17 decks foram alterados (notas de figura e logotipo). O workflow `marp-slides.yml` regenera tudo no próximo *push* para `main` — o tema mudou, o que dispara a regeneração completa.
2. **Substituir o logotipo.** `Slides/themes/logo-ifms.svg` é um arquivo provisório com o texto "IFMS". Trocar pela marca oficial do Instituto, mantendo o nome do arquivo e a *viewBox* 280×90 para não alterar os decks.
3. **Produzir as 18 figuras.** As especificações estão preservadas nas notas de apresentador de cada slide.
4. **Preencher as duas tabelas em branco.** Ambiente técnico de referência (Manual §6.0) e ancoragem no calendário (Cronograma), ambas dependentes de decisões do semestre.
5. **Normalizar fins de linha.** O repositório mistura CRLF e LF, o que polui os diffs. Um `.gitattributes` com `*.md text eol=lf` resolveria.

---

## Registro de Implementação — S1 (julho/2026)

A sugestão S1 foi implementada, adotando a **Rubrica de Avaliação, seção 5, como fonte normativa** da composição de critérios de cada instrumento. Os Critérios de Notas passam a operacionalizar essa composição acrescentando apenas os pesos.

**Matriz consolidada resultante** (Critérios de Notas, item 4):

| Instrumento | Critérios da Rubrica | Peso |
|---|---|---|
| Micro Game (consolidação) | Compreensão Conceitual; Aplicação Prática; Uso da Unity e do Ecossistema; Qualidade Técnica da Solução | 50% do módulo |
| AI Design Log | AI Design Log; Tomada de Decisão; Compreensão Conceitual | 25% do módulo |
| Desafio de Escolha Tecnológica | Tomada de Decisão; Compreensão Conceitual; Uso da Unity e do Ecossistema | 15% do módulo |
| Engenharia Reversa | Compreensão Conceitual; Tomada de Decisão | 10% do módulo |
| Checkpoint (Semana 8) | Comunicação Técnica; Evolução ao Longo do Semestre | 10% da nota final |
| Apresentação final (Semana 17) | Todos os oito critérios | 20% da nota final |

**Decisões tomadas na implementação:**

- **Compreensão Conceitual foi mantida no Micro Game**, conforme a Rubrica — o que preserva o princípio declarado de "valorizar a compreensão conceitual antes da execução técnica", já que o critério passa a incidir sobre 100% da nota do módulo em vez de 25%.
- **Comunicação Técnica deixou de ser contabilizada no Desafio de Escolha Tecnológica.** A Rubrica não a lista nesse instrumento; o texto anterior dos Critérios de Notas a incluía sem respaldo. O critério permanece objeto de observação formativa nas discussões técnicas e na defesa oral do Desafio, mas só compõe nota no checkpoint e na apresentação final.
- A indicação *(principal)* herdada da Rubrica foi mantida como orientação qualitativa, com nota explícita de que **não** confere peso maior ao critério dentro da média aritmética do instrumento.

**Documentos alterados (13):** Critérios de Notas (itens 3, 4 e 5 reescritos); Rubrica de Avaliação (§1 e §5); Formulários de Avaliação (cabeçalho e fichas 1 a 6); Cronograma (nota de avaliação e campo *Entrega* das Semanas 4, 7, 8, 9, 11, 13, 16 e 17); Planos de Aula das Semanas 4, 7, 8, 9, 10, 11, 13, 15 e 16; Slides das Semanas 4, 7, 8, 10, 13, 15, 16 e 17.

**Verificação realizada:** nenhuma ocorrência remanescente de "três entregas" no repositório; matriz conferida programaticamente entre Critérios de Notas e Formulários (identidade de critérios e pesos em todos os instrumentos); somas de pesos fechando em 100% no módulo e no semestre; nenhuma tabela Markdown irregular.

**Pendência conhecida:** os PDFs e PPTX dos oito decks alterados precisam ser regenerados — o workflow `marp-slides.yml` faz isso automaticamente no próximo *push* para `main`.

Os problemas **P1** e **P2** estão resolvidos.

---

## Situação Final

As treze sugestões foram implementadas e os vinte e quatro problemas estão resolvidos. Retomando a pergunta da Conclusão — *a disciplina está pronta para aplicação em sala de aula?* —, a resposta agora é **sim**, com as cinco pendências operacionais listadas acima, nenhuma delas bloqueante para o início do semestre:

- as duas tabelas em branco (ambiente técnico e calendário) dependem de decisões que só o professor do semestre pode tomar, e existem justamente para forçar essas decisões antes da Semana 1;
- a regeneração dos slides é automática no próximo *push*;
- o logotipo e as figuras são acabamento visual, e o material funciona sem eles.

As três costuras apontadas no Resumo Executivo estão fechadas: a avaliação tem uma matriz única e propagada, os documentos operacionais estão alinhados à Apostila, e o planejamento de sala de aula agora parte de um parâmetro de turma explícito — 30 a 40 estudantes, 10 a 14 grupos — em vez de supô-lo.

Vale registrar o que **não** foi alterado, por decisão consciente: a arquitetura pedagógica, a progressão dos seis módulos, a estrutura problema → fundamentos → ferramentas → Micro Game, a Rubrica e seus oito critérios. Eram, desde a primeira leitura, o que o projeto tinha de melhor.

---

*Relatório de revisão técnica, pedagógica e editorial. As seções "Registro de Implementação" documentam as alterações feitas nos documentos do projeto a partir das sugestões S1 a S13; o restante do relatório é o diagnóstico original, preservado para rastreabilidade.*
