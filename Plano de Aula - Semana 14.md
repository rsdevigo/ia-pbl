# Plano de Aula — Semana 14

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 14 de 17 |
| **Unidade** | Unidade VI — Aprendizagem e Adaptação (Semanas 14–16) |
| **Módulo** | Módulo 6 — Como um agente aprende? |
| **Tema** | Fundamentos de Aprendizagem por Reforço |
| **Pergunta Norteadora** | Como um agente aprende? (parte 1) |
| **Tipo de semana** | 🔵 Semana de fundamentação teórica e implementação guiada (sem entrega) |

---

## Objetivos de Aprendizagem

Ao final da Semana 14, o estudante deverá ser capaz de:

1. **Distinguir** um sistema programado explicitamente de um sistema que aprende pela interação, relacionando essa distinção à diferença entre aprendizado supervisionado e Aprendizagem por Reforço (RL).
2. **Definir** com precisão o vocabulário fundamental do RL: agente, ambiente, estado, ação, recompensa, episódio, política e o dilema exploração *versus exploitation*.
3. **Explicar** o ciclo de aprendizagem (observar, decidir, agir, receber recompensa, atualizar) e o papel do retorno acumulado com desconto temporal (γ).
4. **Relacionar** o Processo de Decisão de Markov (MDP) e a propriedade de Markov ao problema de definir um bom estado para um agente de jogo.
5. **Diferenciar** recompensa de valor, e valor de estado V(s) de valor de ação Q(s, a), reconhecendo por que Q(s, a) simplifica a tomada de decisão.
6. **Reconhecer** o ML-Agents como a ferramenta oficial da Unity que materializa esse vocabulário, sem ainda operá-la para treinamento.
7. **Planejar**, em grupo, a estrutura conceitual do Micro Game Adaptive AI — estado, ações e função de recompensa — antes de qualquer implementação de treinamento.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte VI, Capítulo 12 da Apostila — Aprendizagem por Reforço**, seções 12.1 a 12.6 (mais a introdução da seção 12.9, apenas como contextualização de ferramenta):

- o problema: comportamentos que a equipe não consegue programar à mão; a distinção entre programação explícita e aprendizado pela interação; a diferença entre RL e aprendizado supervisionado — seção 12.1;
- fundamentos: agente, ambiente, estado, ação, recompensa, episódio, política e o dilema exploração *versus exploitation* — seção 12.2;
- o ciclo de aprendizagem em cinco etapas (observação, decisão, interação, recompensa, atualização) e o retorno acumulado com fator de desconto γ — seções 12.2 e 12.3;
- Processos de Decisão de Markov (MDP): estados, ações, transições, recompensas, e a propriedade de Markov — seção 12.4;
- função valor: valor de estado V(s) e valor de ação Q(s, a), e a distinção entre recompensa imediata e valor de longo prazo — seção 12.5;
- introdução ao Unity ML-Agents como ferramenta que materializa esse vocabulário na Unity (apenas como contextualização de ferramenta, sem configuração de treinamento) — seção 12.9.

