# Plano de Aula — Semana 12

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 12 de 17 |
| **Unidade** | Unidade V — Otimização Automática (Semanas 12–13) |
| **Módulo** | Módulo 5 — Como encontrar automaticamente boas soluções? |
| **Tema** | Fundamentos de Algoritmos Genéticos |
| **Pergunta Norteadora** | Como encontrar automaticamente boas soluções? (parte 1) |
| **Tipo de semana** | 🔵 Regular (fundamentação e desenvolvimento do Micro Game) |

---

## Objetivos de Aprendizagem

Ao final da Semana 12, o estudante deverá ser capaz de:

1. **Explicar** o problema da explosão combinatória em espaços de busca de otimização, relacionando-o ao mesmo fenômeno já estudado no Minimax (Módulo 4), e **justificar** por que a busca exaustiva se torna inviável nesses casos.
2. **Definir** otimização heurística como a busca por uma solução "boa o suficiente" em tempo aceitável, relacionando o sentido de heurística usado aqui ao já empregado no A* (Módulo 2).
3. **Diferenciar**, no sentido computacional, os termos indivíduo, cromossomo, gene, população e aptidão (fitness), aplicando-os a um exemplo de ajuste de parâmetros de uma IA de jogo.
4. **Distinguir** com precisão otimização evolutiva (busca por uma configuração que maximiza uma função de aptidão) de aprendizagem por interação (ajuste de um comportamento ao longo do tempo, como no RL do Módulo 6), evitando confundir as duas famílias de técnicas.
5. **Descrever**, na ordem correta, as oito etapas do ciclo de um Algoritmo Genético (inicialização, avaliação, seleção, cruzamento, mutação, elitismo, nova geração, critério de parada).
6. **Avaliar** criticamente uma representação (codificação de cromossomo) proposta para um problema simples, identificando se ela tende a gerar soluções válidas ou inválidas.
7. **Explicar** o papel decisivo da função de aptidão na condução da busca evolutiva, relacionando-a ao papel da recompensa na Aprendizagem por Reforço e reconhecendo o risco de uma função mal projetada.
8. **Comparar** as estratégias de seleção por roleta, por torneio e por ranqueamento, indicando uma vantagem e uma limitação de cada.
9. **Diferenciar** crossover de um ponto, de múltiplos pontos e uniforme, relacionando a escolha à representação do cromossomo.
10. **Explicar** o papel da mutação e do elitismo no equilíbrio entre exploração e *exploitation*, e **reconhecer** os sintomas de convergência prematura.
11. **Implementar**, em grupo, a estrutura inicial do Micro Game Genetic Lab em C#, aplicando os quatro operadores genéticos (seleção, cruzamento, mutação, elitismo) a um problema simples e observando a melhoria da aptidão ao longo das gerações.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte VI, Capítulo 13 da Apostila — Heurísticas e Algoritmos Genéticos**, seções 13.1 a 13.6:

- o problema da explosão combinatória em espaços de busca de otimização e a inexistência, para muitos problemas, de um algoritmo exato eficiente — seção 13.1;
- otimização heurística: buscar uma solução "boa o suficiente" em tempo aceitável, e a distinção fundamental entre otimizar (buscar a melhor configuração) e aprender a agir (RL, Capítulo 12) — seção 13.1;
- fundamentos e vocabulário evolutivo no sentido computacional: indivíduo, cromossomo, gene, população e aptidão (fitness), e o princípio da seleção natural artificial — seção 13.2;
- o ciclo completo do Algoritmo Genético em oito etapas: inicialização, avaliação, seleção, cruzamento, mutação, elitismo, nova geração e critério de parada — seção 13.3;
- representação do problema: codificação binária, por valores reais, por permutação e estruturada, e a importância de uma representação que gere soluções válidas — seção 13.4;
- função de aptidão: seu papel central na condução da busca, o paralelo com a recompensa do RL, a influência da forma da função na convergência, e os problemas de funções mal projetadas (aptidão enganosa, objetivo mal especificado, custo de avaliação proibitivo) — seção 13.5;
- operadores genéticos: seleção (roleta, torneio, ranqueamento), crossover (um ponto, múltiplos pontos, uniforme), mutação (taxa de mutação e convergência prematura) e elitismo — seção 13.6.

