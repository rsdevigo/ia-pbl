# Plano de Aula — Semana 13

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 13 de 17 |
| **Unidade** | Unidade V — Otimização Automática (Semanas 12–13) |
| **Módulo** | Módulo 5 — Como encontrar automaticamente boas soluções? |
| **Tema** | Aplicação de Algoritmos Genéticos |
| **Pergunta Norteadora** | Como encontrar automaticamente boas soluções? (parte 2) |
| **Tipo de semana** | 🔴 Semana de encerramento de módulo (Desafio de Escolha Tecnológica, AI Design Log e Engenharia Reversa) |

---

## Objetivos de Aprendizagem

Ao final da Semana 13, o estudante deverá ser capaz de:

1. **Aplicar** os quatro operadores genéticos (seleção, crossover, mutação, elitismo) a um problema mais expressivo do que o utilizado na Semana 12, ajustando representação e função de aptidão conforme a nova complexidade.
2. **Diagnosticar**, a partir da curva de aptidão observada (saltos e platôs), sinais de convergência prematura, e **propor** ajustes de taxa de mutação, pressão seletiva ou grau de elitismo para corrigi-los.
3. **Relacionar** as aplicações de Algoritmos Genéticos em jogos — balanceamento automático, geração procedural de conteúdo, evolução de comportamentos, ajuste de parâmetros de IA e design procedural — a problemas concretos do AI Playground.
4. **Diferenciar** implementação própria em C#, bibliotecas de terceiros (GeneticSharp) e neuroevolução (NEAT), indicando vantagens, limitações e cenários de uso de cada abordagem.
5. **Avaliar** criticamente vantagens e limitações dos Algoritmos Genéticos frente a métodos exatos de otimização e à Aprendizagem por Reforço (Módulo 6), justificando quando cada família de técnica é a mais adequada.
6. **Justificar tecnicamente**, no Desafio de Escolha Tecnológica do Módulo 5, a escolha de uma solução de otimização automática para um problema proposto, considerando requisitos, alternativas e limitações.
7. **Consolidar**, em grupo, o Micro Game Genetic Lab, evidenciando melhoria mensurável da aptidão ao longo das gerações em um problema mais expressivo.
8. **Relacionar**, no quinto momento de Engenharia Reversa, um caso de balanceamento ou geração procedural em um jogo comercial aos conceitos de otimização evolutiva estudados nas Semanas 12 e 13.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte VI, Capítulo 13 da Apostila — Heurísticas e Algoritmos Genéticos**, seções 13.7 a 13.11:

- aplicações de Algoritmos Genéticos em jogos: balanceamento automático, geração procedural de conteúdo (PCG baseada em busca), evolução de comportamentos e estratégias (incluindo neuroevolução), ajuste de parâmetros de IA e design procedural (incluindo evolução interativa) — seção 13.7;
- ferramentas: o esqueleto conceitual de uma implementação própria em C#, bibliotecas de terceiros como a GeneticSharp, e a integração com a Unity via neuroevolução (NEAT) — seção 13.8;
- vantagens (generalidade, exploração global e robustez a ótimos locais, tratamento da função de aptidão como caixa-preta, paralelização, soluções criativas) e limitações (ausência de garantia de ótimo, custo computacional, dependência crítica da função de aptidão, muitos parâmetros a ajustar, convergência prematura, velocidade imprevisível) dos Algoritmos Genéticos, e a comparação com métodos tradicionais de otimização e com a Aprendizagem por Reforço — seção 13.9;
- estudos de caso, distinguindo fato documentado de análise técnica fundamentada: PCG baseada em busca na pesquisa acadêmica, competições de IA de jogos por evolução e neuroevolução (incluindo NEAT), balanceamento e ajuste de parâmetros na indústria (inferência cautelosa), e neuroevolução em jogos experimentais (NERO) — seção 13.10;
- encerramento do capítulo: síntese do Capítulo 13 e da Parte VI, consolidando a distinção entre otimizar (Algoritmos Genéticos) e aprender a agir (Aprendizagem por Reforço, Módulo 6) — seção 13.11.

