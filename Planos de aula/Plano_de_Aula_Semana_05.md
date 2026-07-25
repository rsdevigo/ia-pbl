# Plano de Aula — Semana 5

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 5 de 17 |
| **Unidade** | Unidade II — Navegação e Busca de Caminhos (Semanas 5–7) |
| **Módulo** | Módulo 2 — Como um agente encontra seu destino? |
| **Tema** | Grafos e Representação do Espaço |
| **Pergunta Norteadora** | Como um agente encontra seu destino? (parte 1) |
| **Tipo de semana** | 🔵 Semana regular (fundamentação e desenvolvimento do Micro Game) |

---

## Objetivos de Aprendizagem

Ao final da Semana 5, o estudante deverá ser capaz de:

1. **Diferenciar** busca de caminho (*pathfinding*) de direção/locomoção (*steering*), explicando por que são problemas distintos e complementares.
2. **Definir** os quatro elementos de um grafo de navegação — vértice, aresta, peso e direção — e **exemplificá-los** com situações concretas de jogos.
3. **Explicar** os conceitos de custo de um caminho, conectividade e representação em memória (lista de adjacência versus matriz de adjacência), justificando por que a lista de adjacência é a escolha dominante em pathfinding.
4. **Comparar** as três representações espaciais estudadas — grades, waypoints e malhas de navegação (NavMesh) — quanto ao que cada nó representa, à forma de obtenção do grafo, ao custo de memória e à facilidade de atualização dinâmica.
5. **Relacionar** os componentes do pacote AI Navigation da Unity (NavMesh Surface, NavMesh Agent, NavMesh Modifiers/Areas, Off-Mesh Links) aos conceitos de grafo estudados nesta semana.
6. **Configurar**, em grupo, a primeira NavMesh do Micro Game Navigation, iniciando a transição do Módulo 1 (decisão) para o Módulo 2 (navegação) do AI Playground.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte III, Capítulo 7 da Apostila — Grafos e Representação do Espaço**:

- o problema: como um algoritmo de busca "enxerga" o espaço navegável; distinção entre busca de caminho (rota global) e direção/locomoção (movimento local) — seção 7.1;
- fundamentos de teoria dos grafos aplicados a jogos: vértices/nós, arestas, pesos (grafos ponderados e não ponderados) e grafos direcionados versus não direcionados — seção 7.2.1;
- custo de um caminho como soma dos custos das arestas; conectividade e componentes conexos; representação em memória (lista de adjacência versus matriz de adjacência) e grafos implícitos — seção 7.2.2;
- representações espaciais: grades (conectividade-4 e conectividade-8, custo diagonal, *corner cutting*) — seção 7.3.1; grafos de waypoints (linha de visão, autoria manual, limitações de "trilhos") — seção 7.3.2; malhas de navegação/NavMesh (polígonos como nós, geração automática por *baking*, parâmetros de agente) — seção 7.3.3;
- ferramentas: o pacote oficial **AI Navigation** da Unity — NavMesh Surface, NavMesh Agent, NavMesh Modifiers/Areas e Off-Mesh Links, relacionados aos conceitos de grafo, custo e direção — seção 7.4;
- panorama comparativo de ferramentas de terceiros — **A\* Pathfinding Project** e **Recast & Detour** — apresentado apenas como referência, sem uso prático nesta semana — seção 7.5.

