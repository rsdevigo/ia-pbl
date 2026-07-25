# Plano de Aula — Semana 11

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 11 de 17 |
| **Unidade** | Unidade IV — Busca Adversarial (Semanas 10–11) |
| **Módulo** | Módulo 4 — Como derrotar um adversário inteligente? |
| **Tema** | Heurísticas e Poda Alfa-Beta |
| **Pergunta Norteadora** | Como derrotar um adversário inteligente? (parte 2) |
| **Tipo de semana** | 🔴 Encerramento de módulo (Desafio de Escolha Tecnológica + Engenharia Reversa) |

---

## Objetivos de Aprendizagem

Ao final da Semana 11, o estudante deverá ser capaz de:

1. **Explicar** por que o Minimax puro, embora correto, é inviável em jogos reais devido à explosão combinatória *b^d*, retomando o problema apresentado na Semana 10 como motivação central desta semana.
2. **Diferenciar** com precisão utilidade (valor exato de folha terminal) de função de avaliação (estimativa em nó não-terminal na fronteira de profundidade), aprofundando a distinção introduzida na Semana 10.
3. **Construir** uma função heurística de avaliação simples como soma ponderada de características (*features*) de uma posição de jogo, justificando o peso relativo de cada característica escolhida.
4. **Explicar** o trade-off entre precisão e custo de uma função de avaliação, relacionando-o à profundidade de busca alcançável no tempo disponível.
5. **Enunciar** a condição de poda alfa-beta (α ≥ β) e **explicar** por que a poda não altera a decisão final do Minimax — apenas reduz o número de nós examinados.
6. **Executar manualmente** a poda alfa-beta sobre uma árvore de jogo pequena, registrando os valores de α e β ao longo da busca e identificando os ramos podados.
7. **Diferenciar** corte alfa e corte beta, relacionando cada um ao tipo de nó (MIN ou MAX) em que ocorre.
8. **Justificar** por que a ordenação de jogadas é irrelevante para o Minimax puro, mas decisiva para a eficácia da poda alfa-beta, relacionando essa diferença ao impacto na complexidade (de O(b^d) para O(b^{d/2}) no melhor caso).
9. **Consolidar**, em grupo, o Micro Game Board Game AI, integrando função heurística de avaliação e poda alfa-beta à implementação do Minimax iniciada na Semana 10, permitindo jogar um tabuleiro maior que o jogo da velha.
10. **Justificar** tecnicamente, por escrito e oralmente, a escolha de uma solução de busca adversarial para um cenário proposto, no Desafio de Escolha Tecnológica do Módulo 4.
11. **Aplicar** o roteiro completo de seis etapas da metodologia de Engenharia Reversa de IA a um jogo comercial de tabuleiro ou estratégia por turnos, distinguindo [Documentado], [Inferência] e [Especulação].

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte V, Capítulo 11 da Apostila — Minimax e Busca Adversarial**, seções 11.3.4 e 11.4 (com a subseção 11.4.1), complementado pela parte introdutória de heurísticas do **Capítulo 13** (seção 13.1, apenas o conceito geral de heurística e otimização heurística, sem antecipar Algoritmos Genéticos), e com reutilização da metodologia da **Parte VII, Capítulo 14 — Metodologia de Engenharia Reversa de IA**, já aplicada nas Semanas 4, 7 e 9:

