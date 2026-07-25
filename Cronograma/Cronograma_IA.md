# Cronograma Detalhado — Disciplina de Inteligência Artificial e Ilusão de Inteligência
**Curso Superior de Tecnologia em Jogos Digitais**
Project-Based Learning | 17 Semanas | 51 horas (2 encontros de 1h30/semana)

> 🔴 **Encerramento de módulo** — Desafio de Escolha Tecnológica **e** Engenharia Reversa: semanas **4, 7, 9, 11, 13 e 16**
> 🔴 **Semana 17** — Engenharia Reversa integrada e apresentação final; **não** há Desafio de Escolha Tecnológica
> 🔵 Semana regular (fundamentação e desenvolvimento do Micro Game) nas demais

> **Nota de avaliação:** cada módulo de conteúdo encerra com **quatro** entregas avaliadas — Micro Game consolidado (50%), AI Design Log (25%), Desafio de Escolha Tecnológica (15%) e Engenharia Reversa (10%). Os critérios observados em cada instrumento seguem a Rubrica de Avaliação (seção 5) e os pesos seguem os Critérios de Notas (item 4).

> **Nota de fonte:** os capítulos indicados seguem o sumário oficial da Apostila (rsdevigo.github.io/apostila-ia). Utility AI (Semana 9) é tratado na Apostila na **seção 6.7** (aprofundamento do Capítulo 6) e sintetizado no quadro comparativo da **seção 6.8**; a Semana 9 retoma essa seção conectando-a aos mapas de influência do Capítulo 10, por afinidade de problema — ambos decidem por combinação ponderada de fatores.

> **Nota de ordem de leitura:** três capítulos são estudados fora da sequência linear da Apostila, sempre porque a disciplina se organiza por problema, e não pela ordem do sumário. O professor deve sinalizar cada caso à turma:
> - **Cap. 5 (Árvores de Decisão, Parte II)** é estudado na **Semana 8**, depois do Cap. 6 (Semana 4): ele pertence ao problema "qual ação agora?" (Módulo 3), e não ao problema "em que modo estou?" (Módulo 1). Por isso o **Encerramento da Parte II** só é indicado como leitura na Semana 8, quando a Parte se completa.
> - **Cap. 13 (Heurísticas e Algoritmos Genéticos, Parte VI)** é utilizado em duas passagens não consecutivas: heurísticas de avaliação na **Semana 11** e algoritmos genéticos nas **Semanas 12–13**.
> - **Cap. 13 precede o Cap. 12** dentro da Parte VI: otimização automática (Semanas 12–13) é pré-requisito conceitual mais leve do que aprendizagem por reforço (Semanas 14–16), e a comparação "otimizar × aprender a agir" fica mais clara nessa ordem. O **Encerramento da Parte VI** é indicado na Semana 16, quando ambos os capítulos já foram vistos.

---

## Ancoragem no Calendário Acadêmico

As 17 semanas deste Cronograma são **letivas e sequenciais**, sem semana de reserva. Antes do início do semestre, o professor deve preencher a tabela abaixo confrontando-a com o calendário acadêmico do IFMS vigente, identificando de antemão os encontros que colidem com feriados, recessos, semanas de atividades institucionais ou eventos do campus.

| Semana | Data do Encontro 1 | Data do Encontro 2 | Observações (feriado, evento, reposição) |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 🔴 | | | |
| 5 | | | |
| 6 | | | |
| 7 🔴 | | | |
| 8 | | | *checkpoint* |
| 9 🔴 | | | |
| 10 | | | |
| 11 🔴 | | | |
| 12 | | | |
| 13 🔴 | | | |
| 14 | | | |
| 15 | | | |
| 16 🔴 | | | |
| 17 🔴 | | | apresentação final |

### Plano de contingência

Como cada módulo depende do anterior — o Micro Game evolui em cadeia — e três módulos dispõem de apenas duas semanas, a perda de um encontro se propaga até a Semana 17 se não for absorvida no próprio módulo. Sem semana de folga disponível, a absorção depende de saber de antemão **o que é compressível**:

**Encontros com folga relativa (compressíveis em até 20 minutos, sem perda estrutural):**