Não deve ser antecipado o conteúdo das seções 13.7 a 13.11 (aplicações em jogos, ferramentas e bibliotecas de terceiros como GeneticSharp e NEAT, vantagens e limitações comparadas, e estudos de caso), reservado à Semana 13, conforme o Cronograma. Conforme a observação da Semana 11, o Capítulo 13 é retomado nesta semana **desde o início** — a leitura pontual da seção 13.1 já feita na Semana 11 não substitui a leitura completa das seções 13.1 a 13.6 agora.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte VI, Capítulo 13, seções 13.1 a 13.6 |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, já contendo os quatro Micro Games anteriores |
| **Cena Unity utilizada** | Nova cena mínima para o Micro Game Genetic Lab, hospedando um problema simples e bem definido (por exemplo, aproximar uma string-alvo ou maximizar a soma dos genes de um cromossomo — problema tipo "OneMax"), sem elementos visuais complexos |
| **Assets** | Nenhum asset de arte adicional necessário; elementos visuais permanecem primitivos simples ou apenas saída em texto/console, conforme os Micro Games anteriores |
| **Exemplos** | Diagrama da anatomia de uma população genética (população, indivíduo, cromossomo, gene, aptidão — seção 13.2); fluxograma do ciclo completo do Algoritmo Genético (seção 13.3); traçado de um crossover de um ponto entre dois cromossomos pequenos (seção 13.6) |
| **Vídeos** | Não é necessário vídeo externo para a fundamentação teórica; a demonstração é conduzida ao vivo pelo professor, traçando manualmente um exemplo pequeno de seleção, crossover e mutação |
| **Jogos para Engenharia Reversa** | Não aplicável nesta semana — a Semana 12 é regular (🔵), sem momento de Engenharia Reversa previsto no Cronograma |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação de Algoritmos Genéticos — o problema da otimização em espaços enormes, o vocabulário evolutivo, o ciclo completo do algoritmo, a representação do problema e a função de aptidão.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura da Unidade V e motivação | 10 min | Situar a nova pergunta da Unidade e retomar a explosão combinatória | Anuncia a transição da Unidade IV (busca adversarial) para a Unidade V (otimização automática); apresenta o problema de espaços de busca gigantescos (por exemplo, combinações de parâmetros de uma IA inimiga), retomando a explosão combinatória já vista no Minimax (Módulo 4) | Relacionam o novo problema à explosão combinatória (b^d) estudada no Módulo 4, reconhecendo o padrão recorrente de espaços grandes demais para busca exaustiva |
| 2. Otimização heurística | 10 min | Introduzir a ideia de "bom o suficiente" | Apresenta a seção 13.1: a busca exaustiva como inviável, e a otimização heurística como busca por soluções boas em tempo aceitável, retomando o sentido de heurística já usado no A* (Módulo 2) | Discutem, em duplas, um exemplo de problema de jogo em que "bom o suficiente" é preferível a "ótimo, mas inatingível" |
| 3. Vocabulário evolutivo | 20 min | Fixar os termos fundamentais no sentido computacional | Apresenta a seção 13.2: indivíduo, cromossomo, gene, população, aptidão e seleção natural artificial, usando o exemplo de ajuste de parâmetros de uma IA inimiga | Aplicam os termos a um exemplo proposto pelo professor, identificando o que seria o indivíduo, o cromossomo, cada gene e a aptidão de uma solução candidata |
| 4. Ciclo completo do Algoritmo Genético | 20 min | Apresentar as oito etapas do algoritmo, na ordem | Apresenta a seção 13.3: inicialização, avaliação, seleção, cruzamento, mutação, elitismo, nova geração e critério de parada, destacando o caráter cíclico do processo | Registram, em um esquema próprio, as oito etapas e identificam quais delas correspondem aos "operadores genéticos" (seleção, cruzamento, mutação, elitismo) |
| 5. Representação do problema | 15 min | Ensinar a importância de uma boa codificação de cromossomo | Apresenta a seção 13.4: representações binária, por valores reais, por permutação e estruturada, e o risco de representações que geram soluções inválidas | Avaliam, em duplas, duas propostas de representação para um problema simples, identificando qual tende a gerar mais soluções inválidas e por quê |
| 6. Função de aptidão | 15 min | Consolidar o papel central da função de aptidão | Apresenta a seção 13.5: a função de aptidão como única forma de comunicar o objetivo ao algoritmo, o paralelo com a recompensa do RL (Módulo 6) e os riscos de funções mal projetadas (aptidão enganosa, objetivo mal especificado) | Propõem, em duplas, uma função de aptidão simples (soma ponderada de critérios) para o problema que será implementado no Encontro 2 |