- retomada breve do problema da explosão combinatória (*b^d*) e da profundidade limitada, já introduzidos na Semana 10, como motivação para heurísticas e poda — seções 11.3.2 e 11.3.3;
- funções heurísticas de avaliação: definição, papel de preencher a fronteira de profundidade quando a busca não alcança folhas reais, e construção como soma ponderada de características (material, controle do centro, segurança do rei, mobilidade, no exemplo do xadrez) — seção 11.3.4;
- o trade-off entre qualidade da heurística e profundidade alcançável: heurística melhor compensa profundidade menor; heurística mais sofisticada custa mais por avaliação e pode reduzir a profundidade alcançável no mesmo orçamento de tempo — seção 11.3.4;
- reconhecimento breve de que funções de avaliação podem ser aprendidas a partir de dados, em vez de ajustadas manualmente (caso do NNUE do Stockfish), como ponte conceitual com a Parte VI, sem aprofundar técnicas de aprendizado nesta semana — seção 11.3.4;
- motivação e intuição da poda alfa-beta: por que não é necessário examinar todos os nós para obter a mesma decisão do Minimax completo — seção 11.4 (Motivação);
- funcionamento formal: os valores α (melhor garantido para MAX) e β (melhor garantido para MIN), a condição de poda (α ≥ β), e a distinção entre corte beta (em nó MAX) e corte alfa (em nó MIN) — seção 11.4 (Funcionamento);
- traçado do exemplo numérico da Semana 10 (jogadas A, B, C; folhas 3/5, 6/2, 1/8) com poda alfa-beta, identificando os ramos eliminados sem alterar a jogada escolhida — seção 11.4 (Eliminação de ramos);
- corretude da poda: alfa-beta e Minimax produzem sempre a mesma jogada; a poda é uma otimização exata, não uma aproximação — seção 11.4 (Corretude da poda);
- impacto na complexidade: pior caso O(b^d) igual ao Minimax; melhor caso O(b^{d/2}), permitindo aproximadamente o dobro da profundidade no mesmo tempo — seção 11.4 (Impacto na complexidade);
- ordenação de jogadas: por que a ordem dos filhos examinados determina a eficácia da poda, e as heurísticas mais comuns de ordenação (capturas primeiro, tabela de transposição, aprofundamento iterativo revisitado, heurísticas *killer* e de histórico) — seção 11.4.1;
- ferramentas: confirmação de que não há solução oficial da Unity para busca adversarial, com a implementação do Minimax com heurística e poda alfa-beta permanecendo em C# sobre a própria lógica do jogo, conforme já estabelecido na Semana 10 — seção 11.9;
- reutilização da metodologia de Engenharia Reversa de IA (roteiro de seis etapas e rótulos [Documentado]/[Inferência]/[Especulação]), aplicada de forma completa a um quarto caso, em jogo de tabuleiro ou estratégia por turnos.