- **Semana 5, Encontro 1** — a fundamentação de grafos comporta síntese; as três representações espaciais podem ser apresentadas pela tabela comparativa em vez de uma a uma.
- **Semana 12, Encontro 1** — o vocabulário evolutivo pode ser condensado, já que é retomado na aplicação da Semana 13.
- **Semana 17, Encontro 1** — a revisão integrada de Engenharia Reversa pode cair de 30 para 15 minutos (é o que o próprio plano prevê como alternativa quando a turma tem muitos grupos).
- **Semana 2 e Semana 3, Encontro 1** — comportam redução se a turma chegar com a leitura prévia feita.

**Encontros que não devem ser comprimidos:**

- **Semanas 4, 7, 9, 11, 13 e 16, Encontro 2** — concentram três dos quatro instrumentos avaliativos do módulo. Comprimir aqui é comprimir avaliação.
- **Semana 8, Encontro 2** — o rodízio de checkpoint já opera no limite do tempo com 14 grupos.
- **Semana 15, Encontro 2** — o treinamento efetivo é pré-requisito da Semana 16; sem ele, o módulo inteiro trava.
- **Semana 17, Encontro 2** — a feira é o instrumento de maior peso do semestre.

**Se um encontro for perdido:** a primeira opção é redistribuir o conteúdo dentro do próprio módulo, comprimindo o encontro de fundamentação seguinte. A segunda é converter parte da fundamentação em leitura dirigida da Apostila, com verificação por meio das Questões de Revisão do Encerramento da Parte correspondente. Adiar a entrega de um módulo deve ser a última opção, porque desloca todas as entregas seguintes e compromete o critério de Evolução ao Longo do Semestre, que depende de feedback devolvido a tempo.

---

## Unidade I — Fundamentos e Decisão de NPCs (Semanas 1–4)

*Pergunta da Unidade: como um NPC decide o que fazer?*

---

### Semana 1 🔵
**Tema:** Abertura da disciplina, fundamentos de IA em jogos e apresentação do Projeto Integrador

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | O que é Inteligência Artificial em jogos, e por que "ilusão"? |
| **Apostila** | Parte I, Cap. 1 — O que é IA em Jogos; Parte I, Cap. 2 — História e Evolução |
| **Encontro 1** | Fundamentação: IA de jogos não busca inteligência ótima, mas comportamentos convincentes, controláveis e viáveis (ilusão de inteligência). Panorama histórico das técnicas que serão estudadas no semestre. |
| **Encontro 2** | Apresentação da metodologia PBL e do AI Playground como Projeto Integrador. Formação dos grupos (3 a 4 estudantes; 2 apenas em turmas menores). Esboço do plano inicial do Micro Game 1 (NPC Decision), sem implementação. |
| **Ferramentas** | Unity (setup inicial do projeto AI Playground) |
| **Entrega** | Formação de grupos; plano inicial do Micro Game 1 |

---

### Semana 2 🔵
**Tema:** Máquinas de Estado Finitas

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como um NPC decide o que fazer? (parte 1) |
| **Apostila** | Parte II, Cap. 3 — Máquinas de Estado Finitas (FSM) |
| **Encontro 1** | Fundamentação teórica de FSM (estados, transições, eventos) e demonstração de uma FSM simples no Unity via Animator/scripting. |
| **Encontro 2** | Implementação guiada: primeira versão do Micro Game NPC Decision usando FSM. Discussão técnica sobre os limites de uma FSM plana. |
| **Ferramentas** | Animator / Scripting C# |
| **Entrega** | — |

---

### Semana 3 🔵
**Tema:** Máquinas de Estado Hierárquicas

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como organizar decisões cada vez mais complexas de um NPC? |
| **Apostila** | Parte II, Cap. 4 — Máquinas de Estado Hierárquicas (HFSM) |
| **Encontro 1** | Fundamentação de HFSM como resposta ao crescimento descontrolado de estados e transições da FSM plana. Demonstração de reestruturação hierárquica. |
| **Encontro 2** | Evolução do NPC Decision de FSM para HFSM, reaproveitando a implementação da Semana 2. Discussão técnica comparando as duas abordagens. |
| **Ferramentas** | Scripting C# (HFSM) |
| **Entrega** | — |

---

