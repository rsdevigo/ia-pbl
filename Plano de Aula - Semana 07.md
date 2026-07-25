# Plano de Aula — Semana 7

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 7 de 17 |
| **Unidade** | Unidade II — Navegação e Busca de Caminhos (Semanas 5–7) |
| **Módulo** | Módulo 2 — Como um agente encontra seu destino? |
| **Tema** | JPS+ e Otimizações de Busca |
| **Pergunta Norteadora** | Como tornar a navegação eficiente em larga escala? |
| **Tipo de semana** | 🔴 Encerramento de módulo (Desafio de Escolha Tecnológica + Engenharia Reversa) |

---

## Objetivos de Aprendizagem

Ao final da Semana 7, o estudante deverá ser capaz de:

1. **Explicar** o problema da simetria de caminhos em grades grandes e uniformes, e por que ele faz o A* clássico desperdiçar exploração em rotas de mesmo custo.
2. **Definir** com precisão os conceitos de vizinho natural, vizinho podado e vizinho forçado, relacionando o surgimento de um vizinho forçado à presença de um obstáculo.
3. **Descrever** o funcionamento do Jump Point Search (JPS) como o mesmo A* — mesma função `f = g + h`, mesma otimalidade — com uma geração de sucessores podada por jump points.
4. **Explicar** o que o JPS+ pré-calcula na tabela de saltos e por que esse pré-processamento o torna mais rápido que o JPS clássico em tempo de busca.
5. **Relacionar** os custos do pré-processamento (memória, tempo de construção, rigidez perante mudanças) à limitação decisiva do JPS+ — a exigência de um mapa estático — e julgar quando essa técnica é ou não apropriada.
6. **Comparar**, de forma criteriosa, A*, JPS/JPS+, pathfinding hierárquico, flow fields e suavização de caminho, identificando o problema específico que cada otimização ataca.
7. **Consolidar**, em grupo, o Micro Game Navigation como entrega do Módulo 2, integrando NavMesh, A* e a discussão comparativa com o JPS+.
8. **Justificar** tecnicamente, por escrito e oralmente, a escolha de uma solução de navegação para um cenário proposto, no Desafio de Escolha Tecnológica do Módulo 2.
9. **Aplicar** o roteiro completo de seis etapas da metodologia de Engenharia Reversa de IA a um jogo comercial com navegação relevante, distinguindo [Documentado], [Inferência] e [Especulação].

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte III, Capítulo 9 da Apostila — JPS+ e Otimizações**, com reutilização da metodologia da **Parte VII, Capítulo 14 — Metodologia de Engenharia Reversa de IA**, já apresentada formalmente na Semana 4:

