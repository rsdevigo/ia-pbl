# Plano de Aula — Semana 8

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 8 de 17 |
| **Unidade** | Unidade III — Tomada de Decisão Tática (Semanas 8–9) |
| **Módulo** | Módulo 3 — Como um NPC escolhe sua melhor ação? |
| **Tema** | Árvores de Decisão e introdução aos Mapas de Influência |
| **Pergunta Norteadora** | Como um NPC escolhe sua melhor ação? (parte 1) |
| **Tipo de semana** | 🔵 Abertura de Unidade, com Apresentação Técnica Intermediária (Checkpoint do AI Playground) no Encontro 2 |

---

## Objetivos de Aprendizagem

Ao final da Semana 8, o estudante deverá ser capaz de:

1. **Explicar** o problema que a árvore de decisão resolve — escolher uma ação, no instante presente, a partir de um conjunto de condições — e diferenciá-lo do problema resolvido pela FSM/HFSM (Módulo 1).
2. **Definir** com precisão os conceitos de nó de decisão, ramo e folha, e **descrever** o processo de avaliação de uma árvore de decisão da raiz até a ação.
3. **Distinguir** com clareza a árvore de decisão da árvore de comportamento, relacionando essa distinção aos conceitos de estados de retorno e nós de controle de fluxo já estudados no Módulo 1.
4. **Justificar** por que a ordenação dos testes (mais baratos e decisivos perto da raiz) afeta o custo de avaliação de uma árvore de decisão sem alterar seu resultado.
5. **Reconhecer** o mapa de influência como resposta a uma pergunta distinta da do pathfinding: não "como chegar?", mas "onde ir?", relacionando esse novo conceito à trajetória de navegação construída no Módulo 2.
6. **Descrever**, em nível introdutório, os três pilares do mapa de influência — fonte, propagação e decaimento — e o papel de cada um na transformação de pontos isolados em campos de decisão.
7. **Iniciar** o desenvolvimento do Micro Game Tactical AI, aplicando uma árvore de decisão simples à escolha de alvo de um NPC entre múltiplos candidatos (jogador, aliados).
8. **Apresentar e comunicar tecnicamente**, no checkpoint do AI Playground, o progresso consolidado dos Módulos 1 e 2, evidenciando evolução conceitual e técnica ao longo do semestre.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte II, Capítulo 5 — Árvores de Decisão** (completo) e à **Parte IV, Capítulo 10 — Mapas de Influência** (apenas introdução, seção 10.1 e início da seção 10.2):

- o problema resolvido pela árvore de decisão: escolher uma ação, agora, a partir de um conjunto de condições, sem necessidade intrínseca de memória de estado — seção 5.1;
- fundamentos: nós de decisão (testes), ramos (respostas) e folhas (ações), e o processo de avaliação da raiz até a folha — seção 5.2;
- a distinção essencial entre árvore de decisão e árvore de comportamento — propósito, funcionamento, presença ou ausência de estados de retorno e de noção de tempo — seção 5.2.1;
- ordenação de testes (testes baratos e decisivos perto da raiz) e o efeito da profundidade da árvore no custo e na legibilidade — seção 5.3.1;
- nota de contexto sobre árvores de decisão aprendidas (ID3/entropia), apenas para situar a diferença entre a árvore autoral (usada em jogos) e a árvore induzida por dados — seção 5.3.2;
- exemplos de seleção de ação por árvore de decisão e sua convivência natural dentro de estados de uma FSM/HFSM — seção 5.4;
- vantagens (simplicidade, baixo custo, transparência) e limitações (ausência de tempo, de sequenciamento, de reutilização, de composição) da árvore de decisão, que motivaram a adoção das árvores de comportamento pela indústria — seção 5.5;
- ferramentas: ausência de ferramenta dedicada da Unity; a lógica condicional escrita em C# ou em Visual Scripting, e sua presença como nós de condição dentro do Unity Behavior — seção 5.7;
- introdução ao mapa de influência: o problema de decidir *onde* agir, complementar ao pathfinding, que decide *como chegar* — seção 10.1;
- introdução ao conceito de campo escalar sobre o mapa e a ideia geral de fonte, propagação e decaimento, sem aprofundamento em combinação de camadas nem em atualização em tempo real, reservados à Semana 9 — início da seção 10.2.

