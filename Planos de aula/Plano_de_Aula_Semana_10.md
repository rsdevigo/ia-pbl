# Plano de Aula — Semana 10

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 10 de 17 |
| **Unidade** | Unidade IV — Busca Adversarial (Semanas 10–11) |
| **Módulo** | Módulo 4 — Como derrotar um adversário inteligente? |
| **Tema** | Minimax e Busca Adversarial |
| **Pergunta Norteadora** | Como derrotar um adversário inteligente? (parte 1) |
| **Tipo de semana** | 🔵 Semana regular (fundamentação e desenvolvimento do Micro Game) — abertura da Unidade IV |

---

## Objetivos de Aprendizagem

Ao final da Semana 10, o estudante deverá ser capaz de:

1. **Explicar** por que jogar contra um oponente racional exige uma abordagem diferente das técnicas estudadas nos Módulos 1 a 3, nas quais o ambiente não planeja estrategicamente contra o agente.
2. **Diferenciar** ambientes cooperativos, reativos e competitivos, situando corretamente exemplos de jogos em cada categoria e reconhecendo que apenas o ambiente competitivo exige busca adversarial.
3. **Definir** jogo de soma zero e justificar por que essa propriedade permite ao Minimax usar uma única função de valor, medida do ponto de vista de um dos jogadores.
4. **Identificar** os elementos da árvore de jogo — estado, ação, profundidade, fator de ramificação, utilidade e função de avaliação — e diferenciar com precisão utilidade (exata, em folhas terminais) de função de avaliação (estimada, em nós não-terminais).
5. **Descrever** a regra de propagação do Minimax nos nós MAX e MIN, explicando por que a jogada escolhida corresponde ao melhor resultado garantido no pior caso, e não ao maior valor absoluto da árvore.
6. **Executar manualmente** o algoritmo Minimax em uma árvore de jogo pequena, calculando o valor de cada nó e identificando a jogada ótima na raiz.
7. **Explicar** o conceito de profundidade limitada e de horizonte de busca, reconhecendo o efeito horizonte como uma limitação estrutural da busca, não um erro de implementação.
8. **Justificar** por que não existe solução oficial da Unity equivalente ao Minimax, e **iniciar**, em grupo, a implementação própria em C# do Micro Game Board Game AI para um jogo de tabuleiro simples.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte V, Capítulo 11 da Apostila — Minimax e Busca Adversarial** (seções 11.1 a 11.3, com o exemplo do jogo da velha da seção 11.6):

- o problema: jogar bem contra um oponente racional que antecipa as próprias jogadas para nos prejudicar, e por que avaliar uma jogada apenas pelo que ela faz "agora" é insuficiente — seção 11.1;
- tomada de decisão adversarial: maximizar supondo que o adversário minimizará, sempre considerando o pior desdobramento possível de cada jogada — seção 11.1;
- a distinção entre ambientes cooperativos, reativos e competitivos, situando as técnicas dos Módulos 1 a 3 no território reativo/cooperativo e o Minimax exclusivamente no competitivo — seção 11.1;
- fundamentos: jogos de soma zero (por que uma única função de valor basta) e jogos por turnos com informação perfeita — seção 11.2;
- a árvore de jogo e seus elementos: raiz, ramos (ações), nós filhos (estados), níveis alternados entre os jogadores, e folhas (utilidade) — seção 11.2;
- profundidade, *ply* e fator de ramificação (*b*), e a explosão combinatória *b^d* como o problema central que toda a engenharia do Minimax prático enfrenta — seção 11.2;
- utilidade (valor exato de estados terminais) versus função de avaliação (estimativa em nós não-terminais), como conceito introdutório — sem aprofundar a construção de heurísticas ponderadas, que fica para a Semana 11 — seção 11.2;
- o algoritmo Minimax: jogadores MAX e MIN, a regra de propagação (máximo nos nós MAX, mínimo nos nós MIN), a construção recursiva da árvore de busca em profundidade, e a escolha da jogada de melhor resultado garantido no pior caso — seção 11.3;
- camadas MAX e MIN, a distinção entre jogada (rodada) e *ply* (meia-rodada) — seção 11.3.1;
- profundidade da busca como principal controle de custo e qualidade, e a ideia geral de aprofundamento iterativo — seção 11.3.2;
- horizonte de busca e efeito horizonte, como limitação estrutural da busca com profundidade limitada — seção 11.3.3;
- exemplo consolidador: o jogo da velha como caso em que o Minimax é executado por completo, sem heurística nem poda, servindo de demonstração central do Encontro 1 — seção 11.6.