- o problema: simetria de caminhos em grades grandes, uniformes e abertas, e o desperdício do A* ao explorar rotas redundantes de mesmo custo — seção 9.1;
- fundamentos do Jump Point Search: poda de simetria e canonização de caminhos; vizinhos naturais, podados e forçados; a definição de jump point como nó com vizinho forçado; o procedimento de "pulo" (*jumping*) — seção 9.2 e 9.2.1;
- ênfase conceitual central: o JPS **é o mesmo A***, com a mesma `f = g + h` e a mesma garantia de otimalidade, mudando apenas a geração de sucessores — seção 9.2.1 (quadro de Atenção);
- JPS+ com pré-processamento: a tabela de saltos (distância até o próximo jump point por célula e direção), a troca de varredura por consulta em tempo constante, e o complemento por Goal Bounding — seção 9.2.2;
- os três custos do pré-processamento (memória, tempo de construção, rigidez perante mudanças no mapa) e a exigência de mundo estático como limitação decisiva do JPS+ — seção 9.2.2;
- comparação de desempenho entre A*, JPS e JPS+: ganho de até uma ordem de magnitude em grades abertas, ganho decrescente em mapas labirínticos, ganho marginal em grades pequenas — seção 9.3;
- panorama de outras otimizações da indústria: pathfinding hierárquico (HPA*, dois níveis de busca), pathfinding em blocos e flow fields para multidões de agentes, e suavização de caminho (*string pulling*/*funnel*) — seção 9.4;
- vantagens e limitações consolidadas das técnicas de otimização de busca — seção 9.5;
- aplicações e jogos conhecidos: jogos de estratégia (flow fields, pathfinding hierárquico) e grades estáticas (JPS+) — seção 9.6;
- ferramentas: suavização nativa do NavMesh Agent (*funnel*); ausência de JPS/JPS+ nativo na Unity, por sua representação primária ser a NavMesh irregular; A* Pathfinding Project como alternativa de terceiros para grades — seção 9.7;
- reutilização da metodologia de Engenharia Reversa de IA (roteiro de seis etapas e rótulos [Documentado]/[Inferência]/[Especulação]), já apresentada na seção 14.3 da Apostila e na Semana 4, agora aplicada de forma completa a um segundo caso.

Não deve ser antecipado o conteúdo da Unidade III (Módulo 3 — Decision Trees, Influence Maps, Utility AI): a transição de "como encontrar o destino" para "como escolher a melhor ação" fica para a Semana 8. Também não é objetivo desta semana implementar JPS/JPS+ do zero: por exigir grade uniforme (ausente na NavMesh já adotada no Micro Game) e por a Apostila reservar implementações próprias apenas a casos de valor didático comprovado, o tratamento do JPS+ nesta semana é conceitual e comparativo, não uma nova implementação.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte III, Capítulo 9, completo (seções 9.1 a 9.7); revisão da Parte VII, Capítulo 14, seção 14.3 (roteiro de seis etapas) |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com o Micro Game Navigation evoluído desde a Semana 6; acesso a vídeo ou build do jogo escolhido para o segundo momento de Engenharia Reversa |
| **Cena Unity utilizada** | A mesma cena do Micro Game Navigation (Semanas 5 e 6), agora consolidada como entrega do Módulo 2, sem novos elementos de cenário obrigatórios |
| **Assets** | Nenhum asset adicional; reaproveita-se integralmente o material das Semanas 5 e 6 |
| **Exemplos** | Diagrama de vizinhos naturais, podados e forçados (seção 9.2.1); diagrama comparativo de nós expandidos por A* versus JPS numa grade aberta (seção 9.3); diagrama de suavização de caminho por linha de visão (seção 9.4) |
| **Vídeos** | Recomenda-se, opcionalmente, uma captura ou vídeo demonstrando movimentação de grandes grupos de unidades em um jogo de estratégia, para ilustrar visualmente o conceito de flow field antes da discussão da seção 9.4 |
| **Jogos para Engenharia Reversa** | **StarCraft II** (Blizzard Entertainment, 2010) é sugerido como caso com navegação relevante e observável — deslocamento de grandes grupos de unidades em mapas com obstáculos, contorno dinâmico e recálculo de rota. O professor pode substituir por outro jogo de estratégia ou ação com navegação claramente observável, mantendo a análise estritamente comportamental, conforme a seção 14.4 |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação dos limites de escala do A* e de como o JPS+ os resolve. Comparação com o A* Pathfinding Project (ecossistema de terceiros).

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 5 min | Conectar o A* da Semana 6 ao limite que motiva esta semana | Recapitula que a Semana 6 resolveu a busca ótima (A*), e anuncia a pergunta desta semana: e quando o A*, bem implementado, ainda é lento demais? | Relembram o traço de execução do A* estudado na semana anterior e antecipam, em voz alta, cenários em que a busca ficaria cara (grades grandes, muitos agentes) |
| 2. O problema: simetria de caminhos | 15 min | Apresentar o desperdício do A* em grades grandes e uniformes | Apresenta a seção 9.1: o conceito de simetria de caminhos, o exemplo do "leque" de nós expandidos por A* num campo aberto, e a explosão do problema em grades de larga escala | Discutem, em duplas, por que esse desperdício é pequeno em grafos irregulares (NavMesh) mas grande em grades regulares |
| 3. Vizinhos naturais, podados e forçados | 20 min | Explicar a poda de simetria e a origem do vizinho forçado | Apresenta a seção 9.2.1 com o diagrama de vizinhos naturais, podados e forçados, destacando como um obstáculo "força" uma decisão que não existiria em terreno aberto | Identificam, para um exemplo simples de grade com um obstáculo, qual célula seria um vizinho forçado e por quê |
| 4. Jump points e o procedimento de "pulo" | 15 min | Definir jump point e o mecanismo de salto do JPS | Apresenta a seção 9.2, enfatizando o quadro de Atenção: JPS é o mesmo A*, com a mesma `f = g + h` e a mesma otimalidade, mudando apenas a geração de sucessores | Descrevem, com suas palavras, a diferença entre "expandir vizinho por vizinho" (A*) e "pular até o próximo ponto de decisão" (JPS) |
| 5. JPS+ e a tabela de saltos | 15 min | Explicar o pré-processamento do JPS+ | Apresenta a seção 9.2.2: o cálculo prévio da distância de salto por célula e direção, a troca de varredura por consulta em tempo constante, e a menção ao Goal Bounding | Relacionam a tabela de saltos a uma tabela de consulta já vista em outras disciplinas (cache, tabela pré-computada) |
| 6. Custos do pré-processamento e a exigência de mundo estático | 10 min | Identificar os três custos do JPS+ e sua limitação decisiva | Apresenta os três custos (memória, construção, rigidez) e o Erro Comum da seção 9.2.2 sobre aplicar JPS+ em mundos dinâmicos | Avaliam se o cenário do Micro Game Navigation de cada grupo (mapa fixo ou com obstáculos dinâmicos) favoreceria ou não o uso de JPS+ |
| 7. Comparação de desempenho e outras otimizações | 5 min | Apresentar o panorama de ganho de desempenho e as demais técnicas | Apresenta rapidamente a seção 9.3 (ganho decrescente em mapas labirínticos) e a seção 9.4 (pathfinding hierárquico, flow fields, suavização), reservando aprofundamento para a discussão técnica do Encontro 2 | Registram, para retomada no Encontro 2, qual dessas otimizações parece mais aplicável ao próprio AI Playground |
| 8. Ferramentas: A* Pathfinding Project | 5 min | Comparar a ausência de JPS nativo na Unity com a alternativa de terceiros | Apresenta a seção 9.7: o NavMesh Agent já suaviza caminhos nativamente mas não oferece JPS/JPS+; o A* Pathfinding Project como alternativa de terceiros para grades, com variantes otimizadas e multithreading | Comparam, em voz alta, os cenários em que trocariam a NavMesh por uma solução baseada em grade com A* Pathfinding Project |

---

## Encontro 2 (1h30)

**Foco:** Consolidação do Micro Game Navigation. Desafio de Escolha Tecnológica do Módulo 2. Segundo momento de Engenharia Reversa, em jogo com navegação relevante.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 5 min | Retomar jump points e a limitação do JPS+ antes da prática | Conduz uma discussão breve recuperando o conceito de vizinho forçado e a exigência de mapa estático do JPS+ | Respondem perguntas de verificação oral, relacionando os conceitos ao Micro Game Navigation de cada grupo |
| 2. Consolidação do Micro Game Navigation | 20 min | Finalizar o Micro Game como entrega do Módulo 2 | Acompanha os grupos na revisão final da cena (NavMesh, NavMesh Agent, obstáculo ou destino adicional da Semana 6), verificando robustez e clareza da navegação apresentada | Revisam e ajustam o Micro Game Navigation, preparando-o para a entrega e a discussão técnica do módulo |
| 3. Discussão técnica: quando cada técnica de otimização compensa | 15 min | Consolidar o critério de decisão entre A*, JPS+ e demais otimizações | Conduz a discussão retomando a Boa Prática da seção 9.3 ("medir antes de otimizar") e o Erro Comum da seção 9.5 sobre otimizar sem necessidade real | Argumentam, para o próprio AI Playground, se alguma otimização deste capítulo se justificaria, com base em critérios técnicos e não apenas em sofisticação |
| 4. Desafio de Escolha Tecnológica do Módulo 2 | 20 min | Desenvolver a capacidade de justificar tecnicamente uma escolha de navegação | Apresenta um cenário não idêntico ao Micro Game (por exemplo, um mapa de estratégia grande, aberto e estático, com centenas de unidades buscando caminho simultaneamente) e solicita que cada grupo compare ao menos duas soluções (NavMesh/A*, JPS+, flow field) e justifique a escolhida | Analisam o cenário, comparam alternativas com base em requisitos (escala, dinamismo do mapa, número de agentes) e limitações, e registram a justificativa por escrito |
| 5. Segundo momento de Engenharia Reversa | 20 min | Aplicar o roteiro completo de seis etapas a um caso de navegação | Apresenta trechos de vídeo do jogo escolhido (por exemplo, *StarCraft II*), conduz a definição do problema e a observação orientada ao comportamento de navegação, e orienta a formulação, validação e documentação das hipóteses, reforçando os rótulos [Documentado]/[Inferência]/[Especulação] | Aplicam as seis etapas do roteiro (definição do problema, coleta, registro, hipóteses, validação, documentação) ao comportamento de navegação observado, com nível de confiança explícito para cada afirmação |
| 6. Encerramento do Módulo 2 | 10 min | Fechar o módulo e indicar o caminho da próxima semana | Recapitula a evolução de Grafos (Semana 5) a A* (Semana 6) e JPS+ (Semana 7), confirma as entregas da semana e anuncia que a Semana 8 abre a Unidade III com o checkpoint do AI Playground | Registram pendências das três entregas do módulo para finalização até o prazo definido pelo professor |

---

## Micro Game

**Micro Game em desenvolvimento:** Navigation (Módulo 2) — **consolidação final**.

**Objetivo pedagógico:** demonstrar como um agente encontra seu destino, evoluindo da representação do espaço em grafo (Semana 5) à busca ótima com A* (Semana 6) e à compreensão crítica de quando otimizações como o JPS+ se justificam (Semana 7), consolidando o Módulo 2 do AI Playground.

**Funcionalidades esperadas ao final da Semana 7:**

- a cena do Micro Game Navigation, com NavMesh e NavMesh Agent funcionais, incluindo o destino ou obstáculo adicional introduzido na Semana 6;
- capacidade do grupo de explicar a navegação resultante em termos de grafo, heurística e função `f = g + h`, sem exigência de implementação própria de JPS/JPS+;
- capacidade do grupo de justificar, com critérios técnicos (escala, dinamismo do mapa, número de agentes), se e quando uma otimização como JPS+, pathfinding hierárquico ou flow field se aplicaria ao próprio AI Playground;
- documentação consolidada do raciocínio do módulo no AI Design Log.

**Relação com módulos anteriores:** encerra a trajetória iniciada na Semana 5 (Grafos e NavMesh) e continuada na Semana 6 (A*), demonstrando a mesma navegação sob complexidade progressiva de fundamentação teórica, sem exigir nova implementação de código nesta semana. É esta versão consolidada que compõe o Micro Game entregável do Módulo 2, avaliado conforme os Critérios de Notas da disciplina.

---

## Engenharia Reversa

**Segundo momento formal de Engenharia Reversa da disciplina**, conforme o Cronograma, aplicando o roteiro completo de seis etapas da seção 14.3 da Apostila.

**Jogo analisado:** *StarCraft II* (Blizzard Entertainment, 2010), sugerido como caso com navegação relevante e amplamente observável — deslocamento de grandes grupos de unidades por mapas com obstáculos, terreno irregular e combate dinâmico. O professor pode substituir por outro jogo de estratégia ou ação com navegação claramente observável, mantendo a análise estritamente comportamental.

**Comportamento observado:** deslocamento coordenado de um grupo numeroso de unidades até um ponto de destino comum, incluindo contorno de obstáculos, recálculo de rota diante de mudanças no terreno e comportamento das unidades ao colidir ou se aglomerar.

**Perguntas para discussão:**

- As unidades parecem calcular uma rota individual cada uma, ou existe algum indício de que compartilham uma solução comum de navegação (por exemplo, todas fluindo na mesma direção geral perto do destino)?
- Como as unidades reagem a um obstáculo inesperado no meio do trajeto? A reação sugere recálculo local ou uma estratégia de navegação mais ampla?
- O comportamento observado é mais compatível com uma busca ponto a ponto (A*/JPS+) por unidade ou com uma técnica de navegação de multidões, como discutido na seção 9.4 da Apostila?
- Que evidências sustentam a hipótese levantada, e com que nível de confiança? O que é [Documentado] (por exemplo, entrevistas e materiais técnicos publicados sobre a engine) e o que permanece [Inferência] ou [Especulação]?