Não deve ser antecipado o conteúdo da Seção 11.5 (Monte Carlo Tree Search), que é aprofundamento não previsto no Cronograma desta disciplina. Os estudos de caso da seção 11.8 (Deep Blue, Chinook, AlphaGo) podem ser citados brevemente como contextualização histórica, mas não constituem objetivo de avaliação desta semana. Conforme a observação do Cronograma para a Semana 10, o Capítulo 13 **não é concluído** nesta semana: apenas sua abertura conceitual sobre heurística e otimização heurística (seção 13.1) é utilizada, como reforço terminológico; a parte de Algoritmos Genéticos (seções 13.2 em diante) fica reservada às Semanas 12–13, e não deve ser antecipada.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte V, Capítulo 11, seções 11.3.4 e 11.4 (incluindo 11.4.1); leitura opcional da seção 13.1 do Capítulo 13, apenas para reforçar a generalização do conceito de heurística (sem entrar em Algoritmos Genéticos); revisão da Parte VII, Capítulo 14, seção 14.3 (roteiro de seis etapas); **Encerramento da Parte V**, cuja *Tabela Comparativa — Minimax × Alfa-Beta × MCTS* consolida o módulo; **Apêndice C.1** e **C.2** como apoio ao Desafio |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com a implementação inicial do Minimax da Semana 10; acesso a vídeo ou build do jogo escolhido para o quarto momento de Engenharia Reversa |
| **Cena Unity utilizada** | A mesma cena mínima do Micro Game Board Game AI iniciada na Semana 10, estendida para um tabuleiro maior que o jogo da velha (por exemplo, uma variante simplificada de damas ou Connect Four/Lig-4 em grade reduzida), no qual a exploração completa da árvore deixe de ser viável |
| **Assets** | Nenhum asset de arte adicional necessário; elementos visuais permanecem primitivos simples, conforme a Semana 10 |
| **Exemplos** | Diagrama de como a função de avaliação preenche o horizonte na fronteira de profundidade (seção 11.3.4); traçado do exemplo numérico A/B/C com valores de α e β anotados nos pontos de corte (seção 11.4); diagrama comparativo Minimax completo × árvore podada por alfa-beta (seção 11.4.1) |
| **Vídeos** | Não é necessário vídeo externo para a fundamentação teórica; a demonstração é conduzida ao vivo pelo professor, retraçando o exemplo numérico já usado na Semana 10 com a poda aplicada |
| **Jogos para Engenharia Reversa** | Um jogo digital de tabuleiro ou estratégia por turnos com níveis de dificuldade ajustáveis é sugerido — por exemplo, uma implementação comercial de Reversi/Othello, citada na Apostila (seção 11.8) como caso didático clássico de poda alfa-beta com avaliação baseada em estabilidade de peças e controle de cantos. O professor pode substituir por outro jogo de tabuleiro ou estratégia por turnos com IA de dificuldade perceptivelmente ajustável, mantendo a análise estritamente comportamental, conforme a seção 14.4 |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação de heurísticas de avaliação para tornar o Minimax viável em profundidade maior. Introdução da poda alfa-beta.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Retomada e motivação | 10 min | Reconectar com o problema da Semana 10 e justificar a necessidade desta semana | Recapitula a explosão combinatória *b^d*, a profundidade limitada e o horizonte de busca (Semana 10), destacando que o jogo da velha foi um caso especial resolvido por completo — a maioria dos jogos não permite isso | Relembram, em voz alta, o cálculo aproximado de nós para *b* = 35 (xadrez) feito na Semana 10, reconectando com a necessidade de parar antes das folhas |
| 2. Funções heurísticas de avaliação | 25 min | Ensinar a construir e avaliar funções de avaliação | Apresenta a seção 11.3.4: o papel da função de avaliação na fronteira de profundidade, a construção como soma ponderada de características (material, centro, segurança do rei, mobilidade), e o trade-off entre precisão e custo; cita brevemente a existência de heurísticas aprendidas (NNUE) como ponte com a Parte VI, sem aprofundar | Propõem, em duplas, três características (features) para uma função de avaliação de um jogo simples (por exemplo, damas ou Connect Four) e atribuem pesos relativos, justificando a escolha |
| 3. Motivação da poda alfa-beta | 15 min | Introduzir a intuição da poda antes da formalização | Apresenta a Motivação da seção 11.4: o raciocínio de que um ramo comprovadamente pior que uma alternativa já conhecida não precisa ser explorado até o fim, usando a analogia de comparar jogadas uma a uma | Reformulam, com as próprias palavras, por que "já sei que essa jogada não pode ser melhor" permite parar de analisá-la |
| 4. Funcionamento formal: α, β e a condição de poda | 20 min | Formalizar os valores α e β e a regra α ≥ β | Apresenta a seção 11.4 (Funcionamento): definição de α e β como limites inferior e superior, a condição de poda, e a distinção entre corte beta (nó MAX) e corte alfa (nó MIN) | Acompanham a explicação anotando, em uma tabela simples, o significado de α e β e de cada tipo de corte |
| 5. Traçado guiado do exemplo numérico com poda | 15 min | Consolidar a mecânica da poda em um caso concreto | Retraça, ao vivo, o exemplo A/B/C (folhas 3/5, 6/2, 1/8) já usado na Semana 10, agora aplicando alfa-beta da esquerda para a direita, anotando α e β a cada passo e identificando o corte alfa nos ramos B e C | Acompanham o traçado, antecipando em quais pontos ocorrerá poda antes de o professor revelar, e conferem se acertaram |
| 6. Corretude, complexidade e ordenação de jogadas | 5 min | Fechar com os resultados centrais da técnica | Apresenta rapidamente a corretude da poda (mesma jogada do Minimax), o impacto na complexidade (O(b^d) a O(b^{d/2})) e a importância da ordenação de jogadas (seção 11.4.1), sinalizando que serão retomados no Encontro 2 | Relacionam o ganho de complexidade com o problema de explosão combinatória revisto na Etapa 1 |

---

## Encontro 2 (1h30)