### Semana 4 🔴
**Tema:** Árvores de Comportamento, Blackboard e Engenharia Reversa

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como tornar a decisão do NPC modular e escalável? |
| **Apostila** | Parte II, Cap. 6 — Árvores de Comportamento (Behavior Trees) e Blackboard; Parte VII, Cap. 14 — Metodologia de Engenharia Reversa de IA |
| **Encontro 1** | Fundamentação de Behavior Trees e Blackboard. Demonstração no Unity Behavior, com comparação pontual a soluções de terceiros (NodeCanvas, Behavior Designer). Apresentação formal da metodologia de Engenharia Reversa, que passa a ser reutilizada nos módulos seguintes. |
| **Encontro 2** | Consolidação do Micro Game NPC Decision com BT + Blackboard. Desafio de Escolha Tecnológica do Módulo 1. Primeiro momento de Engenharia Reversa, aplicando a metodologia a um jogo comercial com IA de decisão visível. |
| **Ferramentas** | Unity Behavior, Blackboard; comparação com NodeCanvas / Behavior Designer |
| **Entrega** | **Micro Game 1 — NPC Decision consolidado (50%)**; AI Design Log — Micro Game 1 (25%); Desafio de Escolha Tecnológica M1 (15%); 1º momento de Engenharia Reversa (10%) |
| **Observação** | Encerramento da Unidade I. |

---

## Unidade II — Navegação e Busca de Caminhos (Semanas 5–7)

*Pergunta da Unidade: como um agente encontra seu destino?*

---

### Semana 5 🔵
**Tema:** Grafos e representação do espaço

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como um agente encontra seu destino? (parte 1) |
| **Apostila** | Parte III, Cap. 7 — Grafos e Representação do Espaço |
| **Encontro 1** | Fundamentação de representação do espaço de jogo em grafos, base conceitual antes de qualquer algoritmo de busca. |
| **Encontro 2** | Início do Micro Game Navigation: configuração da NavMesh do Unity AI Navigation, relacionando a malha gerada ao grafo estudado na teoria. |
| **Ferramentas** | AI Navigation / NavMesh |
| **Entrega** | — |

---

### Semana 6 🔵
**Tema:** Busca de caminhos com A*

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como calcular o melhor caminho entre dois pontos? |
| **Apostila** | Parte III, Cap. 8 — Busca de Caminhos com A* |
| **Encontro 1** | Fundamentação do algoritmo A* (função heurística, lista aberta/fechada). Demonstração de uma implementação própria simplificada, para tornar visível o que a NavMesh resolve internamente. |
| **Encontro 2** | Evolução do Micro Game Navigation com A*. Discussão técnica comparando a implementação própria com a solução interna da NavMesh. |
| **Ferramentas** | AI Navigation; implementação própria de A* (comparação conceitual) |
| **Entrega** | — |

---

### Semana 7 🔴
**Tema:** JPS+ e otimizações de busca

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como tornar a navegação eficiente em larga escala? |
| **Apostila** | Parte III, Cap. 9 — JPS+ e Otimizações |
| **Encontro 1** | Fundamentação dos limites de escala do A* e de como o JPS+ os resolve. Comparação com o A* Pathfinding Project (ecossistema de terceiros). |
| **Encontro 2** | Consolidação do Micro Game Navigation. Desafio de Escolha Tecnológica do Módulo 2. Segundo momento de Engenharia Reversa, em jogo com navegação relevante. |
| **Ferramentas** | A* Pathfinding Project (terceiros, comparação) |
| **Entrega** | **Micro Game 2 — Navigation consolidado (50%)**; AI Design Log — Micro Game 2 (25%); Desafio de Escolha Tecnológica M2 (15%); 2º momento de Engenharia Reversa (10%) |
| **Observação** | Encerramento da Unidade II. |

---

## Unidade III — Tomada de Decisão Tática (Semanas 8–9)

*Pergunta da Unidade: como um NPC escolhe sua melhor ação?*

---

### Semana 8 🔵
**Tema:** Árvores de decisão e introdução aos mapas de influência

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como um NPC escolhe sua melhor ação? (parte 1) |
| **Apostila** | Parte II, Cap. 5 — Árvores de Decisão; Parte IV, Cap. 10 — Mapas de Influência (introdução) |
| **Encontro 1** | Fundamentação de Árvores de Decisão como estrutura de escolha entre ações. Introdução conceitual aos Mapas de Influência: da pergunta "como chegar" para "onde devo ir". |
| **Encontro 2** | Início do Micro Game Tactical AI. Apresentação técnica intermediária: checkpoint de progresso do AI Playground como um todo. |
| **Ferramentas** | Scripting C# |
| **Entrega** | Apresentação técnica intermediária — checkpoint do AI Playground (10% da nota final do semestre) |

---