Não deve ser antecipado o algoritmo A\* (Capítulo 8): esta semana trata exclusivamente da **representação** do espaço, não da **busca** sobre essa representação. Também não deve ser aprofundada, nesta semana, a configuração fina de parâmetros de *baking* além do necessário para uma primeira NavMesh funcional — o Capítulo 9 (JPS+ e otimizações) e o refinamento prático ficam para as semanas seguintes.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte III, Capítulo 7, completo (seções 7.1 a 7.5) |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com o Micro Game NPC Decision (Módulo 1) já consolidado; pacote **AI Navigation** instalado em cada projeto |
| **Cena Unity utilizada** | Nova cena, dedicada ao Micro Game Navigation, distinta da cena do NPC Decision, contendo geometria de teste simples (duas salas, um corredor e alguns obstáculos, por exemplo colunas ou caixas) adequada ao bake de uma NavMesh |
| **Assets** | Geometria primitiva (planos, cubos) para compor o cenário de teste; nenhum asset de arte adicional é necessário |
| **Exemplos** | Diagrama de anatomia de um grafo (vértices, arestas, pesos, direção — seção 7.2.1); diagrama comparativo de grade com conectividade-4 e conectividade-8 (seção 7.3.1); diagrama de grafo de waypoints (seção 7.3.2); diagrama de malha de navegação e seu grafo de polígonos (seção 7.3.3) |
| **Vídeos** | Recomenda-se, opcionalmente, um vídeo curto de bake de NavMesh no editor da Unity para apoiar a demonstração do Encontro 2 |
| **Jogos para Engenharia Reversa** | Não aplicável nesta semana — a Semana 5 não prevê momento de Engenharia Reversa, conforme o Cronograma |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação de representação do espaço de jogo em grafos, base conceitual antes de qualquer algoritmo de busca.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e transição de unidade | 5 min | Encerrar a Unidade I e abrir a Unidade II | Recapitula o encerramento do Módulo 1 na Semana 4 e anuncia a nova pergunta da unidade: "como um agente encontra seu destino?", situando a navegação como um problema novo, não uma continuação da decisão | Relacionam a nova pergunta ao ciclo Sentir → Pensar → Agir: a decisão já tomada agora precisa ser executada como deslocamento |
| 2. O problema: pathfinding vs. steering | 10 min | Distinguir busca de caminho de direção/locomoção | Apresenta a seção 7.1: por que mover em linha reta falha diante de obstáculos; diferencia formalmente busca de caminho (rota global) de direção/locomoção (movimento local) | Identificam, em exemplos de jogos conhecidos, qual parte do movimento é rota global e qual é ajuste local |
| 3. Fundamentos de grafos | 15 min | Definir vértice, aresta, peso e direção | Apresenta a seção 7.2.1 com o diagrama de anatomia de um grafo, incluindo grafos ponderados/não ponderados e grafos direcionados/não direcionados | Identificam, em um mapa simples fornecido pelo professor, os vértices, as arestas e ao menos uma conexão direcionada plausível (por exemplo, uma queda de plataforma) |
| 4. Custo, conectividade e representação em memória | 10 min | Explicar custo de caminho, conectividade e lista de adjacência | Apresenta a seção 7.2.2: custo de um caminho como soma de arestas, componentes conexos e a preferência pela lista de adjacência em grafos esparsos | Discutem por que checar a conectividade antes de buscar um caminho evita processamento desperdiçado |
| 5. Grades e grafos de células | 15 min | Explicar grades e o problema do custo diagonal | Apresenta a seção 7.3.1, com o diagrama comparativo de conectividade-4 e conectividade-8, o custo diagonal (√2 ≈ 1,41) e o problema de *corner cutting* | Calculam, para um pequeno exemplo de grade, o custo total de um caminho com passos diagonais e comparam oralmente com o custo que teriam se todos os passos fossem tratados como ortogonais (economia de tempo em relação a calcular dois caminhos completos) |
| 6. Waypoints | 10 min | Explicar grafos de waypoints e suas limitações | Apresenta a seção 7.3.2: pontos posicionados manualmente, arestas por linha de visão, vantagens de controle autoral e a limitação de movimento "amarrado aos trilhos" | Relacionam a descrição de NPCs "sobre trilhos invisíveis" de jogos antigos ao funcionamento de um grafo de waypoints |
| 7. Malhas de navegação (NavMesh) | 15 min | Explicar a NavMesh como representação de áreas | Apresenta a seção 7.3.3: polígonos convexos como nós, arestas por borda compartilhada, geração automática por *baking* e os parâmetros de agente (raio, altura, inclinação máxima, altura de degrau) | Comparam, em grupo, por que a NavMesh resolve a limitação de "amarrado aos trilhos" dos waypoints sem o custo de memória de uma grade fina |
| 8. Síntese comparativa e fechamento | 10 min | Consolidar as três representações e preparar o Encontro 2 | Conduz a construção coletiva de uma tabela comparativa (grades × waypoints × NavMesh) quanto ao que é o nó, como o grafo é obtido, custo de memória e atualização dinâmica; anuncia que o Encontro 2 apresentará a ferramenta oficial da Unity e iniciará o Micro Game Navigation | Registram a tabela comparativa como referência de estudo e organizam-se em grupo para o encontro seguinte |

---

## Encontro 2 (1h30)