**Foco:** Consolidação do Micro Game Board Game AI. Desafio de Escolha Tecnológica do Módulo 4. Quarto momento de Engenharia Reversa, em jogo de tabuleiro ou estratégia por turnos.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando a diferença entre utilidade e função de avaliação, a condição de poda α ≥ β e por que a poda não muda a decisão | Respondem perguntas de verificação oral, relacionando os conceitos à implementação do Minimax iniciada na Semana 10 |
| 2. Implementação guiada em C# | 35 min | Consolidar o Micro Game Board Game AI com heurística e poda | Acompanha os grupos na implementação de uma função de avaliação simples (soma ponderada de características) e da poda alfa-beta sobre a função Minimax já existente, aplicando-as a um tabuleiro maior que o jogo da velha (por exemplo, damas simplificada ou Connect Four em grade reduzida) | Implementam, em grupo, a função de avaliação e a poda alfa-beta em C#, testando se a IA agora joga em tabuleiros maiores dentro de tempo aceitável |
| 3. Discussão técnica | 10 min | Consolidar a compreensão da implementação realizada | Conduz a discussão sobre os pesos escolhidos na função de avaliação e sobre quantos nós cada grupo estima ter economizado com a poda, relacionando à ordenação de jogadas adotada (se houver) | Justificam, em voz alta, os pesos da função de avaliação e comparam informalmente o tempo de resposta da IA antes e depois da poda |
| 4. Desafio de Escolha Tecnológica do Módulo 4 | 15 min | Desenvolver a capacidade de justificar tecnicamente uma escolha de busca adversarial | Apresenta um cenário não idêntico ao Micro Game (por exemplo, um jogo de tabuleiro com fator de ramificação bem maior que o jogo da velha, ou um jogo com elemento de acaso) e solicita que cada grupo avalie se o Minimax com alfa-beta é adequado, considerando alternativas e limitações discutidas na Semana 10 (seção 11.7) | Analisam o cenário, comparam alternativas com base em requisitos e limitações (fator de ramificação, disponibilidade de heurística, tempo real versus turnos, presença de acaso), e registram a justificativa por escrito |
| 5. Quarto momento de Engenharia Reversa | 15 min | Aplicar o roteiro completo de seis etapas a um caso de busca adversarial | Apresenta trechos de vídeo ou partidas do jogo escolhido (por exemplo, um Reversi/Othello comercial com dificuldade ajustável), conduz a definição do problema e a observação orientada à qualidade de jogo em diferentes níveis de dificuldade, e orienta a formulação, validação e documentação das hipóteses sobre profundidade de busca e função de avaliação, reforçando os rótulos [Documentado]/[Inferência]/[Especulação] | Aplicam as seis etapas do roteiro ao comportamento observado, relacionando mudanças de dificuldade a possíveis variações de profundidade de busca e/ou de heurística, com nível de confiança explícito para cada afirmação |
| 6. Encerramento do Módulo 4 e da Unidade IV | 5 min | Fechar o módulo e indicar o caminho da próxima semana | Recapitula a evolução do Minimax puro (Semana 10) ao Minimax com heurística e poda alfa-beta (Semana 11), confirma as entregas da semana e anuncia que a Semana 12 abre a Unidade V com Algoritmos Genéticos, retomando o Capítulo 13 desde o início | Registram pendências das quatro entregas do módulo para finalização até o prazo definido pelo professor |

---

## Micro Game

**Micro Game em desenvolvimento:** Board Game AI (Módulo 4) — **consolidação final**.

**Objetivo pedagógico:** demonstrar como a mesma decisão ótima contra um adversário racional, calculada de forma exata na Semana 10 para um jogo pequeno, pode ser tornada viável em jogos maiores por meio de duas peças complementares — uma função heurística de avaliação, que estima o valor de posições não-terminais, e a poda alfa-beta, que elimina de forma segura ramos que não podem influenciar a decisão final.

**Funcionalidades esperadas ao final da Semana 11:**

- função heurística de avaliação implementada como soma ponderada de características do estado do jogo, aplicada aos nós não-terminais na fronteira de profundidade;
- poda alfa-beta integrada à função recursiva de Minimax já implementada na Semana 10, produzindo a mesma jogada que o Minimax completo com menos nós examinados;
- a IA jogando em um tabuleiro maior que o jogo da velha (por exemplo, damas simplificada ou Connect Four em grade reduzida), dentro de um tempo de resposta aceitável por jogada;
- capacidade do grupo de explicar os pesos escolhidos na função de avaliação e de identificar, em uma árvore pequena, quais ramos seriam podados e por quê.

