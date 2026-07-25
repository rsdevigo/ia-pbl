# Plano de Aula — Semana 1

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 1 de 17 |
| **Unidade** | Unidade I — Fundamentos e Decisão de NPCs (Semanas 1–4) |
| **Módulo** | Módulo 1 — Como um NPC decide o que fazer? *(abertura do módulo)* |
| **Tema** | Abertura da disciplina, fundamentos de IA em jogos e apresentação do Projeto Integrador |
| **Pergunta Norteadora** | O que é Inteligência Artificial em jogos, e por que "ilusão"? |
| **Tipo de semana** | 🔵 Regular (fundamentação e organização do projeto) |

---

## Objetivos de Aprendizagem

Ao final da Semana 1, o estudante deverá ser capaz de:

1. **Diferenciar** a IA de jogos da IA acadêmica, identificando seus critérios de sucesso distintos (credibilidade, diversão, custo computacional e controle do designer versus otimalidade e generalidade).
2. **Explicar** o conceito de ilusão de inteligência e relacioná-lo à distinção entre IA forte e IA fraca.
3. **Descrever** o ciclo Sentir → Pensar → Agir e classificar um agente como reativo, deliberativo ou híbrido.
4. **Relacionar** a evolução histórica das técnicas de IA de jogos às restrições de hardware de cada época, reconhecendo exemplos documentados (Pac-Man, Half-Life, Halo 2, F.E.A.R.).
5. **Reconhecer** a estrutura da disciplina, a metodologia PBL e o papel do AI Playground como Projeto Integrador.
6. **Organizar-se** em grupo de trabalho (2 a 4 estudantes) e **esboçar** um plano inicial para o Micro Game NPC Decision, sem realizar implementação.

---

## Conteúdos

Conteúdos previstos no Cronograma para esta semana, correspondentes à **Parte I da Apostila**:

- Capítulo 1 — O que é Inteligência Artificial em Jogos (problema da IA de jogos, ilusão de inteligência, ciclo Sentir–Pensar–Agir, agentes reativos/deliberativos/híbridos, critérios de qualidade — com destaque para custo computacional/orçamento de quadro (Seção 1.4.1) e controle do designer (Seção 1.4.2) —, mapa das famílias de técnicas);
- Capítulo 2 — História e Evolução da IA em Jogos (coevolução entre hardware e técnica, dos padrões de perseguição dos arcades à era dos dados).