Não deve ser antecipado o restante do Capítulo 10 (combinação de camadas, seção 10.2.2; funcionamento e atualização em tempo real, seção 10.3; exemplos, vantagens, limitações, jogos e ferramentas, seções 10.4 a 10.7): esse conteúdo é reservado à Semana 9, quando o Módulo 3 é aprofundado e consolidado. Também não é objetivo desta semana implementar o mapa de influência: nesta semana ele é apresentado apenas como conceito motivador, preparando a Semana 9.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte II, Capítulo 5, completo (seções 5.1 a 5.8); Parte IV, Capítulo 10, seção 10.1 e início da seção 10.2 (até o conceito de campo escalar, sem aprofundar em 10.2.1 e 10.2.2); **Encerramento da Parte II**, que se completa nesta semana com o Capítulo 5 — sua *Tabela Comparativa Consolidada* (FSM × HFSM × árvore de decisão × BT) é o melhor apoio para a distinção trabalhada no Encontro 1 |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com os Micro Games NPC Decision e Navigation consolidados; cópias impressas da Ficha 5 dos Formulários de Avaliação, uma por grupo, para o rodízio de checkpoint; cronômetro para controlar os 4 a 5 minutos de cada arguição |
| **Dimensionamento de turma** | A disciplina é planejada para turmas de **até 40 estudantes**, podendo operar com cerca de 30, organizadas em grupos de **2 a 4** — o que resulta, na prática, em **10 a 14 grupos**. É esse número que torna inviável o formato de apresentações seriadas e justifica o rodízio adotado neste encontro. Com 14 grupos, o rodízio consome cerca de 56 dos 60 minutos de laboratório: o professor deve iniciá-lo imediatamente e manter o cronômetro visível |
| **Cena Unity utilizada** | Nova cena (ou extensão de cena existente) para o Micro Game Tactical AI, com um NPC tático e ao menos dois ou três alvos candidatos (o jogador e um ou dois aliados simulados), cada um expondo atributos observáveis de distância, vida e nível de ameaça, que alimentem os testes da árvore de decisão de seleção de alvo |
| **Assets** | Nenhum asset adicional obrigatório; reaproveita-se a estrutura de cena e os scripts já existentes dos Micro Games anteriores sempre que aplicável |
| **Exemplos** | Diagrama de árvore de decisão da seção 5.2 (NPC que decide entre patrulhar, fugir, atacar corpo a corpo ou atirar), usado para ensinar o mecanismo geral de nós, ramos e folhas; quadro comparativo árvore de decisão versus árvore de comportamento da seção 5.2.1; diagrama conceitual "como chegar? versus onde ir?" da seção 10.1; no Micro Game, o mesmo mecanismo de testes encadeados é reaplicado a um problema distinto — escolher, entre vários alvos candidatos, qual deve receber a ação do NPC |
| **Vídeos** | Não é necessário vídeo específico nesta semana; recomenda-se, opcionalmente, uma captura curta de um jogo de estratégia mostrando controle territorial, para antecipar visualmente o conceito de mapa de influência que será aprofundado na Semana 9 |
| **Jogos para Engenharia Reversa** | Não previsto nesta semana, conforme o Cronograma |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação da árvore de decisão como terceira forma de seleção de ação, com distinção clara frente à árvore de comportamento. Introdução conceitual ao mapa de influência como ponte para a Semana 9.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e transição de módulo | 5 min | Situar a Semana 8 na trajetória da disciplina | Recapitula a conclusão dos Módulos 1 (NPC Decision) e 2 (Navigation), e anuncia a pergunta do Módulo 3: como um NPC escolhe sua melhor ação? | Relembram brevemente FSM, HFSM e Behavior Trees do Módulo 1, antecipando como esses conceitos se relacionam com uma nova forma de decisão |
| 2. O problema: escolher uma ação a partir de condições | 15 min | Apresentar o problema que a árvore de decisão resolve | Apresenta a seção 5.1, contrastando o problema da árvore de decisão ("qual ação agora?") com o problema da FSM ("em que modo estou?") | Discutem, em duplas, um exemplo próprio de decisão que dependeria de várias condições simultâneas |
| 3. Nós, ramos e folhas | 15 min | Explicar a estrutura e a avaliação da árvore de decisão | Apresenta a seção 5.2 com o diagrama do NPC (patrulhar/fugir/atacar/atirar), demonstrando a descida da raiz até a folha | Percorrem, em voz alta, o caminho de avaliação para um conjunto de condições proposto pelo professor |
| 4. Árvore de decisão versus árvore de comportamento | 20 min | Consolidar a distinção essencial entre as duas arquiteturas | Apresenta o quadro comparativo da seção 5.2.1, retomando os conceitos de estados de retorno e nós de controle de fluxo estudados no Módulo 1 | Preenchem, em grupo, um quadro comparativo próprio, relacionando cada arquitetura a um exemplo do Micro Game NPC Decision já desenvolvido |
| 5. Ordenação de testes e limitações | 15 min | Explicar o efeito da ordenação de testes, situar brevemente a árvore autoral frente à árvore aprendida, e apresentar as limitações que motivaram as árvores de comportamento | Apresenta a seção 5.3.1 (ordenação e profundidade), a nota de contexto da seção 5.3.2 (árvore de decisão autoral, escrita à mão, versus árvore aprendida por ID3/entropia — apenas para situar a diferença, sem aprofundar aprendizado de máquina) e a seção 5.5 (limitações: ausência de tempo, sequenciamento, reutilização e composição) | Identificam, para a árvore de decisão do exemplo, qual teste deveria ficar mais perto da raiz e por quê, e registram a diferença entre a árvore que estão desenhando à mão e uma árvore aprendida a partir de dados |
| 6. Do "como chegar" ao "onde ir": o campo escalar | 15 min | Introduzir o problema do mapa de influência e seu conceito central | Apresenta a seção 10.1 — as três situações (cobertura, avanço de exército, fuga) que o pathfinding, sozinho, não resolve — e emenda no início da seção 10.2, definindo campo escalar e anunciando fonte, propagação e decaimento como pilares a aprofundar na Semana 9 | Relacionam as três situações a cenários do próprio AI Playground e registram dúvidas iniciais sobre campo escalar para a semana seguinte |
| 7. Encerramento e preparação do checkpoint | 5 min | Orientar a preparação da arguição de checkpoint | Apresenta os critérios do checkpoint (Comunicação Técnica e Evolução ao Longo do Semestre), explica o formato de rodízio adotado no Encontro 2 e orienta os grupos a prepararem uma demonstração curta do progresso do AI Playground | Organizam, em grupo, o roteiro da demonstração e da defesa a serem feitas no Encontro 2 |