Não deve ser antecipado o conteúdo da Seção 11.3.4 (construção detalhada de funções heurísticas de avaliação ponderadas) nem da Seção 11.4 (poda alfa-beta e ordenação de jogadas): ambos ficam reservados para a Semana 11, quando o Minimax precisar se tornar viável em profundidade maior. A Seção 11.5 (Monte Carlo Tree Search) é conteúdo de aprofundamento não previsto no Cronograma desta disciplina e não deve ser apresentada.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte V, Capítulo 11, seções 11.1 a 11.3 (incluindo 11.3.1 a 11.3.3) e a subseção do jogo da velha na seção 11.6; leitura opcional da Apresentação da Parte V para contextualizar a abertura da Unidade IV |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo; nenhum Micro Game anterior é reaproveitado diretamente, pois o Board Game AI é um novo Micro Game |
| **Cena Unity utilizada** | Nova cena mínima para o Micro Game Board Game AI: um tabuleiro simples de jogo da velha (grade 3×3) para introduzir o algoritmo, sem necessidade de arte elaborada — o foco é a lógica de jogo e o algoritmo, não a apresentação visual; a mesma cena será estendida para Conecta 4 Reduzido (grade menor que o padrão) na Semana 11, exemplo fixado para o Módulo 4 |
| **Assets** | Nenhum asset de arte adicional necessário; elementos visuais podem ser primitivos simples (quadrados, texto de X e O) |
| **Exemplos** | Diagrama dos três tipos de ambiente — cooperativo, reativo, competitivo (seção 11.1); diagrama de anatomia da árvore de jogo, com raiz, ramos, profundidade e folhas com utilidade (seção 11.2); diagrama de propagação de valores no Minimax com o exemplo numérico de árvore de 2 *plies* (seção 11.3) |
| **Vídeos** | Não é necessário vídeo externo nesta semana; a demonstração é conduzida com o exemplo do jogo da velha, traçado ao vivo pelo professor |
| **Jogos para Engenharia Reversa** | Não aplicável nesta semana — a Semana 10 não prevê momento de Engenharia Reversa, conforme o Cronograma |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação da árvore de jogo e do algoritmo Minimax. Demonstração para um jogo de tabuleiro simples.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura da Unidade IV | 5 min | Introduzir a nova pergunta norteadora e situar o Minimax entre as técnicas já estudadas | Apresenta a transição de "como escolher a melhor ação?" (Módulo 3) para "como derrotar um adversário inteligente?" (Módulo 4), retomando a Apresentação da Parte V; explica que, pela primeira vez no semestre, o ambiente **planeja ativamente contra o agente** | Relembram exemplos de jogos com oponente humano ou de IA (xadrez, damas, jogo da velha) e levantam hipóteses sobre por que decidir contra esse tipo de oponente é diferente |
| 2. O problema da decisão adversarial | 15 min | Fundamentar por que avaliar apenas o "agora" é insuficiente | Apresenta a seção 11.1: o exemplo da captura de dama que parece boa mas leva a xeque-mate; a distinção entre ambientes cooperativos, reativos e competitivos, com o diagrama dos três painéis | Classificam, em duplas, dois ou três jogos ou situações de jogo (incluindo os Micro Games já desenvolvidos no semestre) como cooperativos, reativos ou competitivos, justificando a escolha |
| 3. Fundamentos: soma zero e árvore de jogo | 20 min | Construir o vocabulário formal sobre o qual o Minimax opera | Apresenta a seção 11.2: jogos de soma zero, jogos por turnos com informação perfeita, e a árvore de jogo — raiz, ramos, nós filhos, níveis alternados, folhas; usa o diagrama de anatomia da árvore de jogo | Identificam, na árvore de jogo do jogo da velha na posição inicial, o fator de ramificação da raiz e o de um nó de profundidade 1 |
| 4. Profundidade, ramificação e utilidade | 10 min | Consolidar os parâmetros que governam o custo da busca | Apresenta profundidade, *ply*, fator de ramificação *b* e a explosão *b^d*, com os números de xadrez e Go como referência de magnitude; define utilidade (folhas) e apresenta função de avaliação apenas como conceito introdutório, sem aprofundar sua construção | Calculam, para *b* = 9 e profundidade 3, uma estimativa aproximada do número de nós, comparando com o mesmo cálculo para *b* = 35 (xadrez) |
| 5. O algoritmo Minimax | 20 min | Apresentar a regra de propagação MAX/MIN | Apresenta a seção 11.3: jogadores MAX e MIN, a regra de propagação (máximo em nós MAX, mínimo em nós MIN), e o exemplo numérico completo (jogadas A, B, C com folhas 3/5, 6/2, 1/8), destacando por que a jogada A é escolhida apesar de a folha 6 ser o maior valor da árvore | Traçam, em duplas, a propagação de valores do exemplo numérico, chegando ao valor da raiz e à jogada escolhida, sem consultar a solução do professor |
| 6. Demonstração: Minimax no jogo da velha | 10 min | Consolidar o algoritmo em um caso completo e exato | Conduz, ao vivo, o traçado de uma árvore parcial do jogo da velha a partir de uma posição intermediária, mostrando que, por ser pequena, a árvore pode ser explorada até as folhas reais, sem função de avaliação | Acompanham o traçado, antecipando o valor de cada nó antes de o professor revelar, e verificam se acertaram |
| 7. Profundidade limitada e horizonte (introdução) | 5 min | Antecipar o problema que a Semana 11 resolverá | Apresenta brevemente a ideia de profundidade limitada e de horizonte de busca (seção 11.3.2 e 11.3.3), sinalizando que jogos maiores que o jogo da velha exigirão parar antes das folhas — problema a ser resolvido com heurísticas e poda alfa-beta na Semana 11 | Relacionam a ideia de horizonte com a limitação já observada no cálculo de *b^d* para o xadrez, na Etapa 4 |
| 8. Encerramento e preparação do Encontro 2 | 5 min | Orientar o início da implementação prática | Anuncia que o Encontro 2 iniciará o Micro Game Board Game AI, implementando o Minimax em C# para um jogo da velha completo | Organizam-se em grupo, revisando a lógica de estados e jogadas legais do jogo da velha que servirá de base à implementação |