Não deve ser reintroduzido o conteúdo fundamental das seções 13.1 a 13.6 (já tratado na Semana 12); ele deve ser apenas retomado brevemente, quando necessário, para sustentar a aplicação prática desta semana.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte VI, Capítulo 13, seções 13.7 a 13.11; **Apêndice C.1** e **C.2** como apoio ao Desafio. *Observação:* o **Encerramento da Parte VI** fica reservado para a Semana 16, quando o Capítulo 12 também já tiver sido estudado — sinalizar à turma que a Parte VI ainda não se encerrou |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, incluindo a implementação inicial do Micro Game Genetic Lab iniciada na Semana 12; formulário ou modelo do Desafio de Escolha Tecnológica do Módulo 5; modelo do AI Design Log |
| **Cena Unity utilizada** | Continuidade da cena do Micro Game Genetic Lab iniciada na Semana 12, agora adaptada ao problema mais expressivo que consolida o Micro Game: evoluir a forma/parâmetros de uma criatura simples para melhorar sua locomoção (tema fixo "Criaturas Evoluídas" do Módulo 5), em vez do problema tipo "OneMax" da semana anterior. Outros exemplos (ex.: ajustar um pequeno conjunto de parâmetros de uma IA de jogo) podem ilustrar a discussão em aula, mas não substituem o tema fixo na implementação consolidada |
| **Assets** | Nenhum asset de arte adicional necessário; elementos visuais permanecem primitivos simples ou saída em texto/console, com eventual gráfico simples da evolução da aptidão ao longo das gerações |
| **Exemplos** | Curva típica de evolução da melhor aptidão (com saltos e platôs) para diagnóstico de convergência prematura; quadro comparativo de vantagens e limitações dos Algoritmos Genéticos frente a métodos exatos e ao RL (seção 13.9); trecho do esqueleto conceitual de implementação em C# (seção 13.8), apenas como referência estrutural, não como tutorial |
| **Vídeos** | Não é obrigatório vídeo externo; caso disponível, um vídeo curto mostrando neuroevolução em ação (por exemplo, agentes evoluídos por NEAT) pode ilustrar a seção 13.7/13.10, sem substituir a fundamentação já dada na Semana 12 |
| **Jogos para Engenharia Reversa** | Selecionar previamente um jogo comercial com balanceamento perceptível entre unidades, cartas ou builds (por exemplo, um jogo de estratégia, um card game competitivo ou um jogo com geração procedural de fases/mapas), para o quinto momento de Engenharia Reversa do Encontro 2 |

---

## Encontro 1 (1h30)