**Relação com módulos anteriores:** encerra a trajetória do Módulo 4, iniciada na Semana 10 com o Minimax exato aplicado ao jogo da velha, demonstrando que a mesma lógica de decisão adversarial se torna praticável em jogos maiores por meio de estimativa (heurística) e economia de busca (poda) — sem alterar a natureza da decisão em si. O Micro Game Board Game AI permanece como implementação própria em C#, consistente com o padrão já exercitado no Módulo 3 (mapa de influência e Utility AI), consolidando o AI Playground com quatro Micro Games completos ao final desta semana.

---

## Engenharia Reversa

**Quarto momento formal de Engenharia Reversa da disciplina**, conforme o Cronograma, aplicando o roteiro completo de seis etapas da seção 14.3 da Apostila.

**Jogo analisado:** um jogo digital de Reversi/Othello comercial com múltiplos níveis de dificuldade ajustável, citado na Apostila (seção 11.8) como caso didático clássico de poda alfa-beta, com função de avaliação tipicamente baseada em estabilidade de peças e controle de cantos. O professor pode substituir por outro jogo de tabuleiro ou estratégia por turnos com IA de dificuldade perceptivelmente ajustável (por exemplo, damas, Connect Four ou um jogo de estratégia por turnos com níveis de IA), mantendo a análise estritamente comportamental, conforme a seção 14.4.

**Comportamento observado:** qualidade das jogadas da IA em diferentes níveis de dificuldade — tempo de resposta por jogada, capacidade de antecipar ameaças a médio prazo, e eventuais erros táticos em posições mais complexas nos níveis mais fáceis.

**Perguntas para discussão:**

- As diferenças de dificuldade parecem mais compatíveis com variação na profundidade de busca, na qualidade da função de avaliação, ou em ambas simultaneamente?
- Há sinais observáveis de efeito horizonte (Semana 10) em algum nível de dificuldade — por exemplo, a IA parece "adiar" uma perda inevitável em vez de evitá-la?
- O tempo de resposta da IA varia de forma perceptível com a complexidade da posição (sinal indireto de busca com profundidade variável ou de poda mais ou menos eficaz), ou parece constante?
- Que evidências sustentam a hipótese levantada, e com que nível de confiança? O que é [Documentado] sobre o jogo escolhido (se houver fonte pública) e o que permanece [Inferência] ou [Especulação], considerando que a Apostila trata a atribuição de Minimax/alfa-beta a jogos comerciais de tabuleiro como inferência plausível, não confirmação oficial (seção 11.8)?

**Relação com os conceitos da semana:** aplica o roteiro completo de seis etapas (definição do problema, coleta de evidências, registro das observações, formulação de hipóteses, validação e documentação), já reutilizado nas Semanas 4, 7 e 9, exercitando agora o vocabulário de função de avaliação, poda alfa-beta e profundidade de busca construído nesta semana e na Semana 10.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C#** | Implementação própria da função heurística de avaliação e da poda alfa-beta, estendendo a função Minimax já implementada em C# na Semana 10, já que não há solução oficial da Unity para busca adversarial |
| **Unity (cena mínima)** | Utilizada apenas para hospedar a lógica do jogo e a representação visual simples do tabuleiro maior, reaproveitando a cena mínima da Semana 10 |

Nenhuma ferramenta oficial da Unity é utilizada para heurísticas de avaliação ou poda alfa-beta nesta semana: ambas permanecem implementação própria em C#, conforme indicado pelo Cronograma e pela Apostila (seção 11.9), em continuidade direta com a Semana 10.

---

## Atividade de Laboratório

**Objetivo:** consolidar o Micro Game Board Game AI como entrega do Módulo 4, implementando função heurística de avaliação e poda alfa-beta sobre o Minimax da Semana 10, aplicar o Desafio de Escolha Tecnológica a um cenário de busca adversarial e concluir o quarto momento de Engenharia Reversa.

**Etapas:**