---

## Encontro 2 (1h30)

**Foco:** Operadores genéticos (seleção, crossover, mutação, elitismo) e início da implementação guiada do Micro Game Genetic Lab.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando o ciclo de oito etapas e a diferença entre representação e função de aptidão | Respondem perguntas de verificação oral, relacionando os conceitos à implementação que será iniciada em seguida |
| 2. Operadores genéticos | 25 min | Apresentar seleção, crossover, mutação e elitismo | Apresenta a seção 13.6: seleção por roleta, torneio e ranqueamento; crossover de um ponto, múltiplos pontos e uniforme; mutação e taxa de mutação; elitismo; traça ao vivo um exemplo pequeno de crossover de um ponto e de mutação | Acompanham o traçado do exemplo, identificando o ponto de corte do crossover e o gene alterado pela mutação |
| 3. Implementação guiada em C# | 40 min | Iniciar o Micro Game Genetic Lab | Acompanha os grupos na implementação de uma população inicial aleatória, da função de aptidão definida no Encontro 1, da seleção por torneio, do crossover de um ponto, da mutação com taxa pequena e do elitismo, aplicados a um problema simples (por exemplo, aproximar uma string-alvo ou maximizar a soma dos genes) | Implementam, em grupo, a estrutura inicial do laço evolutivo em C#, testando se a aptidão média e a melhor aptidão da população melhoram ao longo das gerações |
| 4. Discussão técnica | 10 min | Consolidar a compreensão da implementação realizada | Conduz a discussão sobre a curva de aptidão observada por cada grupo (saltos e platôs), relacionando-a à seção 13.3, e questiona sobre o efeito da taxa de mutação escolhida | Comparam informalmente a evolução da aptidão entre grupos e levantam hipóteses sobre o efeito da taxa de mutação e do tamanho da população |
| 5. Encerramento | 5 min | Fechar a semana e indicar o caminho da Semana 13 | Recapitula os fundamentos e operadores estudados, confirma que não há entrega formal nesta semana, e anuncia que a Semana 13 aprofunda a aplicação dos Algoritmos Genéticos a um problema mais expressivo, consolidando o Micro Game Genetic Lab | Registram pendências da implementação iniciada, para continuidade na Semana 13 |

---

## Micro Game

**Micro Game em desenvolvimento:** Genetic Lab (Módulo 5) — **início**.

**Objetivo pedagógico:** demonstrar como um Algoritmo Genético simples — combinando população, aptidão e os quatro operadores genéticos (seleção, cruzamento, mutação, elitismo) — encontra automaticamente boas soluções para um problema pequeno e bem definido, sem necessidade de busca exaustiva, evidenciando na prática o ciclo evolutivo apresentado no Encontro 1.

**Funcionalidades esperadas ao final da Semana 12:**