Não devem ser antecipados conteúdos de máquinas de estado (Capítulo 3) ou de qualquer outra Parte da Apostila: a Semana 1 é exclusivamente conceitual e organizacional.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte I completa (Apresentação, Capítulo 1, Capítulo 2, Encerramento); Plano de Ensino; Cronograma; Rubrica de Avaliação (seção 1, "Filosofia da Avaliação", e seção 5, composição de critérios por instrumento); Critérios de Notas (itens 4 e 5, pesos); Modelos de Entrega do Aluno (a serem distribuídos à turma neste encontro) |
| **Materiais necessários** | Projetor/tela para apresentação; quadro para registrar a formação dos grupos; computadores com Unity Hub instalado para os estudantes |
| **Cena Unity utilizada** | Nenhuma cena de IA ainda. Apenas criação de um projeto Unity vazio (template 3D ou 2D, conforme padrão já adotado nas demais disciplinas do curso), que servirá de base para o AI Playground |
| **Assets** | Nenhum asset de IA necessário nesta semana |
| **Exemplos** | Trechos de gameplay (vídeo ou demonstração ao vivo) de *Pac-Man* (1980), *Space Invaders* (1978) e *Half-Life* (1998), para ilustrar a Seção 2.2–2.3 da Apostila. [IMAGEM/VÍDEO NECESSÁRIO — descrever para produção posterior: capturas de gameplay de domínio público ou emulador, evitando reprodução de material protegido sempre que possível; alternativamente, usar as ilustrações esquemáticas já descritas na Apostila (Figuras 1.1, 1.2, 2.1, 2.2)] |
| **Vídeos** | Vídeo curto (3–5 min) mostrando os quatro fantasmas de *Pac-Man* em jogo, para apoiar a discussão de 2.2.1. [VÍDEO NECESSÁRIO — a ser selecionado pelo professor entre fontes legítimas de gameplay] |
| **Jogos para Engenharia Reversa** | Não previsto nesta semana (ver seção "Engenharia Reversa" abaixo) |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação teórica — o que é IA de jogos e por que ela é uma "ilusão".

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura | 10 min | Situar a disciplina no curso e apresentar a pergunta norteadora do semestre | Apresenta a disciplina, a ementa, a filosofia PBL e a pergunta "o que é IA em jogos, e por que ilusão?" | Ouvem, fazem perguntas iniciais |
| 2. IA de jogos x IA acadêmica | 20 min | Diferenciar os dois campos a partir de seus critérios de sucesso | Expõe a distinção da Seção 1.1–1.1.2 da Apostila, usando a tabela comparativa (objetivo, critério de sucesso, custo computacional, controle do designer); fecha a etapa com os dois critérios da Seção 1.4 tratados de forma concreta: o orçamento de quadro (~16,7 ms disponíveis a 60 FPS, dividido entre IA, física, gráficos e áudio) e o controle do designer como conteúdo autoral (cita rapidamente Unity Behavior/Animator como ferramentas que existem para dar esse controle, sem entrar no funcionamento — a ferramenta só será ensinada quando o conceito correspondente chegar) | Comparam exemplos de jogos e discutem por que uma IA "ótima" pode ser um mau design |
| 3. Ilusão de inteligência | 20 min | Explicar IA forte x IA fraca e a ideia de comportamento convincente | Apresenta a Seção 1.2, incluindo o experimento de Heider e Simmel e o conceito de fluxo (Csíkszentmihályi) | Discutem em duplas exemplos de jogos em que perceberam "inteligência" que, na verdade, era simples |
| 4. Ciclo Sentir-Pensar-Agir e tipos de agente | 20 min | Apresentar o modelo unificador de agente e a classificação reativo/deliberativo/híbrido | Demonstra o ciclo com exemplos e apresenta a tabela da Seção 1.3.2 | Classificam, em grupo, exemplos de NPCs de jogos conhecidos como reativos, deliberativos ou híbridos |
| 5. Panorama histórico | 15 min | Relacionar a evolução das técnicas à evolução do hardware | Percorre a linha do tempo do Capítulo 2, com destaque para *Pac-Man*, *Half-Life*, *Halo 2* e *F.E.A.R.* | Observam a demonstração/vídeo e identificam qual técnica cada jogo provavelmente utiliza |
| 6. Encerramento e síntese | 5 min | Consolidar os conceitos-chave do encontro | Retoma o mapa de famílias de técnicas (Seção 1.5) e anuncia o Encontro 2 | Anotam dúvidas para o próximo encontro |

---

## Encontro 2 (1h30)