---

## Encontro 2 (1h30)

**Foco:** Início do Micro Game Board Game AI, como implementação própria em C# (não há solução oficial da Unity para este problema).

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando a regra de propagação MAX/MIN e a diferença entre utilidade e função de avaliação, com perguntas diretas à turma | Respondem perguntas de verificação oral, relacionando os conceitos ao jogo da velha traçado no Encontro 1 |
| 2. Ferramentas: por que não há solução oficial da Unity | 10 min | Situar a implementação própria como decisão de projeto coerente, não como limitação improvisada | Explica que a Unity não oferece um sistema nativo para busca adversarial (diferente do NavMesh ou do Unity Behavior), por ser uma ferramenta de propósito geral voltada a jogos de ação em tempo real; situa o Minimax como técnica de nicho para jogos de tabuleiro e estratégia por turnos | Registram, no início do AI Design Log do módulo, a justificativa para a implementação própria em C# |
| 3. Implementação guiada em C# | 45 min | Construir a primeira versão funcional do Minimax no Micro Game Board Game AI | Acompanha os grupos na implementação de uma representação de estado do jogo da velha (tabuleiro, jogador da vez, teste de jogo terminal) e da função recursiva de Minimax, seguindo a estrutura do pseudocódigo apresentado no Encontro 1: casos-base com utilidade, alternância MAX/MIN, e construção recursiva sob demanda | Implementam, em grupo, a representação do estado do jogo e a função Minimax em C#, testando se o algoritmo identifica corretamente a jogada ótima em posições simples |
| 4. Testes e discussão técnica | 15 min | Verificar a corretude da implementação e consolidar a compreensão | Solicita que cada grupo teste a IA contra jogadas humanas simples (incluindo tentativas de "vencer" a IA) e conduz uma discussão sobre por que, com jogo perfeito, o jogo da velha deveria sempre terminar em empate | Testam a própria implementação, verificando se a IA nunca perde e explicam, oralmente, por que a árvore completa do jogo da velha permite Minimax exato, sem heurística |
| 5. Encerramento e transição para a Semana 11 | 10 min | Fechar a semana e indicar o caminho seguinte | Recapitula os elementos da árvore de jogo e a regra de propagação, anuncia que a Semana 11 aprofundará funções heurísticas de avaliação e apresentará a poda alfa-beta para tornar o Minimax viável em jogos maiores que o jogo da velha | Registram, em grupo, o estado atual da implementação e as dúvidas remanescentes para retomada na Semana 11 |

---

## Micro Game

**Micro Game em desenvolvimento:** Board Game AI (Módulo 4) — **início**.

**Objetivo pedagógico:** demonstrar como um NPC pode tomar decisões ótimas contra um oponente racional, aplicando o algoritmo Minimax a um jogo de tabuleiro simples e completo o suficiente para ser explorado sem heurística nem poda, evidenciando o algoritmo em sua forma mais pura antes de qualquer otimização.