Não deve ser antecipado o Q-Learning (seção 12.6) em profundidade algorítmica, nem o treinamento efetivo com ML-Agents, ambos reservados para a Semana 15. Caso o Q-Learning seja mencionado, deve ser apenas como o algoritmo que a Semana 15 detalhará, sem apresentar a regra de atualização.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte VI, Capítulo 12, seções 12.1 a 12.5 (leitura obrigatória) e 12.9 (leitura de contextualização) |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo; quadro ou slide com o vocabulário fundamental do RL para referência durante a aula; modelo de planejamento (estado/ação/recompensa) para o Micro Game Adaptive AI |
| **Cena Unity utilizada** | Nova cena para o Micro Game Adaptive AI (Módulo 6), ainda vazia ou com um cenário mínimo (por exemplo, uma arena simples ou um pequeno percurso), sem componentes de ML-Agents configurados nesta semana |
| **Assets** | Nenhum asset de arte necessário; elementos primitivos simples (cubos, esferas, planos) bastam para representar agente e ambiente do Adaptive AI |
| **Exemplos** | O diagrama do laço agente–ambiente (seção 12.2); a trilha S1–S5 usada na Apostila para ilustrar retorno e desconto (sem a regra de atualização de Bellman, reservada à Semana 15); o exemplo do jogo *CoastRunners* (reward hacking) para ilustrar recompensa mal projetada; o paralelo entre função valor e função de avaliação do Minimax (Capítulo 11) e mapa de influência (Capítulo 10), já estudados |
| **Vídeos** | Não é obrigatório vídeo externo; caso disponível, um vídeo curto mostrando os exemplos oficiais do ML-Agents (Walker/Crawler, criaturas aprendendo a caminhar) ilustra bem o conceito de agente aprendendo pela interação, sem exigir explicação técnica do treinamento |
| **Jogos para Engenharia Reversa** | Não há momento formal de Engenharia Reversa previsto nesta semana pelo Cronograma; o professor pode, a critério próprio, citar brevemente exemplos já conhecidos (AlphaGo, agentes de Atari) apenas como ilustração motivacional, sem constituir um momento formal de análise |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação teórica priorizada — o problema que a RL resolve, o vocabulário fundamental, o ciclo de aprendizagem, o MDP e a função valor. O ML-Agents é apresentado apenas como ferramenta que viabiliza o conceito na Unity, sem treinamento ainda.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura da Unidade VI e o problema da RL | 15 min | Situar a pergunta norteadora do módulo e apresentar o problema que motiva a Aprendizagem por Reforço | Anuncia a Unidade VI ("Como um agente aprende?"); apresenta a seção 12.1 — comportamentos que a equipe não consegue programar à mão; contrasta programação explícita (Partes II a V) com aprendizado pela interação; distingue RL de aprendizado supervisionado | Relacionam exemplos de jogos em que o comportamento "certo" seria difícil de programar à mão, conectando à experiência dos módulos anteriores (FSM, Behavior Trees, GOAP) |
| 2. Vocabulário fundamental do RL | 25 min | Fixar os conceitos de agente, ambiente, estado, ação, recompensa, episódio e política | Apresenta a seção 12.2, usando o diagrama do laço agente–ambiente; enfatiza a diferença entre recompensa e valor (antecipada) e o alerta sobre recompensa mal especificada (exemplo do *CoastRunners*) | Em duplas, definem estado, ação e recompensa para um minijogo simples (por exemplo, um agente que deve coletar moedas evitando obstáculos) |
| 3. Exploração *versus* exploitation e o ciclo de aprendizagem | 20 min | Compreender o dilema central do RL e o laço iterativo de aprendizagem | Apresenta o dilema exploração/*exploitation* e a estratégia ε-greedy; descreve o ciclo de cinco etapas (observar, decidir, agir, receber recompensa, atualizar) da seção 12.3 | Discutem, em grupo, por que um agente que só faz *exploitation* ou só explora falha, relacionando a situações do cotidiano (o problema do caça-níqueis) |
| 4. MDP e a propriedade de Markov | 15 min | Formalizar o cenário de decisão e destacar a responsabilidade de projetar um bom estado | Apresenta a seção 12.4: estados, ações, transições, recompensas; explica a propriedade de Markov e o alerta de que ela é uma hipótese de projeto, não uma garantia automática | Analisam, em duplas, se um estado proposto (por exemplo, apenas a posição de um agente, sem velocidade) é markoviano o suficiente para uma tarefa dada |
| 5. Função valor: V(s) e Q(s, a) | 15 min | Diferenciar recompensa de valor e situar Q(s, a) como base da decisão | Apresenta a seção 12.5, retomando o paralelo com a função de avaliação do Minimax (Capítulo 11) e o mapa de influência (Capítulo 10); explica por que Q(s, a) reduz a decisão a "escolha a ação de maior Q" | Discutem um exemplo de recompensa imediata baixa mas valor alto (ou o inverso), fixando a distinção entre os dois conceitos |

---

## Encontro 2 (1h30)

**Foco:** Setup inicial do Micro Game Adaptive AI (ambiente, agente, observações e recompensas planejadas), sem treinar o agente.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão do vocabulário aplicado ao AI Playground | 10 min | Retomar os conceitos do Encontro 1 e conectá-los ao Projeto Integrador | Revisa brevemente agente, ambiente, estado, ação, recompensa e política; anuncia que a tarefa da aula é planejar — não treinar — o Micro Game Adaptive AI | Relembram, em grupo, o vocabulário e relacionam cada termo a um elemento do próprio AI Playground |
| 2. Apresentação do ML-Agents como ferramenta (contextualização) | 15 min | Situar o ML-Agents como a ferramenta oficial da Unity para RL, sem entrar em configuração | Apresenta a seção 12.9 de forma conceitual: o ML-Agents permite que cenas da Unity sirvam de ambiente de treinamento; o desenvolvedor define observações, ações e recompensa em C#; o treinamento roda em Python; a política treinada é executada via Sentis. Reforça que nesta semana não há treinamento | Observam a demonstração (ou vídeo) dos exemplos oficiais do ML-Agents (Walker/Crawler), relacionando o que veem ao vocabulário estudado no Encontro 1 |
| 3. Laboratório — planejamento do Micro Game Adaptive AI | 40 min | Definir, em grupo, estado, ações e função de recompensa do Micro Game antes de qualquer implementação de treinamento | Acompanha os grupos na definição do problema do Adaptive AI (por exemplo, um agente que deve aprender a alcançar um alvo, desviar de obstáculos ou equilibrar-se), orientando a escolha de observações que garantam a propriedade de Markov e recompensas que evitem *reward hacking* | Definem, em grupo e por escrito, o estado (observações), o espaço de ações e a função de recompensa planejada para o Adaptive AI; montam o cenário mínimo na Unity (agente, ambiente, alvo/obstáculos), sem configurar componentes de ML-Agents |
| 4. Discussão técnica | 15 min | Comparar as escolhas de estado, ação e recompensa entre grupos | Conduz a discussão comparando as propostas dos grupos, apontando riscos de recompensa mal especificada e de estados não markovianos | Apresentam brevemente sua proposta de estado/ação/recompensa e recebem retorno dos colegas e do professor |
| 5. Encerramento | 10 min | Consolidar o planejamento e preparar a Semana 15 | Recapitula a diferença entre planejar (Semana 14) e treinar (Semana 15); anuncia que a Semana 15 tratará o Q-Learning e o treinamento efetivo com ML-Agents; reforça a recomendação de instalar previamente o ambiente ML-Agents (Python e pacotes) | Registram, para uso na Semana 15, o planejamento de estado, ações e recompensa validado na discussão |

---

## Micro Game

**Micro Game em desenvolvimento:** Adaptive AI (Módulo 6) — **início (planejamento e setup)**.

**Objetivo pedagógico:** demonstrar, antes de qualquer treinamento, que projetar um agente de Aprendizagem por Reforço exige decisões conceituais explícitas — o que observar (estado), o que é possível fazer (ações) e o que se deseja alcançar (recompensa) —, e que essas decisões determinam o sucesso do aprendizado tanto quanto o algoritmo em si.

**Funcionalidades esperadas ao final da Semana 14:**

- cenário mínimo do Micro Game Adaptive AI montado na Unity (agente, ambiente, alvo ou obstáculos conforme o problema escolhido pelo grupo), sem componentes de ML-Agents configurados;
- definição escrita do estado (observações), do espaço de ações e da função de recompensa planejada, validada em discussão técnica;
- nenhum treinamento realizado nesta semana — o Micro Game permanece em fase de planejamento.

**Relação com módulos anteriores:** inicia o Módulo 6 e a Unidade VI, retomando o paralelo entre função valor (RL) e função de avaliação do Minimax (Módulo 4) e mapa de influência (Módulo 3), já estudados. Prepara diretamente a Semana 15, na qual o mesmo planejamento será operacionalizado por meio do Q-Learning conceitual e do treinamento efetivo com ML-Agents.

---

## Engenharia Reversa

O Cronograma **não prevê** um momento formal de Engenharia Reversa na Semana 14. A recorrência de Engenharia Reversa ao longo da disciplina é retomada em semanas específicas indicadas no Cronograma; nesta semana, o foco permanece na fundamentação teórica e no planejamento do Micro Game Adaptive AI.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Unity (cena mínima)** | Montagem do cenário inicial do Micro Game Adaptive AI (agente, ambiente, alvo/obstáculos), sem componentes de ML-Agents configurados |
| **Unity ML-Agents** | Apresentado apenas como **contextualização de ferramenta** (seção 12.9): o que é, como se relaciona ao vocabulário do capítulo, e o que fará (treinamento) a partir da Semana 15. Nenhuma configuração de agente, comportamento ou treinamento é realizada nesta semana |

Nenhuma ferramenta de terceiros é indicada para esta semana, uma vez que o ML-Agents é a solução oficial e única prevista pelo Cronograma para o Módulo 6.

---

## Atividade de Laboratório

**Objetivo:** planejar, em grupo, a estrutura conceitual do Micro Game Adaptive AI — estado, ações e função de recompensa —, e montar o cenário mínimo correspondente na Unity, sem treinar o agente.

**Etapas:**

1. Escolher, em grupo, o problema que o Adaptive AI resolverá (por exemplo, alcançar um alvo, desviar de obstáculos, equilibrar-se ou manter-se em uma área).
2. Definir o **estado** (quais observações o agente terá), verificando se a informação escolhida é suficiente para respeitar a propriedade de Markov.
3. Definir o **espaço de ações** disponível ao agente (discretas ou contínuas, conforme o problema escolhido).
4. Definir a **função de recompensa**, evitando recompensar o meio em vez do fim e evitando sinais que favoreçam *reward hacking*.
5. Montar, na Unity, o cenário mínimo correspondente (agente, ambiente, alvo/obstáculos), sem adicionar componentes de ML-Agents.
6. Apresentar a proposta de estado, ação e recompensa na discussão técnica do Encontro 2, recebendo retorno para ajuste antes da Semana 15.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter um cenário mínimo montado na Unity e uma definição escrita e validada de estado, ações e recompensa para o Micro Game Adaptive AI, pronta para ser operacionalizada com ML-Agents na Semana 15.

---

## Verificação da Aprendizagem

A Semana 14 é uma semana de fundamentação, sem entrega formal nem fechamento de módulo. Conforme a Rubrica de Avaliação, o professor deve observar, de forma formativa:

- **Compreensão Conceitual** — se o estudante distingue com clareza programação explícita de aprendizado pela interação, define corretamente o vocabulário fundamental (agente, ambiente, estado, ação, recompensa, episódio, política) e compreende a diferença entre recompensa e valor;
- **Aplicação Prática** — se o planejamento do Micro Game Adaptive AI (estado, ações, recompensa) é coerente com o problema escolhido e com os cuidados discutidos em aula (propriedade de Markov, risco de recompensa mal especificada);
- **Comunicação Técnica** — se o grupo consegue apresentar e justificar oralmente, na discussão técnica do Encontro 2, as escolhas feitas para estado, ações e recompensa.

Como não há entrega nesta semana, a observação serve de insumo formativo para a avaliação do Módulo 6, que será consolidada ao final da Semana 16.

---

## Entregas

Conforme o Cronograma, a Semana 14 **não possui entrega formal**. O planejamento de estado, ações e recompensa do Micro Game Adaptive AI, produzido no Encontro 2, deve ser preservado pelos grupos para uso direto na Semana 15.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir Aprendizagem por Reforço com aprendizado supervisionado, esperando que exista um "gabarito" de ações corretas | Retomar o quadro de Atenção da seção 12.1, reforçando que o RL dispõe apenas de um sinal avaliativo de recompensa, muitas vezes esparso e atrasado |
| Definir recompensa para o meio (a ação desejada) em vez do fim (o resultado desejado), correndo risco de *reward hacking* | Retomar o Erro Comum e o exemplo do *CoastRunners* (seção 12.2), pedindo que o grupo explicite qual **resultado** deseja recompensar, não qual ação |
| Propor um estado insuficiente para a tarefa (violando a propriedade de Markov), por exemplo omitindo velocidade ou direção quando estas são relevantes | Retomar o Alerta da seção 12.4, pedindo que o grupo justifique, para cada observação omitida, se ela poderia ser necessária para decidir bem |
| Confundir valor com recompensa, avaliando decisões apenas pelo ganho imediato | Retomar o Erro Comum da seção 12.5, pedindo que o grupo dê um exemplo do próprio Adaptive AI em que a recompensa imediata é baixa mas o valor é alto (ou o inverso) |
| Tentar, por entusiasmo, configurar ou treinar o ML-Agents nesta semana, antecipando a Semana 15 e comprometendo o tempo de planejamento | Reforçar explicitamente que a Semana 14 é de planejamento conceitual, e que a configuração técnica do ML-Agents será conduzida com cuidado na Semana 15 |

---

## Preparação para a Próxima Semana

Para a Semana 15 (Treinamento com ML-Agents), o professor deve:

- confirmar que todos os grupos possuem, por escrito, a definição de estado, ações e recompensa do Micro Game Adaptive AI, validada na discussão técnica do Encontro 2;
- confirmar que todos os grupos possuem o cenário mínimo do Adaptive AI montado na Unity;
- **antecipar a instalação do ambiente ML-Agents (Python e pacotes)** em todos os computadores utilizados, conforme observação do Cronograma, evitando perda de aula com setup técnico na Semana 15;
- solicitar a leitura prévia da Parte VI, Capítulo 12, seção 12.6 (Q-Learning) e, se possível, da seção 12.9 completa (Ferramentas), preparando os estudantes para a configuração do treinamento na Semana 15.