**Foco:** Aprofundamento da aplicação de Algoritmos Genéticos a um problema mais expressivo — convergência, diversidade, ajuste de parâmetros, aplicações em jogos, ferramentas, e avaliação crítica de vantagens e limitações.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Retomada e transição para um problema mais expressivo | 10 min | Recuperar o Micro Game Genetic Lab da Semana 12 e anunciar o aprofundamento da semana | Revisa brevemente o ciclo de oito etapas e os quatro operadores genéticos (Semana 12); apresenta o problema mais expressivo que consolida o Micro Game — evoluir a forma/parâmetros de uma criatura simples para melhorar sua locomoção (tema fixo "Criaturas Evoluídas") — podendo usar exemplos adicionais (como ajustar parâmetros de uma IA de jogo) apenas para ilustrar a discussão | Relacionam o novo problema ao problema simples resolvido na Semana 12, identificando o que muda na representação e na função de aptidão |
| 2. Convergência, diversidade e ajuste de parâmetros | 25 min | Ensinar a diagnosticar e corrigir convergência prematura em um problema mais exigente | Aprofunda a leitura da curva de aptidão (saltos e platôs, seção 13.3) aplicada ao novo problema; retoma a seção 13.6 para relacionar sintomas de convergência prematura a ajustes de taxa de mutação, pressão seletiva e grau de elitismo | Analisam, em duplas, uma curva de aptidão hipotética com platô longo e propõem um ajuste de parâmetro (mutação, seleção ou elitismo) para retomar a evolução |
| 3. Aplicações de Algoritmos Genéticos em jogos | 20 min | Relacionar os fundamentos a aplicações concretas da indústria e da pesquisa | Apresenta a seção 13.7: balanceamento automático, PCG baseada em busca, evolução de comportamentos e neuroevolução, ajuste de parâmetros de IA e design procedural (incluindo evolução interativa) | Identificam, para cada aplicação apresentada, um exemplo hipotético no contexto do AI Playground de seu próprio grupo |
| 4. Ferramentas: implementação própria, bibliotecas e neuroevolução | 20 min | Situar a implementação própria diante de bibliotecas de terceiros e da neuroevolução | Apresenta a seção 13.8: o esqueleto conceitual da implementação em C# (como referência estrutural, não tutorial), a GeneticSharp como biblioteca de terceiros, e a neuroevolução (NEAT) como ponte com o RL do Módulo 6 | Comparam, em duplas, a implementação própria já realizada na Semana 12 com o uso hipotético de uma biblioteca de terceiros, discutindo o que se ganha e o que se perde |
| 5. Vantagens, limitações e comparação com RL | 15 min | Consolidar a avaliação crítica da técnica | Apresenta a seção 13.9: vantagens (generalidade, exploração global, robustez a ótimos locais) e limitações (ausência de garantia, custo, dependência da função de aptidão); retoma a distinção otimizar × aprender a agir frente ao RL (Módulo 6) | Discutem, em grupo, um problema para o qual um GA seria a ferramenta certa e outro para o qual um método exato seria preferível, justificando cada escolha |

---

## Encontro 2 (1h30)

**Foco:** Consolidação do Micro Game Genetic Lab, Desafio de Escolha Tecnológica do Módulo 5 e quinto momento de Engenharia Reversa.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão das soluções desenvolvidas | 10 min | Verificar o estado da implementação de cada grupo antes da consolidação | Percorre os grupos revisando a implementação inicial do Micro Game Genetic Lab (Semana 12) e o problema mais expressivo definido no Encontro 1 | Apresentam brevemente, em cada grupo, o estado atual da implementação e as dúvidas pendentes |
| 2. Laboratório — consolidação do Micro Game Genetic Lab | 35 min | Concluir a aplicação dos operadores genéticos ao problema mais expressivo | Acompanha os grupos na adaptação da representação, da função de aptidão e dos parâmetros (taxa de mutação, tamanho do torneio, grau de elitismo) ao novo problema, orientando o diagnóstico de eventuais platôs de convergência | Implementam, em grupo, a versão consolidada do Micro Game Genetic Lab, testando diferentes parâmetros e registrando a curva de melhor aptidão e aptidão média ao longo das gerações |
| 3. Discussão técnica | 10 min | Comparar resultados entre grupos e consolidar o aprendizado | Conduz a discussão comparando as curvas de aptidão obtidas pelos grupos, relacionando diferenças de parâmetros a diferenças de convergência | Comparam os resultados obtidos, relacionando decisões de representação, função de aptidão e parâmetros aos resultados observados |
| 4. Desafio de Escolha Tecnológica do Módulo 5 | 20 min | Consolidar a capacidade de justificar tecnicamente uma escolha de otimização | Apresenta um problema de otimização automática (por exemplo, balancear parâmetros de uma arma ou gerar variações de uma fase) e solicita que cada grupo justifique, por escrito, a solução que utilizaria | Elaboram, em grupo, a justificativa do Desafio de Escolha Tecnológica, considerando requisitos, alternativas, limitações e ferramentas disponíveis |
| 5. Engenharia Reversa (5º momento) e encerramento | 15 min | Relacionar otimização automática a um jogo comercial e encerrar a Unidade V | Conduz o quinto momento de Engenharia Reversa, apresentando um jogo comercial com balanceamento ou geração procedural perceptível, e levanta perguntas de discussão; recapitula o encerramento da Unidade V e anuncia a Unidade VI (Aprendizagem e Adaptação) | Analisam o jogo apresentado, levantam hipóteses sobre a arquitetura de balanceamento/geração usada e relacionam as hipóteses aos conceitos de otimização evolutiva estudados |