1. Escolher, em grupo, um tabuleiro maior que o jogo da velha (por exemplo, damas simplificada ou Connect Four/Lig-4 em grade reduzida), no qual a exploração completa da árvore não seja mais viável em tempo aceitável.
2. Definir de duas a quatro características (features) da posição relevantes para o jogo escolhido, atribuir pesos e implementar a função de avaliação como soma ponderada, aplicada nos nós da fronteira de profundidade.
3. Integrar a poda alfa-beta à função recursiva de Minimax já implementada na Semana 10, carregando os valores de α e β ao longo da busca em profundidade.
4. Testar a implementação, comparando o número de nós examinados e o tempo de resposta com e sem poda, verificando que a jogada escolhida permanece a mesma.
5. Jogar manualmente contra a IA em diferentes profundidades de busca, observando a mudança de qualidade das jogadas e relacionando-a ao trade-off entre profundidade e heurística discutido na seção 11.3.4.
6. Analisar o cenário do Desafio de Escolha Tecnológica (jogo com fator de ramificação maior ou com elemento de acaso), avaliar se o Minimax com alfa-beta permanece adequado e registrar a justificativa por escrito.
7. Aplicar as seis etapas do roteiro de Engenharia Reversa ao jogo de tabuleiro ou estratégia por turnos escolhido, registrando evidências, hipóteses, validação e documentação com os rótulos de confiança apropriados.
8. Reunir as quatro entregas do módulo: Micro Game consolidado, AI Design Log, Desafio de Escolha Tecnológica e Engenharia Reversa do Módulo 4.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter o Micro Game Board Game AI consolidado como entrega do Módulo 4 — com Minimax, função de avaliação e poda alfa-beta integrados, aplicados a um tabuleiro maior que o jogo da velha —, uma justificativa técnica registrada para o cenário do Desafio de Escolha Tecnológica, e o registro completo das seis etapas de Engenharia Reversa aplicadas ao jogo escolhido.

---

## Verificação da Aprendizagem

A Semana 11 **encerra formalmente o Módulo 4 e a Unidade IV** (Busca Adversarial), e a verificação da aprendizagem gera nota, conforme os Critérios de Notas da disciplina. O professor deve aplicar a Rubrica de Avaliação aos quatro instrumentos previstos:

- **Micro Game (consolidação)** — avaliado principalmente por Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução, observando se a função de avaliação e a poda alfa-beta produzem o comportamento esperado (mesma jogada do Minimax, com menos nós examinados) e se a implementação própria em C# está bem organizada, já que não há solução oficial da Unity a avaliar (peso 50% do módulo);
- **AI Design Log** — avaliado pelo critério de AI Design Log, verificando se o documento registra problema, alternativas consideradas ao longo do módulo (profundidade de busca, características da função de avaliação, uso ou não de poda), solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras (peso 25% do módulo);
- **Desafio de Escolha Tecnológica** — avaliado principalmente por Tomada de Decisão, apoiado por Compreensão Conceitual, verificando se o grupo avaliou corretamente a adequação do Minimax com alfa-beta ao cenário proposto, considerando fator de ramificação, tempo disponível e presença ou não de acaso (peso 15% do módulo);
- **Engenharia Reversa** — avaliado por Compreensão Conceitual e Tomada de Decisão, verificando a qualidade das hipóteses formuladas sobre a busca adversarial observada no jogo escolhido e o uso correto dos rótulos [Documentado]/[Inferência]/[Especulação] (peso 10% do módulo).

A nota do Módulo 4 compõe 11,67% da nota final do semestre, conforme os Critérios de Notas. O professor deve registrar e comunicar aos estudantes a nota obtida em cada instrumento e a nota consolidada do módulo, conforme recomendado pela Rubrica, dando atenção especial ao critério de Evolução ao Longo do Semestre em relação aos módulos anteriores.


**Instrumentos de verificação disponíveis na Apostila.** Antes de recorrer a questões próprias, o professor deve usar o material já pronto e alinhado: os **Exercícios de fixação** ao final do Capítulo 11, e — nas semanas de encerramento de Parte — as **Questões de Revisão**, os **Exercícios Conceituais** e os **Exercícios de Integração** do Encerramento correspondente. Recomenda-se aplicar duas ou três questões na abertura do Encontro 2, como verificação rápida antes do laboratório, e usar a Tabela Comparativa do Encerramento da Parte V como apoio à discussão técnica. Esse material é a principal fonte de verificação formativa da disciplina, e não deve ficar sem uso.

---

## Entregas