**Relação com os conceitos da semana:** aplica o roteiro completo de seis etapas (definição do problema, coleta de evidências, registro das observações, formulação de hipóteses, validação e documentação) da metodologia apresentada na Semana 4, exercitando agora o vocabulário de navegação em larga escala construído no Capítulo 9 — simetria de caminhos, otimizações e, especialmente, o conceito de flow field como alternativa a buscas individuais quando muitos agentes compartilham destino.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **AI Navigation / NavMesh Agent** (oficial) | Consolidado como base do Micro Game Navigation; sua suavização nativa de caminho (*funnel*) é usada como referência ao discutir a seção 9.4 |
| **A\* Pathfinding Project** (terceiros) | Retomado da Semana 6 e aprofundado nesta semana como a alternativa do ecossistema Unity que oferece suporte a grades e otimizações comparáveis ao JPS+, sem uso prático obrigatório |
| **JPS/JPS+** | Tratado exclusivamente em nível conceitual e comparativo; não há ferramenta oficial da Unity nem implementação própria prevista nesta semana |

---

## Atividade de Laboratório

**Objetivo:** consolidar o Micro Game Navigation como entrega do Módulo 2, aplicar o Desafio de Escolha Tecnológica a um cenário de navegação em larga escala e concluir o segundo momento de Engenharia Reversa.