### Semana 9 🔴
**Tema:** Mapas de influência e Utility AI

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como um NPC escolhe sua melhor ação? (parte 2) |
| **Apostila** | Parte IV, Cap. 10 — Mapas de Influência (aprofundamento); Parte II, Cap. 6, seções 6.7 e 6.8 — IA de utilidade (Utility AI), retomada aqui por afinidade de problema |
| **Encontro 1** | Aprofundamento de Mapas de Influência e retomada da IA de utilidade (seção 6.7). Como não há solução oficial da Unity equivalente, a implementação é própria em C#. |
| **Encontro 2** | Consolidação do Micro Game Tactical AI. Desafio de Escolha Tecnológica do Módulo 3. Terceiro momento de Engenharia Reversa, em jogo com decisão espacial ou por utilidade visível (Age of Empires ou The Sims, Cap. 15). |
| **Ferramentas** | Implementação própria em C# (sem solução oficial Unity equivalente) |
| **Entrega** | **Micro Game 3 — Tactical AI consolidado (50%)**; AI Design Log — Micro Game 3 (25%); Desafio de Escolha Tecnológica M3 (15%); 3º momento de Engenharia Reversa (10%) |
| **Observação** | Encerramento da Unidade III. |

---

## Unidade IV — Busca Adversarial (Semanas 10–11)

*Pergunta da Unidade: como derrotar um adversário inteligente?*

---

### Semana 10 🔵
**Tema:** Minimax e busca adversarial

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como derrotar um adversário inteligente? (parte 1) |
| **Apostila** | Parte V, Cap. 11 — Minimax e Busca Adversarial |
| **Encontro 1** | Fundamentação da árvore de jogo e do algoritmo Minimax. Demonstração para um jogo de tabuleiro simples. |
| **Encontro 2** | Início do Micro Game Board Game AI, como implementação própria em C# (não há solução oficial da Unity para este problema). |
| **Ferramentas** | Implementação própria em C# |
| **Entrega** | — |

---

### Semana 11 🔴
**Tema:** Heurísticas e poda alfa-beta

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como derrotar um adversário inteligente? (parte 2) |
| **Apostila** | Parte VI, Cap. 13 — Heurísticas e Algoritmos Genéticos (parte de heurísticas de avaliação) |
| **Encontro 1** | Fundamentação de heurísticas de avaliação para tornar o Minimax viável em profundidade maior. Introdução da poda alfa-beta. |
| **Encontro 2** | Consolidação do Micro Game Board Game AI. Desafio de Escolha Tecnológica do Módulo 4. Quarto momento de Engenharia Reversa, em jogo de tabuleiro ou estratégia por turnos. |
| **Ferramentas** | Implementação própria em C# |
| **Entrega** | **Micro Game 4 — Board Game AI consolidado (50%)**; AI Design Log — Micro Game 4 (25%); Desafio de Escolha Tecnológica M4 (15%); 4º momento de Engenharia Reversa (10%) |
| **Observação** | Encerramento da Unidade IV. O Capítulo 13 será retomado nas Semanas 12–13 para a parte de Algoritmos Genéticos — sinalizar aos estudantes que o capítulo não foi "concluído" nesta semana. |

---

## Unidade V — Otimização Automática (Semanas 12–13)

*Pergunta da Unidade: como encontrar automaticamente boas soluções?*

---

### Semana 12 🔵
**Tema:** Fundamentos de algoritmos genéticos

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como encontrar automaticamente boas soluções? (parte 1) |
| **Apostila** | Parte VI, Cap. 13 — Heurísticas e Algoritmos Genéticos (parte de Algoritmos Genéticos) |
| **Encontro 1** | Fundamentação de Algoritmos Genéticos: população, seleção, cruzamento e mutação. |
| **Encontro 2** | Início do Micro Game Genetic Lab, implementação própria em C#, aplicando os operadores genéticos a um problema simples. |
| **Ferramentas** | Implementação própria em C# |
| **Entrega** | — |

---

### Semana 13 🔴
**Tema:** Aplicação de algoritmos genéticos

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como encontrar automaticamente boas soluções? (parte 2) |
| **Apostila** | Parte VI, Cap. 13 — Heurísticas e Algoritmos Genéticos (aplicação) |
| **Encontro 1** | Aprofundamento da aplicação de Algoritmos Genéticos a um problema mais expressivo: convergência, diversidade e ajuste de parâmetros. |
| **Encontro 2** | Consolidação do Micro Game Genetic Lab. Desafio de Escolha Tecnológica do Módulo 5. Quinto momento de Engenharia Reversa, relacionando otimização automática a balanceamento ou geração procedural em jogos comerciais. |
| **Ferramentas** | Implementação própria em C# |
| **Entrega** | **Micro Game 5 — Genetic Lab consolidado (50%)**; AI Design Log — Micro Game 5 (25%); Desafio de Escolha Tecnológica M5 (15%); 5º momento de Engenharia Reversa (10%) |
| **Observação** | Encerramento da Unidade V. |