- uma população inicial de indivíduos gerada aleatoriamente, com uma representação (cromossomo) adequada ao problema escolhido;
- uma função de aptidão implementada para o problema simples definido pelo grupo (por exemplo, aproximar uma string-alvo ou maximizar a soma dos genes de um cromossomo);
- os operadores de seleção por torneio, crossover de um ponto, mutação com taxa configurável e elitismo, integrados ao laço evolutivo;
- evidência observável de que a melhor aptidão da população melhora (ou, no mínimo, não piora) ao longo das gerações, graças ao elitismo.

**Relação com módulos anteriores:** inaugura o Módulo 5 e a Unidade V, retomando o padrão de implementação própria em C# já exercitado no Módulo 4 (Minimax com heurística e poda), diante da ausência de uma solução oficial simples da Unity para Algoritmos Genéticos. A construção de uma função de aptidão como soma ponderada de critérios ecoa diretamente a função de avaliação do Minimax (Módulo 4) e os mapas de influência (Módulo 3), reforçando um padrão recorrente da disciplina. O Micro Game Genetic Lab será consolidado na Semana 13, quando o problema será tornado mais expressivo.

---

## Engenharia Reversa

Não aplicável nesta semana. A Semana 12 é uma semana regular (🔵), sem Desafio de Escolha Tecnológica nem momento de Engenharia Reversa previstos no Cronograma. O próximo momento de Engenharia Reversa (o quinto da disciplina) está previsto para a Semana 13, relacionando otimização automática a balanceamento ou geração procedural em jogos comerciais.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C#** | Implementação própria do laço evolutivo e dos operadores genéticos (seleção, crossover, mutação, elitismo), aplicados ao problema simples escolhido pelo grupo |
| **Unity (cena mínima)** | Utilizada apenas para hospedar a lógica do Micro Game Genetic Lab e, se pertinente, exibir a evolução da aptidão ao longo das gerações |

Nenhuma ferramenta oficial da Unity é utilizada para Algoritmos Genéticos nesta semana: a implementação permanece própria em C#, conforme indicado pelo Cronograma. Bibliotecas de terceiros (como a GeneticSharp) e a neuroevolução (como o NEAT) são contextualizadas na Apostila na seção 13.8, reservada à Semana 13, e não devem ser antecipadas.

---

## Atividade de Laboratório

**Objetivo:** implementar, em grupo, a estrutura inicial de um Algoritmo Genético simples em C#, aplicando os quatro operadores genéticos a um problema pequeno e bem definido, e observar a melhoria da aptidão ao longo das gerações.

**Etapas:**

1. Escolher, em grupo, um problema pequeno e bem definido para o Micro Game Genetic Lab (por exemplo, aproximar uma string-alvo ou maximizar a soma dos genes de um cromossomo — problema tipo "OneMax").
2. Definir a representação do cromossomo (por exemplo, vetor de genes binários ou inteiros) e implementar a geração de uma população inicial aleatória.
3. Implementar a função de aptidão definida no Encontro 1, como soma ponderada de critérios quando aplicável.
4. Implementar a seleção por torneio, escolhendo pais com maior chance para os indivíduos mais aptos.
5. Implementar o crossover de um ponto, combinando os genes de dois pais para gerar descendentes.
6. Implementar a mutação, alterando genes ao acaso com uma taxa pequena e configurável.
7. Implementar o elitismo, preservando o melhor indivíduo de cada geração na geração seguinte.
8. Rodar o laço evolutivo por um número definido de gerações, registrando a evolução da melhor aptidão e da aptidão média da população.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma implementação inicial funcional do Micro Game Genetic Lab, capaz de evoluir uma população em direção a soluções melhores para o problema escolhido, com os quatro operadores genéticos identificáveis no código e evidência observável de melhoria da aptidão ao longo das gerações.

---

## Verificação da Aprendizagem