**Etapas:**

1. Revisar a cena do Micro Game Navigation (Semanas 5 e 6), verificando se a NavMesh, o NavMesh Agent e o destino/obstáculo adicional funcionam corretamente e de forma estável.
2. Em grupo, documentar brevemente por que a solução adotada (NavMesh + A* interno) foi suficiente para o Micro Game, sem necessidade de JPS+, pathfinding hierárquico ou flow field.
3. Analisar o cenário do Desafio de Escolha Tecnológica (mapa grande, aberto e estático, com centenas de unidades buscando caminho simultaneamente), comparar ao menos duas soluções possíveis e registrar a justificativa por escrito.
4. Aplicar as seis etapas do roteiro de Engenharia Reversa ao comportamento de navegação observado no jogo escolhido, registrando evidências, hipóteses, validação e documentação com os rótulos de confiança apropriados.
5. Reunir as três entregas do módulo (Micro Game consolidado, Desafio de Escolha Tecnológica, Engenharia Reversa) junto ao AI Design Log do Módulo 2.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter o Micro Game Navigation consolidado como entrega do Módulo 2, uma justificativa técnica registrada para o cenário do Desafio de Escolha Tecnológica, e o registro completo das seis etapas de Engenharia Reversa aplicadas ao jogo escolhido.