**Foco:** Início do Micro Game Navigation: configuração da NavMesh do Unity AI Navigation, relacionando a malha gerada ao grafo estudado na teoria.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 5 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando vértice, aresta, peso, direção e as três representações espaciais | Respondem perguntas de verificação oral, relacionando cada conceito a um termo que verão na ferramenta |
| 2. Ferramentas oficiais: AI Navigation | 15 min | Mostrar como os conceitos aparecem no pacote oficial da Unity | Apresenta a seção 7.4: NavMesh Surface e o processo de *baking*; NavMesh Agent como usuário da malha; NavMesh Modifiers/Areas como materialização dos pesos de aresta; Off-Mesh Links como arestas adicionais, muitas vezes direcionadas | Relacionam cada componente apresentado ao conceito correspondente da teoria (nó, aresta, peso, direção) |
| 3. Panorama de ferramentas de terceiros | 5 min | Situar alternativas sem aprofundar seu uso | Cita brevemente o A\* Pathfinding Project e o Recast & Detour (seção 7.5), reforçando que a escolha da ferramenta deve seguir a escolha da representação, não o contrário | Registram os nomes das ferramentas de terceiros como referência para o Capítulo 8 |
| 4. Demonstração de bake de NavMesh | 15 min | Mostrar ao vivo a geração de uma malha | Demonstra, na cena de teste, a adição de um NavMesh Surface, a parametrização de Agent Radius/Height/Max Slope/Step Height e a execução do bake, destacando o recuo da malha em relação às paredes | Observam a demonstração e identificam visualmente os polígonos gerados como nós do grafo |
| 5. Implementação guiada: cena e bake do Micro Game Navigation | 35 min | Criar a primeira NavMesh de cada grupo | Acompanha os grupos na preparação da própria cena de teste (salas, corredor, obstáculos), na configuração do NavMesh Surface e na execução do bake; orienta a adição de um NavMesh Agent a um NPC de teste, com um destino simples definido em código ou por um ponto fixo na cena | Constroem a cena de teste, configuram e executam o bake da NavMesh, e adicionam um NavMesh Agent que se desloca até um destino definido |
| 6. Testes e ajustes | 10 min | Verificar se a malha e o agente funcionam como esperado | Circula entre os grupos, verificando se a malha cobre corretamente a área navegável e se o agente chega ao destino sem atravessar obstáculos | Testam o deslocamento do agente, ajustando parâmetros de bake caso a malha apresente buracos ou cubra áreas indevidas |
| 7. Fechamento e transição | 5 min | Preparar a ponte para a Semana 6 | Recapitula a correspondência polígono = nó / borda compartilhada = aresta, e anuncia que a Semana 6 introduzirá o algoritmo A\*, comparando-o à busca interna já usada pelo NavMesh Agent | Registram dúvidas e organizam-se para a leitura prévia do Capítulo 8 |

---

## Micro Game

**Micro Game em desenvolvimento:** Navigation (Módulo 2) — **início**.

**Objetivo pedagógico:** demonstrar como um agente encontra seu destino, começando pela representação do espaço navegável em NavMesh, antes de qualquer algoritmo de busca ser estudado formalmente.

**Funcionalidades esperadas ao final da Semana 5:**

- uma cena própria de teste, com salas, corredor e obstáculos simples;
- uma NavMesh gerada por *baking*, com parâmetros de agente (raio, altura, inclinação máxima, altura de degrau) definidos e justificados pelo grupo;
- um NavMesh Agent associado a um NPC de teste, capaz de se deslocar até um destino simples (ponto fixo ou definido em código), sem customização adicional de busca;
- capacidade do grupo de apontar, na malha gerada, a correspondência entre polígono e nó do grafo, e entre borda compartilhada e aresta.

**Relação com módulos anteriores:** abre a Unidade II e o Módulo 2 do AI Playground, distinto do Módulo 1 (decisão de NPC), mas reaproveitando a familiaridade com organização de cena e scripting em C# já consolidada nas Semanas 1 a 4. O Micro Game Navigation, nesta primeira versão, utiliza a busca interna do NavMesh Agent como caixa-preta; a Semana 6 abrirá essa caixa-preta ao apresentar o algoritmo A\* que a sustenta.

---

## Engenharia Reversa

Não há momento de Engenharia Reversa previsto para a Semana 5, conforme o Cronograma — os momentos formais ocorrem apenas nas semanas de encerramento de módulo (🔴), e o segundo momento da disciplina está previsto para a Semana 7, ao final do Módulo 2.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **AI Navigation / NavMesh** (oficial) | Construção da primeira NavMesh do Micro Game Navigation: NavMesh Surface, parâmetros de agente e bake; NavMesh Agent para deslocamento até um destino |
| **A\* Pathfinding Project / Recast & Detour** (terceiros) | Apresentados apenas como panorama comparativo (seção 7.5 da Apostila), sem uso prático nesta semana |

---

## Atividade de Laboratório

**Objetivo:** configurar a primeira NavMesh do Micro Game Navigation e verificar que um agente consegue percorrer a malha até um destino, relacionando a malha gerada ao grafo estudado na teoria.

**Etapas:**