---

## Encontro 2 (1h30)

**Foco:** Início do Micro Game Tactical AI com árvore de decisão, com o checkpoint do AI Playground conduzido **em rodízio** durante o próprio laboratório.

> **Formato do checkpoint.** Com turmas de 30 a 40 estudantes (10 a 14 grupos), apresentações seriadas para toda a turma são inviáveis: consumiriam o encontro inteiro e reduziriam cada grupo a três minutos. O checkpoint é, portanto, conduzido em **rodízio**: os grupos trabalham no Tactical AI enquanto o professor circula e realiza, com cada um, uma arguição de 4 a 5 minutos na própria bancada, aplicando a Ficha 5 dos Formulários de Avaliação. O formato preserva a defesa técnica individualizada exigida pela Rubrica, devolve ao laboratório o tempo antes gasto em apresentações seriadas e é coerente com a orientação de circulação entre grupos do Manual do Professor (§4.3). Ver a nota de dimensionamento de turma na Preparação do Professor.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida e organização do rodízio | 10 min | Retomar os conceitos-chave e organizar a dinâmica do encontro | Recupera a distinção entre árvore de decisão e árvore de comportamento e anuncia a ordem do rodízio de checkpoint, para que cada grupo saiba quando será arguido | Respondem perguntas de verificação oral e deixam o AI Playground dos Módulos 1 e 2 pronto para demonstração na própria bancada |
| 2. Laboratório do Tactical AI com checkpoint em rodízio | 60 min | Implementar a árvore de decisão de seleção de alvo e avaliar o progresso do AI Playground nos Módulos 1 e 2 | Circula entre os grupos em duas frentes simultâneas: orienta a implementação da árvore de decisão de seleção de alvo (atributos dos candidatos, ordenação dos testes) e conduz, com cada grupo, uma arguição de 4 a 5 minutos sobre os Micro Games NPC Decision e Navigation, avaliando Comunicação Técnica e Evolução ao Longo do Semestre e registrando feedback na Ficha 5 | Implementam a árvore de decisão de seleção de alvo do NPC do Tactical AI, testando ao menos dois caminhos de avaliação distintos que resultem em alvos diferentes; quando chega sua vez, demonstram o AI Playground e defendem as decisões técnicas tomadas até aqui |
| 3. Síntese do checkpoint e discussão técnica | 10 min | Devolver à turma o que foi observado no rodízio e consolidar a árvore implementada | Apresenta os padrões observados no rodízio (acertos recorrentes e fragilidades comuns) e conduz a discussão sobre a ordenação de testes escolhida pelos grupos, relacionando-a à seção 5.3.1 | Justificam, em voz alta, a ordem dos testes escolhida para a própria árvore e comparam com a de outros grupos |
| 4. Encerramento | 10 min | Fechar a semana e indicar o caminho do Módulo 3 | Recapitula o início do Módulo 3 e anuncia que a Semana 9 aprofunda o mapa de influência e retoma a IA de utilidade da seção 6.7 | Registram o feedback recebido no checkpoint e as pendências a resolver antes da Semana 9 |