---

## Verificação da Aprendizagem

A Semana 7 **encerra formalmente o Módulo 2**, e a verificação da aprendizagem gera nota, conforme os Critérios de Notas da disciplina. O professor deve aplicar a Rubrica de Avaliação aos quatro instrumentos previstos:

- **Micro Game (consolidação)** — avaliado principalmente por Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução, observando se a navegação funciona corretamente e se o grupo compreende a arquitetura por trás do NavMesh Agent (peso 50% do módulo);
- **AI Design Log** — avaliado pelo critério de AI Design Log, verificando se o documento registra problema, alternativas consideradas ao longo do módulo (grafos, A*, JPS+ e demais otimizações), solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras (peso 25% do módulo);
- **Desafio de Escolha Tecnológica** — avaliado principalmente por Tomada de Decisão, apoiado por Compreensão Conceitual, verificando se o grupo comparou alternativas viáveis (NavMesh/A*, JPS+, flow field) e justificou tecnicamente a escolha para o cenário de larga escala proposto (peso 15% do módulo);
- **Engenharia Reversa** — avaliado por Compreensão Conceitual e Tomada de Decisão, verificando a qualidade das hipóteses formuladas sobre a navegação observada em *StarCraft II* (ou jogo equivalente) e o uso correto dos rótulos [Documentado]/[Inferência]/[Especulação] (peso 10% do módulo).

