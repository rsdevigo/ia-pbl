# Incrementos de Implementação por Micro Game

Tabela extraída do Cronograma e dos Planos de Aula (Semanas 01–17), organizada como entrada para a geração de prompts de implementação no modo Plan do Cursor. Cada linha corresponde a um incremento incremental do projeto Unity único (AI Playground), dentro da subpasta de Assets do respectivo Micro Game.

Legenda de colunas: **Semana/Encontro** (2º Encontro = "Desenvolvimento do Micro Game", salvo indicação contrária) · **Incremento a implementar (código)** · **Pacote/Biblioteca necessário** · **Assets/Cenário necessário**.

---

## Módulo 1 — NPC Decision: Criatura de Ambiente

| Semana / Encontro | Incremento a implementar (código) | Pacote / Biblioteca | Assets / Cenário |
|---|---|---|---|
| S01 – 2º Encontro | Setup do projeto Unity "AI Playground" (estrutura de pastas por Micro Game). Nenhuma lógica de IA ainda. | Unity (template 3D/2D) | Nenhum. Esboço textual do cenário/NPC/comportamentos esperados. |
| S02 – 2º Encontro | FSM inicial do NPC: 3–5 estados (ex.: Patrulhar, Perseguir, Atacar), transições com guardas e prioridade, enter/update/exit por estado. Implementação via Animator, `enum`/`switch` ou padrão *State* em C#. | Animator Controller (oficial) e/ou Scripting C# | Cena de demonstração com 1 NPC (cápsula/modelo provisório) e ponto de referência do jogador. |
| S03 – 2º Encontro | Reestruturação em HFSM: ao menos 2 superestados (ex.: "Pacífico", "Combate") agrupando os subestados da S02; transição herdada válida por superestado; estado inicial por nível; decisão sobre estado de histórico. | Sub-state machines do Animator e/ou extensão do padrão *State* em C# | Mesma cena da S02, reaproveitada. |
| S04 – 2º Encontro | Migração da HFSM para Behavior Tree: seletor-raiz com subárvores por superestado, ≥1 sequência, ≥1 seletor interno, ≥1 decorador justificado; definição das chaves do Blackboard (tipo, nós que leem/escrevem). Comportamento observável deve ser equivalente ao da HFSM. | **Unity Behavior** (oficial) + Blackboard | Mesma cena das S02/S03. |

**Estado final do Micro Game 1:** BT com Blackboard funcional, equivalente à HFSM anterior, documentada no AI Design Log.

---

## Módulo 2 — Navigation: Entregador

| Semana / Encontro | Incremento a implementar (código) | Pacote / Biblioteca | Assets / Cenário |
|---|---|---|---|
| S05 – 2º Encontro | Bake de NavMesh na cena de teste (NavMesh Surface: Agent Radius/Height/Max Slope/Step Height); adição de NavMesh Agent a um NPC com destino simples (código ou ponto fixo). | **AI Navigation / NavMesh** (oficial): NavMesh Surface, NavMesh Agent, NavMesh Modifiers/Areas, Off-Mesh Links | Nova cena "Entregador": geometria primitiva simples (duas salas, um corredor, obstáculos — colunas/caixas). |
| S06 – 2º Encontro | Adição de um segundo destino ou obstáculo móvel, validando recálculo de rota pelo NavMesh Agent. Opcional: versão mínima de A* próprio sobre grade auxiliar (script simplificado, listas aberta/fechada). | NavMesh Agent (reutilizado); Scripting C# (A* próprio, opcional); A* Pathfinding Project citado apenas como referência, sem uso obrigatório | Mesma cena da S05. |
| S07 – 2º Encontro | Sem novo código obrigatório: revisão/robustez da cena (NavMesh + NavMesh Agent + obstáculo/destino da S06). JPS+ tratado apenas conceitualmente, sem implementação. | NavMesh Agent (consolidado) | Mesma cena das S05/S06, sem novos elementos obrigatórios. |

**Estado final do Micro Game 2:** NavMesh + NavMesh Agent robustos, navegação testada com múltiplos destinos/obstáculos, documentado no AI Design Log.

---

## Módulo 3 — Tactical AI: Seleção de Alvo

| Semana / Encontro | Incremento a implementar (código) | Pacote / Biblioteca | Assets / Cenário |
|---|---|---|---|
| S08 – 2º Encontro | Árvore de decisão do NPC avaliando 2–3 condições (ex.: visão do jogador, distância, vida), com nós de decisão, ramos e folhas de ação; testar ao menos 2 caminhos de avaliação distintos. | Scripting C# (estruturas condicionais) ou Visual Scripting (oficial, alternativa) | Nova cena (ou extensão) "Tactical AI" com NPC e 2–3 condições observáveis. |
| S09 – 2º Encontro | Integração da árvore de decisão (S08) com: grade simples de mapa de influência (fontes, propagação, decaimento, atualizado em baixa frequência) e/ou função de utilidade ponderada com ≥3 ações candidatas para seleção de alvo. | Scripting C# (implementação própria — sem solução oficial Unity equivalente); AI Navigation/NavMesh citado apenas como possível base de distância, sem uso obrigatório | Mesma cena da S08, estendida com grade de células e, se possível, mais de um NPC/ponto de ameaça. |

**Estado final do Micro Game 3:** NPC com árvore de decisão + mapa de influência e/ou utility AI, escolhendo alvo entre jogador/aliados por distância, vida, ameaça.

---

## Módulo 4 — Board Game AI: Conecta 4 Reduzido