---

## Micro Game

**Micro Game em desenvolvimento:** Tactical AI (Módulo 3) — **início**.

**Objetivo pedagógico:** demonstrar como um NPC escolhe, entre múltiplos alvos candidatos, aquele que deve receber sua ação — aplicando, para isso, a estrutura mais simples e transparente da família de técnicas desta semana, a árvore de decisão —, antes de avançar, na Semana 9, para uma seleção de alvo por combinação ponderada de fatores (mapa de influência e Utility AI).

**Funcionalidades esperadas ao final da Semana 8:**

- uma cena do Micro Game Tactical AI com um NPC e ao menos dois alvos candidatos (o jogador e um ou dois aliados simulados), cada um expondo distância, vida e nível de ameaça observáveis;
- uma árvore de decisão implementada em C# ou Visual Scripting que, a partir de testes encadeados sobre esses atributos (por exemplo, "há aliado com vida crítica?", "algum alvo representa ameaça imediata?", "qual alvo está mais próximo?"), resulte na escolha de um único alvo entre os candidatos, com nós de decisão, ramos e folhas de alvo claramente identificáveis;
- capacidade do grupo de explicar o caminho de avaliação da árvore para diferentes configurações de alvos;
- capacidade do grupo de justificar a ordenação dos testes escolhida.

**Relação com módulos anteriores:** inaugura o Módulo 3 sobre a base consolidada dos Módulos 1 (NPC Decision — FSM, HFSM, Behavior Trees, Blackboard) e 2 (Navigation — NavMesh, A*, JPS+), reaproveitando, quando pertinente, a mesma cena e os mesmos NPCs já desenvolvidos, agora com uma nova camada de tomada de decisão tática de seleção de alvo.

---

## Engenharia Reversa

Não há momento de Engenharia Reversa previsto para a Semana 8, conforme o Cronograma. O próximo momento formal ocorre na Semana 9, ao final do Módulo 3, aplicado a um jogo com IA tática visível.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C#** | Implementação da árvore de decisão do Micro Game Tactical AI, por meio de estruturas condicionais organizadas segundo nós de decisão, ramos e folhas |
| **Visual Scripting** (oficial, alternativa) | Alternativa para grafos de decisão condicional, para grupos que preferirem uma representação visual da árvore de decisão |
| **Unity Behavior** (mencionado, não utilizado nesta semana) | Referenciado apenas para situar onde os testes de uma árvore de decisão reaparecem como nós de condição dentro de uma árvore de comportamento, sem uso prático obrigatório nesta semana |