**Foco:** Apresentação da metodologia PBL, do AI Playground e organização inicial do trabalho semestral.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 | Conduz uma discussão breve recuperando ilusão de inteligência e ciclo Sentir-Pensar-Agir | Respondem perguntas de verificação oral |
| 2. Metodologia PBL | 15 min | Explicar como o semestre é estruturado em torno de um único projeto | Apresenta a lógica PBL, a organização em Unidades/Módulos e o papel do Desafio de Escolha Tecnológica e do AI Design Log; distribui os **Modelos de Entrega do Aluno**, que trazem o formato exigido de cada entrega do semestre, e a **Rubrica de Avaliação**, para que a turma conheça os critérios desde o primeiro encontro | Ouvem e relacionam a metodologia à sequência problema → fundamentos → aplicações → ferramentas → Micro Game |
| 3. O AI Playground e os Micro Games | 15 min | Apresentar o Projeto Integrador e sua composição em Micro Games independentes | Descreve o AI Playground como conjunto de Micro Games, cada um ligado a um módulo de conteúdo, e situa o Micro Game 1 (NPC Decision) no Módulo 1 | Visualizam o percurso completo do semestre a partir do Cronograma |
| 4. Formação dos grupos | 15 min | Organizar os estudantes em grupos de 2 a 4 pessoas | Orienta a formação dos grupos e registra a composição de cada um | Formam grupos e definem forma de comunicação/organização interna |
| 5. Setup inicial do projeto Unity | 20 min | Criar a base técnica comum do AI Playground | Orienta a criação de um projeto Unity vazio por grupo, com a estrutura de pastas que acomodará os futuros Micro Games | Criam o projeto Unity do AI Playground em seus computadores/repositórios |
| 6. Esboço do plano do Micro Game 1 | 10 min | Iniciar o planejamento conceitual do NPC Decision, sem implementação | Apresenta a pergunta do Módulo 1 ("como um NPC decide o que fazer?") e orienta o preenchimento de um esboço textual do Micro Game | Esboçam, em grupo, uma ideia inicial de cenário e NPC para o Micro Game 1 |
| 7. Encerramento | 5 min | Fechar a semana e indicar o caminho da próxima | Recapitula as entregas da semana e anuncia o tema da Semana 2 (Máquinas de Estado Finitas) | Registram pendências e dúvidas |

---

## Micro Game

**Micro Game em desenvolvimento:** NPC Decision (Módulo 1).

**Objetivo pedagógico:** ao longo do Módulo 1, demonstrar como um NPC decide o que fazer, evoluindo de uma Máquina de Estados Finita simples até uma Árvore de Comportamento com Blackboard.

**Estado ao final da Semana 1:** nenhuma implementação. O que se espera é apenas um **esboço conceitual** produzido pelo grupo, contendo:

- ideia geral do cenário do Micro Game (ambiente, objetivo do jogador);
- descrição informal do NPC e das situações às quais ele deverá reagir;
- lista preliminar de comportamentos observáveis esperados (por exemplo: patrulhar, perceber o jogador, perseguir, atacar).

**Relação com módulos anteriores:** não se aplica — trata-se do primeiro Micro Game do semestre. A Semana 1 estabelece o vocabulário conceitual (ciclo Sentir-Pensar-Agir, ilusão de inteligência) que será diretamente empregado a partir da Semana 2, quando o Micro Game passa a ser efetivamente implementado com Máquinas de Estado Finitas.

---

## Engenharia Reversa

Não há atividade formal de Engenharia Reversa prevista para a Semana 1, conforme o Cronograma — o primeiro momento formal ocorre na Semana 4, junto à apresentação da metodologia de Engenharia Reversa (Capítulo 14 da Apostila).

Ainda assim, os exemplos históricos discutidos no Encontro 1 (Seção 2.2 a 2.6 da Apostila — *Pac-Man*, *Half-Life*, *Halo 2*, *F.E.A.R.*) devem ser tratados como **ilustrações informais**, e não como exercício de Engenharia Reversa: o objetivo aqui é histórico e conceitual, não analítico. O professor deve evitar aprofundar hipóteses de arquitetura nesta semana, reservando essa prática estruturada para a Semana 4.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Unity** | Criação do projeto vazio que servirá de base para o AI Playground (setup inicial de pastas e organização do projeto) |

Nenhuma ferramenta específica de IA (Animator, Unity Behavior, AI Navigation, ML-Agents, Sentis) é utilizada nesta semana — sua introdução respeita a sequência didática de cada módulo, a partir da Semana 2.

---

## Atividade de Laboratório

**Objetivo:** organizar as condições de trabalho do semestre e produzir o primeiro artefato do Projeto Integrador.

**Etapas:**