A nota do Módulo 2 compõe 11,67% da nota final do semestre, conforme os Critérios de Notas. O professor deve registrar e comunicar aos estudantes a nota obtida em cada instrumento e a nota consolidada do módulo, conforme recomendado pela Rubrica.

---

## Entregas

Conforme o Cronograma, esta semana encerra o Módulo 2 com três entregas:

- **Desafio de Escolha Tecnológica (Módulo 2)** — justificativa escrita comparando ao menos duas alternativas de navegação para o cenário de larga escala apresentado no Encontro 2;
- **AI Design Log — Micro Game 2** — documento contendo problema, requisitos, alternativas consideradas (grafos e representação do espaço, A*, JPS+ e demais otimizações), solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras, conforme especificado no CLAUDE.md do projeto;
- **2º momento de Engenharia Reversa** — registro completo das seis etapas do roteiro aplicado a *StarCraft II* (ou ao jogo escolhido pelo professor).

O Micro Game Navigation, consolidado nesta semana, permanece no AI Playground de cada grupo como base para os módulos seguintes.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir o JPS com um algoritmo diferente do A*, achando que ele troca otimalidade por velocidade | Retomar o quadro de Atenção da seção 9.2.1: o JPS mantém a mesma `f = g + h` e a mesma garantia de otimalidade; apenas a geração de sucessores muda |
| Não perceber que o vizinho forçado depende da presença de um obstáculo, tratando qualquer vizinho não-podado como forçado | Retomar a seção 9.2.1 e pedir que o grupo identifique, num exemplo com e sem obstáculo, a diferença entre vizinho natural e vizinho forçado |
| Recomendar JPS+ para o cenário do Desafio de Escolha Tecnológica sem considerar se o mapa é estático ou dinâmico | Retomar o Erro Comum da seção 9.2.2 e exigir, na justificativa escrita, uma resposta explícita sobre a dinâmica do mapa proposto |
| Tratar toda otimização de pathfinding como sempre desejável, sem considerar seu custo de implementação e manutenção | Retomar a Boa Prática e o quadro de Atenção da seção 9.5: otimização é resposta a um problema medido, não um troféu a colecionar |
| Na Engenharia Reversa, confundir navegação individual (A*/JPS+) com navegação de multidões (flow field), sem justificar a distinção pela evidência observada | Retomar a seção 9.4 e pedir que o grupo aponte, no vídeo analisado, o sinal específico (por exemplo, unidades fluindo em direção comum) que sustenta cada hipótese |

---

## Preparação para a Próxima Semana

Para a Semana 8 (Checkpoint do AI Playground — abertura da Unidade III), o professor deve:

- garantir que as três entregas do Módulo 2 (Desafio de Escolha Tecnológica, AI Design Log, Engenharia Reversa) estejam recebidas e avaliadas antes do início da Semana 8, registrando a nota do módulo conforme os Critérios de Notas;
- confirmar que todos os grupos possuem, ao final da Semana 7, o Micro Game Navigation consolidado no AI Playground, encerrando o Módulo 2;
- preparar os critérios de avaliação do checkpoint da Semana 8, que privilegia os critérios de Comunicação Técnica e Evolução ao Longo do Semestre, conforme a Rubrica e os Critérios de Notas (peso de 10% na nota final);
- anunciar a transição de unidade: da pergunta "como um agente encontra seu destino?" para "como um NPC escolhe sua melhor ação?", que abre o Módulo 3 (Decision Trees, Influence Maps, Utility AI) após o checkpoint;
- não é necessária instalação ou configuração adicional de ferramentas nesta transição: a Semana 8 é dedicada à apresentação intermediária do progresso, sem novo conteúdo teórico.