1. Preparar, em cada projeto, uma cena de teste com salas, corredor e obstáculos simples (blocos ou colunas).
2. Adicionar um NavMesh Surface à cena e definir os parâmetros de agente (Agent Radius, Agent Height, Max Slope, Step Height), justificando os valores escolhidos.
3. Executar o bake e observar visualmente a malha gerada, verificando a cobertura da área navegável e o recuo em relação às paredes.
4. Adicionar um NavMesh Agent a um NPC de teste e definir um destino simples, testando se o deslocamento ocorre sem atravessar obstáculos.
5. Em grupo, apontar na malha gerada a correspondência entre polígono e nó do grafo, e entre borda compartilhada e aresta, registrando essa relação por escrito ou em diagrama.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma NavMesh funcional no Micro Game Navigation, com um agente se deslocando corretamente até um destino de teste, e deve ser capaz de explicar a correspondência entre a malha gerada e o grafo estudado na teoria.

---

## Verificação da Aprendizagem

O Módulo 2 se encerra formalmente apenas na Semana 7, quando ocorrem o Desafio de Escolha Tecnológica, o AI Design Log e a Engenharia Reversa do módulo. A verificação nesta semana é, portanto, **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes definem corretamente vértice, aresta, peso e direção, e se comparam com propriedade as três representações espaciais (critério **Compreensão Conceitual** da Rubrica);
- observação da implementação guiada no Encontro 2, verificando se a NavMesh foi gerada corretamente e se o agente se desloca sem atravessar obstáculos (primeiro indício do critério **Aplicação Prática**, formalmente avaliado na consolidação do Micro Game na Semana 7);
- discussão da correspondência entre polígono/nó e borda/aresta, avaliando se os grupos relacionam corretamente a ferramenta aos fundamentos teóricos (indício inicial do critério **Uso da Unity e do Ecossistema**);
- circulação entre os grupos durante a implementação guiada, observando a organização da cena e dos parâmetros de bake (indício inicial do critério **Qualidade Técnica da Solução**).

Nenhuma nota é atribuída nesta semana, conforme os Critérios de Notas da disciplina, que vinculam a composição da nota aos módulos encerrados nas Semanas 4, 7, 9, 11, 13 e 16, ao checkpoint da Semana 8 e à apresentação final da Semana 17.

---

## Entregas

Não há entrega formal prevista para a Semana 5, conforme o Cronograma.

A NavMesh e o agente básico implementados nesta semana permanecem com os grupos, para evolução na Semana 6 (introdução do algoritmo A\* e comparação com a busca interna do NavMesh Agent) e consolidação na Semana 7, quando o Micro Game Navigation passa a compor as entregas do Módulo 2 (Desafio de Escolha Tecnológica, AI Design Log e Engenharia Reversa).

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir busca de caminho (pathfinding) com direção/locomoção (steering), tratando-os como o mesmo problema | Retomar o Erro Comum da seção 7.1 e pedir que o grupo identifique, num exemplo de jogo, qual parte é rota global e qual é ajuste local |
| Atribuir custo igual (1,0) a passos ortogonais e diagonais numa grade, subestimando o efeito desse erro | Retomar o Atenção da seção 7.3.1 e pedir que o grupo calcule manualmente o custo de dois caminhos alternativos com e sem o ajuste do custo diagonal |
| Confundir o papel do nó em cada representação (célula, ponto ou polígono), tratando-os como conceitos diferentes em vez de variações de um mesmo papel abstrato | Retomar o Atenção da seção 7.2, reforçando que "nó" é sempre um lugar no grafo, independentemente do objeto geométrico que o representa |
| Configurar o Agent Radius/Height de forma incompatível com a geometria da cena, gerando uma NavMesh com buracos ou cobertura incorreta | Orientar o grupo a reduzir a escala do problema (testar em uma cena mais simples) e comparar visualmente a malha antes e depois do ajuste dos parâmetros, relacionando ao Erro Comum da seção 7.3.3 sobre malhas construídas para um agente específico |
| Esquecer de verificar a conectividade da NavMesh, tentando mover um agente para uma área isolada por um obstáculo | Retomar a Boa Prática da seção 7.2.2 sobre checar componentes conexos antes de disparar uma busca cara, aplicando-a de forma concreta ao caso testado |

---

## Preparação para a Próxima Semana

Para a Semana 6 (Busca de Caminhos com A\*), o professor deve:

- solicitar a leitura prévia do Capítulo 8 da Apostila (Busca de Caminhos com A\*);
- garantir que todos os grupos possuam, ao final da Semana 5, uma NavMesh funcional e um NavMesh Agent se deslocando corretamente até um destino no Micro Game Navigation;
- preparar previamente um exemplo de implementação própria simplificada de A\* em C#, a ser demonstrado na Semana 6 para tornar visível o que a NavMesh resolve internamente;
- não é necessária nenhuma instalação ou configuração adicional de ferramentas: a Semana 6 dá continuidade ao uso do pacote AI Navigation já iniciado nesta semana, complementado pela implementação própria de A\* para fins comparativos.