1. Formação dos grupos (2 a 4 estudantes; ver a nota de dimensionamento de turma na Preparação do Professor), com registro pelo professor.
2. Criação, por grupo, de um projeto Unity vazio nomeado como AI Playground, com estrutura de pastas prevendo a futura adição de cada Micro Game.
3. Preenchimento de um esboço textual (documento simples, não necessariamente formatado) descrevendo cenário, NPC e comportamentos esperados do Micro Game NPC Decision.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter um projeto Unity criado e um esboço escrito do Micro Game 1, ainda sem qualquer implementação de lógica de IA.

---

## Verificação da Aprendizagem

Como a Semana 1 é predominantemente conceitual e organizacional, e o primeiro instrumento avaliativo formal do Módulo 1 (Micro Game, AI Design Log, Desafio de Escolha Tecnológica, Engenharia Reversa) só ocorre na Semana 4, a verificação nesta semana é **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes distinguem corretamente IA de jogos e IA acadêmica e se reconhecem a ideia de ilusão de inteligência (relacionado ao critério **Compreensão Conceitual** da Rubrica);
- observação da discussão em grupo sobre classificação de agentes (reativo/deliberativo/híbrido);
- leitura do esboço do Micro Game 1 produzido no Encontro 2, verificando se o grupo já consegue articular, mesmo informalmente, um problema de decisão de NPC — primeiro indício do critério **Tomada de Decisão**, que será formalmente avaliado a partir do Desafio de Escolha Tecnológica do Módulo 1 (Semana 4).

Nenhuma nota é atribuída nesta semana, conforme os Critérios de Notas da disciplina, que vinculam a composição da nota aos módulos encerrados nas Semanas 4, 7, 9, 11, 13 e 16, ao checkpoint da Semana 8 e à apresentação final da Semana 17.

---

## Entregas

| Entrega | Descrição | Caráter |
|---|---|---|
| Formação de grupos | Grupos de 2 a 4 estudantes registrados pelo professor | Organizacional, não avaliativa |
| Plano inicial do Micro Game 1 | Esboço textual do cenário, NPC e comportamentos esperados do NPC Decision | Formativa, insumo para a consolidação do Micro Game na Semana 4 |

Não há, nesta semana, entrega de Micro Game consolidado, AI Design Log ou Desafio de Escolha Tecnológica — esses instrumentos só surgem ao final do Módulo 1, na Semana 4.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir IA de jogos com IA acadêmica/aprendizado de máquina, esperando que a disciplina trate principalmente de redes neurais | Reforçar, com exemplos concretos, que a maior parte da indústria usa técnicas determinísticas; retomar a tabela comparativa da Seção 1.1.2 |
| Dificuldade em aceitar que uma IA "burra de propósito" pode ser um bom design | Usar o exemplo do "tiro de aviso" e do canal de fluxo (Seção 1.2.3) para tornar a ideia concreta |
| Grupos formados sem afinidade de trabalho ou desequilíbrio de habilidades técnicas | Professor pode mediar a formação de grupos, sugerindo equilíbrio entre perfis mais técnicos e mais voltados a design |
| Esboço do Micro Game excessivamente ambicioso ou distante do escopo de um Micro Game | Relembrar os critérios de escopo reduzido definidos para os Micro Games e redirecionar o grupo para uma ideia simples e demonstrável |

---

## Preparação para a Próxima Semana

Para a Semana 2 (Máquinas de Estado Finitas), o professor deve:

- solicitar a leitura prévia do Capítulo 3 da Apostila (Máquinas de Estado Finitas);
- garantir que todos os grupos tenham, de fato, um projeto Unity criado e funcional ao final da Semana 1;
- revisar o esboço do Micro Game 1 de cada grupo antes do próximo encontro, para adaptar exemplos da Semana 2 aos cenários propostos pelos próprios estudantes, quando possível;
- não é necessária nenhuma instalação ou configuração adicional de ferramentas: a Semana 2 utiliza Animator/Scripting C#, já nativos do Unity.