---

## Micro Game

**Micro Game em desenvolvimento:** Genetic Lab (Módulo 5) — **consolidação**.

**Objetivo pedagógico:** demonstrar, no problema que consolida o tema fixo do Genetic Lab — evoluir a forma/parâmetros de uma criatura simples para melhorar sua locomoção —, que um Algoritmo Genético completo, com representação adequada, função de aptidão bem projetada e os quatro operadores genéticos calibrados, encontra automaticamente boas soluções, evidenciando na prática o equilíbrio entre exploração e *exploitation* e os sintomas de convergência prematura discutidos no Encontro 1.

**Funcionalidades esperadas ao final da Semana 13:**

- representação e função de aptidão adaptadas ao problema de locomoção da criatura, mais expressivo do que o utilizado na Semana 12;
- os operadores de seleção, crossover, mutação e elitismo, com parâmetros ajustados a partir da observação da curva de aptidão;
- evidência registrada (gráfico ou log) da evolução da melhor aptidão e da aptidão média ao longo das gerações, incluindo eventuais ajustes feitos para corrigir convergência prematura;
- Micro Game Genetic Lab funcionalmente consolidado, encerrando o Módulo 5.

**Relação com módulos anteriores:** encerra o Módulo 5 e a Unidade V, aplicando em maior escala o mesmo padrão de implementação própria em C# do Módulo 4 (Minimax com heurística e poda) e reforçando o paralelo, já discutido na Semana 12, entre a função de aptidão e a função de avaliação do Minimax e os mapas de influência (Módulo 3). Prepara a transição para o Módulo 6 (Aprendizagem e Adaptação), no qual a distinção entre otimizar e aprender a agir será revisitada sob a ótica da Aprendizagem por Reforço.

---

## Engenharia Reversa

**5º momento de Engenharia Reversa da disciplina**, previsto no Cronograma para esta semana.

| Campo | Conteúdo |
|---|---|
| **Jogo analisado** | A ser selecionado pelo professor entre jogos com balanceamento perceptível entre unidades, cartas ou builds, ou com geração procedural evidente. A Apostila não traz estudo de caso de algoritmos genéticos — é o único momento do semestre sem caso correspondente no Capítulo 15, e o professor deve dizer isso à turma: a ausência de fonte torna a análise **inteiramente [Inferência]**, o que é, em si, uma lição metodológica |
| **Comportamento observado** | Padrões de equilíbrio entre opções de jogo (nenhuma estratégia claramente dominante) ou variedade e jogabilidade consistente de conteúdo gerado (fases, mapas ou itens) |
| **Perguntas para discussão** | O balanceamento observado é mais compatível com ajuste manual por designers, com otimização automática (possivelmente evolutiva) ou com uma combinação dos dois? Que critérios uma função de aptidão precisaria medir para produzir esse resultado? Que evidências sustentam cada hipótese, e quais permanecem apenas plausíveis? |
| **Relação com os conceitos da semana** | Conecta diretamente as seções 13.7 (aplicações de balanceamento automático e PCG) e 13.10 (estudos de caso, distinguindo fato documentado de análise técnica fundamentada) ao caso analisado, exercitando a mesma cautela metodológica adotada na Apostila |

Conforme a Apostila (seção 13.10) e a orientação já dada no Capítulo 12, o professor deve conduzir a discussão distinguindo claramente **fato documentado** de **inferência plausível**: salvo documentação explícita do estúdio, atribuir o uso de Algoritmos Genéticos a um jogo comercial específico é hipótese, não fato.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C#** | Consolidação do laço evolutivo e dos operadores genéticos, adaptados ao problema mais expressivo definido no Encontro 1 |
| **Unity (cena mínima)** | Continuidade da cena do Micro Game Genetic Lab, hospedando a lógica consolidada e, se pertinente, a exibição da curva de aptidão |