O jogo da velha é usado **apenas como introdução ao algoritmo** nesta semana, exatamente como a Apostila o utiliza na seção 11.6: é pequeno o suficiente para ser resolvido por completo, tornando visível o Minimax em sua forma pura, sem heurística nem poda. O Micro Game Board Game AI, porém, converge para **Conecta 4 Reduzido** (grade menor que o padrão, na qual a IA avalia jogadas futuras), o exemplo fixado para o Módulo 4 conforme o CLAUDE.md — não para uma variante de damas ou para o próprio jogo da velha consolidado. Essa transição ocorre na Semana 11, quando a exploração completa deixa de ser viável e heurística e poda alfa-beta se tornam necessárias.

**Funcionalidades esperadas ao final da Semana 10:**

- representação funcional do estado do jogo da velha (tabuleiro, jogador da vez, teste de jogo terminal e de jogadas legais);
- implementação recursiva do algoritmo Minimax em C#, capaz de calcular o valor de cada jogada disponível e escolher a jogada ótima na raiz;
- verificação empírica de que a IA nunca perde uma partida contra um adversário humano, jogando corretamente até o empate diante de jogo perfeito;
- capacidade do grupo de explicar, para uma posição dada, por que uma determinada jogada foi escolhida pelo algoritmo.

**Relação com módulos anteriores:** inaugura o Módulo 4 e a Unidade IV, introduzindo o primeiro problema do semestre em que o ambiente planeja estrategicamente contra o agente — uma categoria distinta das técnicas de decisão (Módulo 1), navegação (Módulo 2) e tomada de decisão tática (Módulo 3), todas situadas em ambientes cooperativos ou reativos. O Micro Game Board Game AI é iniciado como implementação própria em C#, seguindo o mesmo padrão de implementação própria já exercitado no Módulo 3 (mapa de influência e Utility AI), já que também aqui não há solução oficial da Unity equivalente.

---

## Engenharia Reversa

Não há momento de Engenharia Reversa previsto para a Semana 10, conforme o Cronograma — os momentos formais ocorrem apenas nas semanas de encerramento de módulo (🔴). O quarto momento da disciplina está previsto para a Semana 11, ao final do Módulo 4, em jogo de tabuleiro ou estratégia por turnos com dificuldade perceptivelmente ajustável.

Os estudos de caso da seção 11.8 (Deep Blue, Chinook, AlphaGo), se citados no Encontro 1, devem ser tratados como **contextualização histórica**, e não como exercício de Engenharia Reversa: são sistemas com arquitetura publicada, e o objetivo aqui é situar o Minimax na história da IA, não formular hipóteses.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C#** | Implementação própria do algoritmo Minimax e da representação de estado do jogo da velha, já que não há solução oficial da Unity para busca adversarial |
| **Unity (cena mínima)** | Utilizada apenas para hospedar a lógica do jogo e uma representação visual simples do tabuleiro; nenhum pacote oficial de IA da Unity é aplicável a este problema |

Nenhuma ferramenta oficial da Unity é utilizada para o Minimax nesta semana: a técnica é implementação própria em C#, conforme indicado pelo Cronograma e pela Apostila (seção 11.9).

---

## Atividade de Laboratório

**Objetivo:** implementar a primeira versão funcional do Micro Game Board Game AI, aplicando o algoritmo Minimax a um jogo da velha completo, sem heurística nem poda.

**Etapas:**

1. Definir, em grupo, a representação do estado do jogo (tabuleiro 3×3, jogador da vez, função de jogadas legais, função de teste de jogo terminal e de utilidade).
2. Implementar a função recursiva de Minimax em C#, seguindo a estrutura de casos-base (jogo terminal → utilidade) e alternância MAX/MIN, sem necessidade de limite de profundidade nem função de avaliação, já que a árvore do jogo da velha é pequena o suficiente para ser explorada por completo.
3. Testar a implementação a partir da posição inicial vazia, verificando se a IA joga de forma consistente com o resultado teórico esperado (empate garantido com jogo perfeito).
4. Jogar manualmente contra a IA, tentando vencê-la, e registrar se ela nunca perde.
5. Discutir, em grupo, por que a jogada escolhida pela IA em cada posição é a que garante o melhor resultado no pior caso, e não necessariamente a que leva à folha de maior valor absoluto da árvore.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma implementação funcional do Minimax aplicada ao jogo da velha, com a IA jogando de forma consistente (nunca perdendo) e capaz de justificar oralmente a jogada escolhida em posições simples, servindo de base para a evolução do Micro Game Board Game AI na Semana 11.

---