A Semana 12 é uma semana regular e **não encerra o Módulo 5** — as entregas e a nota do módulo são geradas apenas ao final da Semana 13, conforme o Cronograma e os Critérios de Notas. Ainda assim, o professor deve utilizar a discussão técnica do Encontro 2 como oportunidade de feedback formativo, observando informalmente, à luz da Rubrica de Avaliação:

- **Compreensão Conceitual** — se o estudante distingue corretamente indivíduo, cromossomo, gene, população e aptidão, e se compreende a diferença entre otimização evolutiva e aprendizagem por interação (RL);
- **Aplicação Prática** — se a implementação inicial do Micro Game Genetic Lab reflete corretamente os quatro operadores genéticos estudados, com evidência de melhoria da aptidão ao longo das gerações.

Este feedback antecipa fragilidades antes da consolidação do Micro Game e das demais entregas do módulo, previstas para a Semana 13, quando a nota do Módulo 5 será efetivamente lançada.

---

## Entregas

Conforme o Cronograma, não há entrega formal prevista para a Semana 12. O Micro Game Genetic Lab, iniciado nesta semana, permanece em desenvolvimento no AI Playground de cada grupo e será consolidado na Semana 13, junto com o Desafio de Escolha Tecnológica do Módulo 5, o AI Design Log correspondente e o quinto momento de Engenharia Reversa.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir Algoritmo Genético com Aprendizagem por Reforço, tratando-os como a mesma coisa por ambos "melhorarem com o tempo" | Retomar o quadro de Atenção da seção 13.1, reforçando que o GA busca uma configuração ótima em um espaço de candidatos, enquanto o RL aprende um comportamento por interação ao longo de episódios |
| Escolher uma representação de cromossomo que gera, com frequência, soluções inválidas para o problema escolhido | Retomar a seção 13.4 e o Erro Comum associado, pedindo que o grupo verifique se operações de crossover e mutação sobre cromossomos válidos tendem a produzir cromossomos também válidos |
| Definir uma função de aptidão pouco graduada (quase todas as soluções recebem a mesma aptidão), deixando a busca "cega" | Retomar a seção 13.5, pedindo que o grupo teste a função de aptidão manualmente em duas ou três soluções de qualidade visivelmente diferente, verificando se os valores retornados também diferem |
| Configurar uma taxa de mutação muito alta ou muito baixa, levando a uma busca aleatória ou a uma convergência prematura | Retomar a seção 13.6, sugerindo valores típicos pequenos (entre aproximadamente 0,1% e 5% por gene) e orientando o grupo a observar a curva de aptidão para diagnosticar o problema |
| Implementar o elitismo de forma excessiva (preservando grande parte da população), sufocando a diversidade e acelerando a convergência prematura | Retomar a Boa Prática da seção 13.6, recomendando preservar apenas uma pequena fração da população (por exemplo, 1 a 5%) |

---

## Preparação para a Próxima Semana

Para a Semana 13 (Aplicação de Algoritmos Genéticos — encerramento da Unidade V), o professor deve:

- confirmar que todos os grupos possuem, ao final da Semana 12, uma implementação inicial funcional do Micro Game Genetic Lab, com os quatro operadores genéticos identificáveis no código;
- solicitar a leitura prévia da Parte VI, Capítulo 13 da Apostila, seções 13.7 a 13.11 (aplicações em jogos, ferramentas, vantagens e limitações, e estudos de caso);
- anunciar que a Semana 13 aprofundará a aplicação dos Algoritmos Genéticos a um problema mais expressivo do que o utilizado nesta semana, discutindo convergência, diversidade e ajuste de parâmetros;
- reservar, para a Semana 13, a consolidação do Micro Game Genetic Lab, o Desafio de Escolha Tecnológica do Módulo 5 e o quinto momento de Engenharia Reversa, relacionando otimização automática a balanceamento ou geração procedural em jogos comerciais, conforme o Cronograma.