| Semana / Encontro | Incremento a implementar (código) | Pacote / Biblioteca | Assets / Cenário |
|---|---|---|---|
| S10 – 2º Encontro | Representação de estado do jogo da velha (tabuleiro 3×3, jogador da vez, teste de jogada terminal, jogadas legais) + função recursiva de Minimax (casos-base, alternância MAX/MIN, construção sob demanda), sem função de avaliação nem poda. | Scripting C# (implementação própria — sem solução oficial Unity) | Nova cena mínima: grade 3×3, sem arte elaborada (quadrados/texto X e O). |
| S11 – 2º Encontro | Função de avaliação (soma ponderada de características) + poda alfa-beta sobre o Minimax da S10; aplicação a tabuleiro maior — **Conecta 4 em grade reduzida** (ou damas simplificada). | Scripting C# (estendendo S10) | Mesma cena mínima, estendida para o tabuleiro do Conecta 4 reduzido. |

**Estado final do Micro Game 4:** IA joga Conecta 4 Reduzido com Minimax + poda alfa-beta + heurística, em tempo aceitável, com nós examinados reduzidos verificáveis.

---

## Módulo 5 — Genetic Lab: Criaturas Evoluídas

| Semana / Encontro | Incremento a implementar (código) | Pacote / Biblioteca | Assets / Cenário |
|---|---|---|---|
| S12 – 2º Encontro | População inicial aleatória (representação/cromossomo); função de aptidão para problema simples (ex.: aproximar string-alvo / "OneMax"); operadores: seleção por torneio, crossover de um ponto, mutação com taxa configurável, elitismo. | Scripting C# (laço evolutivo e operadores — implementação própria) | Nova cena mínima "Genetic Lab", sem elementos visuais complexos. |
| S13 – 2º Encontro | Adaptação da representação, função de aptidão e parâmetros (taxa de mutação, tamanho do torneio, grau de elitismo) a um problema mais expressivo (ex.: evoluir parâmetros de uma criatura/IA de jogo para locomoção); registro de evidência (gráfico/log) de melhor aptidão e aptidão média; ajustes para convergência prematura. | Scripting C# (consolidação); GeneticSharp/NEAT citados apenas como contextualização, sem uso obrigatório | Continuidade da cena da S12, adaptada ao problema de locomoção/parâmetros da criatura. |

**Estado final do Micro Game 5:** AG evoluindo forma/parâmetros de uma criatura simples para melhor locomoção, com evidência registrada de melhoria ao longo das gerações.

---

## Módulo 6 — Adaptive AI: Coletor de Recompensas

| Semana / Encontro | Incremento a implementar (código) | Pacote / Biblioteca | Assets / Cenário |
|---|---|---|---|
| S14 – 2º Encontro | Montagem do cenário mínimo (agente, ambiente, alvo/obstáculos), **sem** configurar ML-Agents ainda; escrita do esqueleto do script `Agent` em C# (métodos de coleta de observações, execução de ações, atribuição de recompensa). | Nenhum pacote de IA ainda (Unity puro); ML-Agents apenas contextualizado | Nova cena "Adaptive AI": arena simples ou pequeno percurso, elementos primitivos (cubos, esferas, planos) representando itens positivos/negativos. |
| S15 – 2º Encontro | Conclusão do script `Agent` (`CollectObservations`, `OnActionReceived`, `AddReward`); adição de Behavior Parameters e Decision Requester; configuração do arquivo YAML de hiperparâmetros; treinamento via linha de comando; acompanhamento da curva de recompensa no TensorBoard; preservação do modelo `.onnx`. | **Unity ML-Agents** (pacote oficial, requer instalação via Package Manager + ambiente Python do ML-Agents); TensorBoard | Mesma cena da S14, recebendo os componentes de ML-Agents. |
| S16 – 2º Encontro | Importação do `.onnx` (S15) como asset do Sentis; criação do worker de inferência; substituição do vínculo Decision Requester/ML-Agents pela leitura direta do modelo; verificação de funcionamento autônomo (sem dependência do ambiente de treinamento). | **Unity Sentis** (pacote oficial, requer instalação via Package Manager) | Mesma cena, já treinada, recebendo o componente de inferência do Sentis. |

**Estado final do Micro Game 6:** Agente treinado via ML-Agents, executando de forma autônoma por inferência via Sentis, coletando itens positivos e evitando negativos.

---

## Semana 17 — Integração final (sem novo Micro Game)

| Semana / Encontro | Incremento a implementar (código) | Pacote / Biblioteca | Assets / Cenário |
|---|---|---|---|
| S17 – 2º Encontro (+ laboratório prévio) | Reunião das cenas dos 6 Micro Games em um único projeto Unity; teste isolado de cada um; navegação simples entre eles (ex.: menu). Nenhuma mecânica nova de IA. | Todas as ferramentas dos Módulos 1–6, já implementadas (nenhuma nova) | Projeto Unity do AI Playground completo, com as 6 cenas reunidas. |

---

## Observações

- Semanas de abertura de módulo (S01, S05, S08¹, S10, S12, S14) concentram fundamentação teórica no 1º Encontro; a tabela lista apenas o incremento de código do 2º Encontro, que é o insumo relevante para prompts de implementação no modo Plan.
- ¹ S08 tem checkpoint em rodízio (arguição) em paralelo à implementação da árvore de decisão — não é um incremento de código adicional.
- Ferramentas citadas apenas como panorama comparativo (NodeCanvas, Behavior Designer, A* Pathfinding Project, EQS da Unreal, GeneticSharp, NEAT) **não** entraram como pacote necessário, pois os planos de aula não determinam seu uso prático obrigatório.
- ML-Agents e Sentis exigem instalação via Unity Package Manager e, no caso do ML-Agents, também o ambiente Python (`mlagents` via pip) para treinamento — não citado explicitamente no texto dos planos além de "linha de comando", mas implícito ao uso da ferramenta.