## Verificação da Aprendizagem

O Módulo 4 se encerra formalmente apenas na Semana 11, quando ocorrem o Desafio de Escolha Tecnológica, o AI Design Log e o quarto momento de Engenharia Reversa do módulo, conforme o Cronograma e os Critérios de Notas. A verificação nesta semana é, portanto, **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação, sem gerar nota isolada.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes diferenciam corretamente ambientes cooperativos, reativos e competitivos, e se definem com precisão utilidade e função de avaliação (critério **Compreensão Conceitual** da Rubrica);
- observação do traçado manual do exemplo numérico e da demonstração do jogo da velha, verificando se os grupos aplicam corretamente a regra de propagação MAX/MIN (indício inicial do critério **Compreensão Conceitual**, aprofundado na Semana 11);
- observação da implementação guiada do Encontro 2, verificando se a representação de estado e a função Minimax produzem o comportamento esperado — IA que nunca perde no jogo da velha (indício inicial do critério **Aplicação Prática**, formalmente avaliado na consolidação do Micro Game na Semana 11);
- qualidade da justificativa oral apresentada pelos grupos ao explicar por que uma jogada foi escolhida pelo algoritmo (indício inicial do critério **Comunicação Técnica**).

---

## Entregas

Conforme o Cronograma, a Semana 10 **não possui entregas formais avaliadas**. A implementação inicial do Minimax no Micro Game Board Game AI permanece em desenvolvimento e será consolidada, com o restante do Módulo 4 (heurísticas de avaliação e poda alfa-beta), na Semana 11 — não constitui entrega avaliada isoladamente nesta semana.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Escolher a jogada que leva ao maior valor absoluto da árvore, ignorando que o adversário nunca permitiria alcançá-la | Retomar o Erro Comum da seção 11.3, reforçando a pergunta-guia: "qual é o pior que pode acontecer depois desta jogada, se o oponente jogar perfeitamente?" |
| Confundir "ambiente difícil" com "ambiente adversarial", tratando qualquer inimigo desafiador como caso de Minimax | Retomar o Erro Comum da seção 11.1, reforçando que a busca adversarial só se justifica quando há um oponente racional alternando decisões com o agente, não apenas um ambiente hostil |
| Perder a conta de qual nível da árvore é MAX e qual é MIN, aplicando a operação errada durante o traçado manual | Retomar a Boa Prática da seção 11.3.1: marcar cada camada com o jogador correspondente antes de propagar valores, usando convenção visual consistente (por exemplo, triângulos para cima e para baixo) |
| Tentar implementar, já nesta semana, profundidade limitada ou função de avaliação ponderada, antecipando conteúdo da Semana 11 | Reforçar que o jogo da velha é pequeno o suficiente para ser resolvido por completo, sem necessidade de heurística ou poda; redirecionar o grupo à implementação exata prevista para esta semana |
| Confundir utilidade (valor exato de uma folha terminal) com função de avaliação (estimativa de um nó não-terminal) | Retomar a Boa Prática da seção 11.2, destacando que, nesta semana, como a árvore do jogo da velha é explorada por completo, apenas a utilidade é utilizada — a função de avaliação só se tornará necessária na Semana 11 |

---

## Preparação para a Próxima Semana

Para a Semana 11 (Heurísticas e Poda Alfa-Beta — encerramento do Módulo 4 e da Unidade IV), o professor deve:

- confirmar que todos os grupos possuem, ao final da Semana 10, uma implementação funcional do Minimax aplicada ao jogo da velha no Micro Game Board Game AI, servindo de base para a evolução do módulo;
- solicitar a leitura prévia do material indicado para a Semana 11 sobre funções heurísticas de avaliação e poda alfa-beta, conforme a Apostila;
- preparar o cenário de **Conecta 4 Reduzido** (grade menor que o padrão), o Micro Game fixado para o Módulo 4, no qual a exploração completa da árvore deixe de ser viável, motivando a necessidade de profundidade limitada, função de avaliação e poda alfa-beta;
- reservar, para a Semana 11, o material do quarto momento de Engenharia Reversa, em jogo de tabuleiro ou estratégia por turnos, conforme o Cronograma;
- anunciar aos estudantes que a Semana 11 encerra o Módulo 4 e a Unidade IV, com **quatro** entregas avaliadas: Micro Game 4 consolidado (50%), AI Design Log do Micro Game 4 (25%), Desafio de Escolha Tecnológica (15%) e o quarto momento de Engenharia Reversa (10%) — reforçando que o Micro Game é a entrega de maior peso do módulo, e não apenas um artefato de trabalho.