Conforme o Cronograma e a matriz dos Critérios de Notas (item 4), esta semana encerra o Módulo 4 e a Unidade IV com **quatro** entregas avaliadas:

- **Micro Game 4 — Board Game AI consolidado (50%)** — Minimax com função de avaliação e poda alfa-beta funcionando sobre o jogo de tabuleiro escolhido, avaliado pelos critérios de Compreensão Conceitual, Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução;
- **AI Design Log — Micro Game 4 (25%)** — documento contendo problema, requisitos, alternativas consideradas (profundidade de busca, características da função de avaliação, uso de poda), solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras, conforme o modelo dos Modelos de Entrega do Aluno (§1);
- **Desafio de Escolha Tecnológica — Módulo 4 (15%)** — justificativa escrita avaliando a adequação do Minimax com poda alfa-beta ao cenário de busca adversarial apresentado no Encontro 2;
- **4º momento de Engenharia Reversa (10%)** — registro completo das seis etapas do roteiro aplicado ao jogo de tabuleiro ou estratégia por turnos escolhido.

O Micro Game Board Game AI permanece no AI Playground de cada grupo como base para os módulos seguintes, mas a versão consolidada nesta semana é **entrega formal avaliada**, e não apenas um artefato de trabalho.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Construir uma função de avaliação com pesos arbitrários, sem justificativa relacionada ao comportamento desejado no jogo | Retomar a seção 11.3.4, pedindo que o grupo justifique cada peso em termos de sua contribuição observável para a qualidade da jogada |
| Confundir a poda alfa-beta com uma técnica que "joga diferente" ou "aproxima" a decisão, em vez de reconhecer que ela produz exatamente a mesma jogada do Minimax completo | Retomar o quadro de Atenção da seção 11.4 (Corretude da poda), reforçando que a poda é uma otimização exata, não uma heurística de corte arriscada |
| Aplicar a condição de poda de forma invertida, confundindo corte alfa (nó MIN) com corte beta (nó MAX) | Retomar a seção 11.4 (Funcionamento) e pedir que o grupo marque, antes de cada traçado, qual jogador (MAX ou MIN) está em cada camada, como já praticado na Semana 10 |
| Implementar a poda alfa-beta sem ordenar as jogadas, obtendo pouco ou nenhum ganho de desempenho, e concluir erroneamente que a poda "não funciona" | Retomar a seção 11.4.1, explicando que o ganho da poda depende da ordem de exploração, e sugerir uma ordenação simples (por exemplo, priorizar jogadas que capturam peças) |
| Tentar usar profundidade muito alta no tabuleiro maior sem heurística nem poda, tornando a IA lenta demais para uso prático | Reforçar que a heurística e a poda desta semana existem exatamente para resolver esse problema; redirecionar o grupo a reduzir a profundidade e validar o ganho de desempenho antes de aumentá-la novamente |

---

## Preparação para a Próxima Semana

Para a Semana 12 (Fundamentos de Algoritmos Genéticos — abertura da Unidade V), o professor deve:

- garantir que as quatro entregas do Módulo 4 (Micro Game consolidado, AI Design Log, Desafio de Escolha Tecnológica, Engenharia Reversa) estejam recebidas e avaliadas antes do início da Semana 12, registrando a nota do módulo conforme a matriz dos Critérios de Notas (item 4);
- confirmar que todos os grupos possuem, ao final da Semana 11, o Micro Game Board Game AI consolidado no AI Playground, encerrando o Módulo 4 e a Unidade IV;
- solicitar a leitura prévia da Parte VI, Capítulo 13 da Apostila, desde o início (seções 13.1 a 13.3), esclarecendo aos estudantes que o capítulo será retomado do zero, e não continuado a partir da leitura pontual da seção 13.1 já feita nesta semana;
- anunciar a transição de unidade: da pergunta "como derrotar um adversário inteligente?" para "como encontrar automaticamente boas soluções?", situando os Algoritmos Genéticos como uma nova família de técnicas de otimização, distinta da busca adversarial do Módulo 4;
- reservar, para a Semana 13, a consolidação do Micro Game Genetic Lab, o Desafio de Escolha Tecnológica do Módulo 5 e o quinto momento de Engenharia Reversa, conforme o Cronograma.