Nenhuma ferramenta oficial da Unity é utilizada para Algoritmos Genéticos: a implementação permanece própria em C#, conforme indicado pelo Cronograma. Bibliotecas de terceiros (GeneticSharp) e a neuroevolução (NEAT) são apresentadas nesta semana apenas como **contextualização** (seção 13.8), para fins de comparação e discussão no Desafio de Escolha Tecnológica — não como exigência de implementação.

---

## Atividade de Laboratório

**Objetivo:** consolidar, em grupo, o Micro Game Genetic Lab aplicado a um problema mais expressivo, ajustando parâmetros a partir do diagnóstico da curva de aptidão, e produzir a justificativa do Desafio de Escolha Tecnológica do Módulo 5.

**Etapas:**

1. Adaptar a representação do cromossomo e a função de aptidão implementadas na Semana 12 ao problema mais expressivo apresentado no Encontro 1.
2. Reexecutar o laço evolutivo, registrando a curva da melhor aptidão e da aptidão média ao longo das gerações.
3. Diagnosticar, a partir da curva obtida, se há sinais de convergência prematura (platô muito longo com pouca diversidade na população).
4. Ajustar, se necessário, a taxa de mutação, o tamanho do torneio de seleção ou o grau de elitismo, e reexecutar, comparando a nova curva com a anterior.
5. Documentar, para o AI Design Log, as alternativas de parâmetros consideradas e a justificativa da configuração final escolhida.
6. Elaborar, em grupo, a resposta ao Desafio de Escolha Tecnológica do Módulo 5, justificando a solução de otimização escolhida para o problema proposto pelo professor.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter o Micro Game Genetic Lab consolidado, com evidência registrada de melhoria da aptidão ao longo das gerações no problema mais expressivo, além da entrega do Desafio de Escolha Tecnológica do Módulo 5 e do AI Design Log correspondente.

---

## Verificação da Aprendizagem

A Semana 13 **encerra o Módulo 5**, e a nota do módulo é lançada ao final desta semana, conforme o Cronograma e os Critérios de Notas. Conforme a Rubrica de Avaliação, o professor deve observar:

- **Compreensão Conceitual** — se o estudante distingue com clareza otimização evolutiva de aprendizagem por interação (RL), relaciona corretamente os operadores genéticos aos seus papéis de exploração e *exploitation*, e situa os Algoritmos Genéticos no panorama das técnicas já estudadas na disciplina;
- **Aplicação Prática** — se a consolidação do Micro Game Genetic Lab reflete corretamente os quatro operadores genéticos aplicados ao problema mais expressivo, com evidência de melhoria da aptidão ao longo das gerações;
- **Tomada de Decisão** — principalmente por meio do Desafio de Escolha Tecnológica do Módulo 5, avaliando se a justificativa apresentada considera requisitos, alternativas, limitações e ferramentas disponíveis;
- **AI Design Log** — se o documento descreve problema, alternativas consideradas, solução escolhida, justificativa, ferramentas utilizadas e limitações de forma clara e coerente.

Os momentos de Engenharia Reversa associados ao Desafio de Escolha Tecnológica são avaliados principalmente pela Compreensão Conceitual e pela Tomada de Decisão, conforme a Rubrica.


**Instrumentos de verificação disponíveis na Apostila.** Antes de recorrer a questões próprias, o professor deve usar o material já pronto e alinhado: os **Exercícios de fixação** ao final do Capítulo 13, e — nas semanas de encerramento de Parte — as **Questões de Revisão**, os **Exercícios Conceituais** e os **Exercícios de Integração** do Encerramento correspondente. Recomenda-se aplicar duas ou três questões na abertura do Encontro 2, como verificação rápida antes do laboratório, e usar o Apêndice C.2 como apoio à discussão técnica. Esse material é a principal fonte de verificação formativa da disciplina, e não deve ficar sem uso.