Nenhuma ferramenta de mapa de influência é utilizada nesta semana: o conteúdo do Capítulo 10 é tratado exclusivamente em nível conceitual e introdutório, com aprofundamento reservado à Semana 9.

---

## Atividade de Laboratório

**Objetivo:** implementar uma árvore de decisão simples e funcional no Micro Game Tactical AI, e preparar e apresentar o checkpoint técnico intermediário do AI Playground.

**Etapas:**

1. Definir, em grupo, de dois a três alvos candidatos do NPC (por exemplo, o jogador e um ou dois aliados simulados) e os atributos observáveis de cada um (distância, vida, nível de ameaça).
2. Desenhar, em papel ou diagrama simples, a árvore de decisão de seleção de alvo antes de implementá-la, aplicando o critério de ordenação de testes da seção 5.3.1 — testes mais baratos e decisivos (por exemplo, presença de ameaça imediata) mais perto da raiz.
3. Implementar a árvore de decisão em C# ou Visual Scripting, testando ao menos dois caminhos de avaliação distintos, cada um resultando na escolha de um alvo diferente entre os candidatos.
4. Deixar o AI Playground (Micro Games NPC Decision e Navigation consolidados) pronto para demonstração imediata na própria bancada, com o roteiro de defesa preparado a partir do Modelo de Plano de Apresentação (Modelos de Entrega do Aluno, §4).
5. Demonstrar e defender o checkpoint ao professor, na arguição de 4 a 5 minutos do rodízio, respondendo a perguntas técnicas sobre as escolhas de arquitetura realizadas até aqui.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma árvore de decisão funcional no Micro Game Tactical AI e deve ter sido arguido no rodízio de checkpoint, recebendo feedback formativo sobre Comunicação Técnica e Evolução ao Longo do Semestre.

---

## Verificação da Aprendizagem

A Semana 8 **não encerra um módulo de conteúdo** — o Módulo 3 é consolidado apenas na Semana 9 —, mas gera nota por meio da **Apresentação Técnica Intermediária (Checkpoint)**, conforme os Critérios de Notas da disciplina. O professor deve aplicar a Rubrica de Avaliação ao checkpoint, observando principalmente:

- **Comunicação Técnica** — verificando se o grupo explica com clareza o problema, a solução adotada e as decisões técnicas dos Micro Games NPC Decision e Navigation, respondendo adequadamente a perguntas da turma ou do professor;
- **Evolução ao Longo do Semestre** — verificando se o grupo incorporou, de forma consistente, o feedback recebido nos Módulos 1 e 2, evidenciando progresso perceptível no domínio conceitual e técnico.

O checkpoint da Semana 8 corresponde a 10% da nota final do semestre, conforme os Critérios de Notas. O professor deve registrar e comunicar aos estudantes a nota obtida no checkpoint, com o respectivo feedback formativo, preparando o terreno para o critério de Evolução que será novamente observado no Módulo 3 (Semana 9).

A implementação inicial da árvore de decisão no Micro Game Tactical AI não gera nota isolada nesta semana: ela é observada formativamente pelo professor, para orientar a consolidação do Micro Game na Semana 9, quando o Módulo 3 é encerrado e avaliado pelos quatro instrumentos previstos (Micro Game, AI Design Log, Desafio de Escolha Tecnológica e Engenharia Reversa).


**Instrumentos de verificação disponíveis na Apostila.** Antes de recorrer a questões próprias, o professor deve usar o material já pronto e alinhado: os **Exercícios de fixação** ao final do Capítulo 5, e — nas semanas de encerramento de Parte — as **Questões de Revisão**, os **Exercícios Conceituais** e os **Exercícios de Integração** do Encerramento correspondente. Recomenda-se aplicar duas ou três questões na abertura do Encontro 2, como verificação rápida antes do laboratório, e usar a Tabela Comparativa Consolidada do Encerramento da Parte II como apoio à discussão técnica. Esse material é a principal fonte de verificação formativa da disciplina, e não deve ficar sem uso.

---

## Entregas

Conforme o Cronograma, a única entrega formal avaliada da Semana 8 é:

- **Apresentação Técnica Intermediária (Checkpoint do AI Playground)** — demonstração e defesa oral do progresso consolidado dos Módulos 1 e 2, realizada na arguição de rodízio do Encontro 2 e avaliada pelos critérios de Comunicação Técnica e Evolução ao Longo do Semestre (10% da nota final do semestre).

A árvore de decisão implementada no Micro Game Tactical AI permanece em desenvolvimento e será consolidada, com o restante do Módulo 3, na Semana 9 — não constitui entrega avaliada isoladamente nesta semana.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir árvore de decisão com árvore de comportamento, tratando-as como sinônimos por compartilharem a forma de árvore | Retomar o quadro comparativo da seção 5.2.1, com ênfase nos conceitos de estados de retorno e nós de controle de fluxo, já vistos no Módulo 1 |
| Tentar expressar, na árvore de decisão do Micro Game, uma sequência de ações com dependência de sucesso ("faça A, depois B") | Retomar o Erro Comum da seção 5.5: a árvore de decisão escolhe uma ação, não orquestra uma sequência; esse é o território das árvores de comportamento, já disponível do Módulo 1 |
| Ordenar os testes da árvore sem critério, colocando testes caros ou pouco decisivos perto da raiz | Retomar a Boa Prática da seção 5.3.1 e pedir que o grupo justifique, para cada teste, se ele é barato/decisivo o suficiente para ficar próximo da raiz |
| Confundir o mapa de influência, ainda em nível introdutório, com a grade de navegação já estudada no Módulo 2 | Retomar o quadro de Atenção da seção 10.2, reforçando que a grade de navegação responde "posso ir?" (topológico) e o mapa de influência responde "vale a pena ir?" (avaliativo) |
| Tentar comparar os alvos candidatos por uma pontuação numérica combinada (por exemplo, somar distância, vida e ameaça em um único número) já nesta semana | Explicar que a combinação ponderada de fatores é o território da IA de Utilidade e do mapa de influência, retomados na Semana 9; nesta semana a árvore de decisão resolve a escolha de alvo por testes encadeados (sim/não), não por soma de pesos |
| Apresentar o checkpoint de forma excessivamente técnica ou excessivamente genérica, sem equilibrar clareza e profundidade | Orientar previamente, no Encontro 1, que a defesa deve explicar decisões técnicas de forma acessível, com exemplos concretos do próprio AI Playground |
| Grupo despreparado quando chega sua vez no rodízio, consumindo o tempo de arguição para abrir cena ou recompilar o projeto | Anunciar a ordem do rodízio logo na etapa 1 do Encontro 2 e exigir que o AI Playground esteja aberto e rodando desde o início do encontro; grupos despreparados vão para o fim da fila, sem tempo adicional |

---

## Preparação para a Próxima Semana

Para a Semana 9 (Mapas de Influência e Utility AI — encerramento do Módulo 3 e da Unidade III), o professor deve:

- registrar a nota do checkpoint da Semana 8, com o respectivo feedback formativo de Comunicação Técnica e Evolução ao Longo do Semestre, antes do início da Semana 9;
- confirmar que todos os grupos possuem, ao final da Semana 8, uma árvore de decisão de seleção de alvo funcional no Micro Game Tactical AI, servindo de base para a consolidação do Módulo 3;
- preparar o aprofundamento do Capítulo 10 (seções 10.2.1 em diante — fontes, propagação, decaimento, combinação de camadas, atualização em tempo real, exemplos, vantagens, limitações, jogos e ferramentas, incluindo a comparação com o EQS da Unreal) e a extensão para Utility AI, sem solução oficial equivalente na Unity;
- reservar, para a Semana 9, o material do terceiro momento de Engenharia Reversa, em jogo com IA tática visível (tiro ou estratégia), conforme o Cronograma;
- anunciar aos estudantes que a Semana 9 encerra o Módulo 3 e a Unidade III, com **quatro** entregas avaliadas: Micro Game 3 consolidado (50%), AI Design Log do Micro Game 3 (25%), Desafio de Escolha Tecnológica (15%) e o terceiro momento de Engenharia Reversa (10%) — reforçando que o Micro Game é a entrega de maior peso do módulo, e não apenas um artefato de trabalho.