---

## Unidade VI — Aprendizagem e Adaptação (Semanas 14–16)

*Pergunta da Unidade: como um agente aprende?*

---

### Semana 14 🔵
**Tema:** Fundamentos de aprendizagem por reforço

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como um agente aprende? (parte 1) |
| **Apostila** | Parte VI, Cap. 12 — Aprendizagem por Reforço |
| **Encontro 1** | Fundamentação teórica priorizada: agente, ambiente, recompensa, política. ML-Agents apresentado apenas como ferramenta que viabiliza o conceito na Unity, sem treinamento ainda. |
| **Encontro 2** | Setup inicial do Micro Game Adaptive AI (ambiente, agente, observações e recompensas planejadas), sem treinar o agente. |
| **Ferramentas** | ML-Agents (introdução) |
| **Entrega** | — |
| **Observação** | Recomenda-se antecipar a instalação do ambiente ML-Agents (Python e pacotes) para esta semana, evitando perda de aula com setup técnico na Semana 15. |

---

### Semana 15 🔵
**Tema:** Treinamento com ML-Agents

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como um agente aprende? (parte 2) |
| **Apostila** | Parte VI, Cap. 12 — Aprendizagem por Reforço (aprofundamento prático) |
| **Encontro 1** | Configuração do treinamento no ML-Agents: hiperparâmetros básicos e observação das primeiras curvas de recompensa. |
| **Encontro 2** | Treinamento efetivo do agente do Micro Game Adaptive AI. Semana predominantemente prática, com acompanhamento contínuo do professor. |
| **Ferramentas** | ML-Agents |
| **Entrega** | Acompanhamento do projeto |

---

### Semana 16 🔴
**Tema:** Inferência com Sentis e consolidação

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | Como um agente aprende? (parte 3) |
| **Apostila** | Parte VI, Cap. 12 — Aprendizagem por Reforço (aplicação); introdução ao Sentis |
| **Encontro 1** | Apresentação do Sentis como ferramenta oficial da Unity para inferência de modelos treinados. Aplicação ao agente treinado do Adaptive AI. |
| **Encontro 2** | Consolidação do Micro Game Adaptive AI. Desafio de Escolha Tecnológica do Módulo 6 — encerra o ciclo dos seis módulos. Sexto momento de Engenharia Reversa, em jogo com IA adaptativa ou aprendizado perceptível (Black & White ou Left 4 Dead, Cap. 15). |
| **Ferramentas** | Sentis |
| **Entrega** | **Micro Game 6 — Adaptive AI consolidado (50%)**; AI Design Log — Micro Game 6 (25%); Desafio de Escolha Tecnológica M6 (15%); 6º momento de Engenharia Reversa (10%) |
| **Observação** | Encerramento da Unidade VI e do ciclo completo dos seis módulos de conteúdo. |

---

## Unidade VII — Projeto Final e Encerramento (Semana 17)

---

### Semana 17 🔴
**Tema:** Engenharia Reversa integrada e apresentação final do AI Playground

| Campo | Conteúdo |
|---|---|
| **Pergunta Norteadora** | O que aprendemos sobre IA e ilusão de inteligência? |
| **Apostila** | Parte VII, Cap. 15 — Estudos de Caso Comentados (síntese integrada de todo o semestre) |
| **Encontro 1** | Revisão integrada dos jogos analisados ao longo do semestre à luz de todas as técnicas estudadas, retomando o Cap. 15. |
| **Encontro 2** | Apresentação final do AI Playground completo, com todos os Micro Games reunidos. Entrega do AI Design Log consolidado. Encerramento do semestre. |
| **Ferramentas** | Todas as anteriores (integração) |
| **Entrega** | Apresentação final do AI Playground + AI Design Log consolidado (20% da nota final do semestre) |

---

*Disciplina: Inteligência Artificial e Ilusão de Inteligência — Curso Superior de Tecnologia em Jogos Digitais*
*Apostila: https://rsdevigo.github.io/apostila-ia*