---

## Entregas

Conforme o Cronograma e a matriz dos Critérios de Notas (item 4), a Semana 13 encerra a Unidade V e o Módulo 5 com **quatro** entregas avaliadas:

- **Micro Game 5 — Genetic Lab consolidado (50%)** — os quatro operadores genéticos aplicados a um problema mais expressivo, com evidência de melhoria da aptidão ao longo das gerações, avaliado pelos critérios de Compreensão Conceitual, Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução;
- **AI Design Log — Micro Game 5 (25%)** — documentando o raciocínio completo do desenvolvimento do Genetic Lab nas Semanas 12 e 13, conforme o modelo dos Modelos de Entrega do Aluno (§1);
- **Desafio de Escolha Tecnológica — Módulo 5 (15%)** — justificativa técnica da solução de otimização escolhida;
- **5º momento de Engenharia Reversa (10%)** — relacionando otimização automática a balanceamento ou geração procedural em um jogo comercial.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Aplicar o problema mais expressivo sem ajustar a representação ou a função de aptidão herdadas da Semana 12, produzindo resultados pouco expressivos ou inválidos | Retomar as seções 13.4 e 13.5, pedindo que o grupo verifique explicitamente se a representação e a função de aptidão continuam adequadas ao novo problema antes de reexecutar o laço evolutivo |
| Não reconhecer sinais de convergência prematura na curva de aptidão, insistindo em parâmetros que já demonstraram estagnação | Retomar o quadro "Na Prática" da seção 13.3 e a Boa Prática da seção 13.6, orientando o grupo a comparar explicitamente a diversidade da população em gerações de platô com gerações de salto |
| Confundir, no Desafio de Escolha Tecnológica, "otimizar" (GA) com "aprender a agir" (RL), propondo a técnica errada para o problema apresentado | Retomar o quadro de Atenção da seção 13.1 e a comparação da seção 13.9, pedindo que o grupo explicite se o problema exige uma configuração fixa (otimização) ou um comportamento que se ajusta continuamente (aprendizagem) |
| No 5º momento de Engenharia Reversa, afirmar categoricamente que um jogo comercial específico "usa Algoritmos Genéticos" sem base documentada | Retomar a seção 13.10 e o quadro de Atenção associado, exigindo que o grupo classifique cada afirmação como fato documentado ou hipótese plausível, com a fonte correspondente |
| Justificar o Desafio de Escolha Tecnológica de forma genérica, sem considerar requisitos, alternativas e limitações específicas do problema proposto | Retomar o modelo do Desafio (Modelos de Entrega do Aluno, §2) e o descritor "Proficiente" da Rubrica no critério Tomada de Decisão, pedindo que o grupo relacione explicitamente cada requisito do problema à escolha feita |

---

## Preparação para a Próxima Semana

Para a Semana 14 (início da Unidade VI — Aprendizagem e Adaptação), o professor deve:

- confirmar que todos os grupos entregaram o Micro Game Genetic Lab consolidado, o Desafio de Escolha Tecnológica do Módulo 5 e o AI Design Log correspondente;
- registrar a nota do Módulo 5, conforme os Critérios de Notas;
- anunciar a transição para a Unidade VI, cuja pergunta norteadora é "Como um agente aprende?", retomando a distinção entre otimizar (Algoritmos Genéticos, Módulo 5) e aprender a agir (Aprendizagem por Reforço, Módulo 6), já antecipada ao longo do Capítulo 13;
- solicitar a leitura prévia da Parte VI, Capítulo 12 da Apostila (Aprendizagem por Reforço), já indicada no Plano de Ensino, caso ainda não tenha sido revisitada pelos estudantes;
- recomendar a antecipação da instalação do ambiente ML-Agents (Python e pacotes), conforme observação do Cronograma para a Semana 14, evitando perda de aula com setup técnico na Semana 15.
