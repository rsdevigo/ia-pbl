# Plano de Aula — Semana 2

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 2 de 17 |
| **Unidade** | Unidade I — Fundamentos e Decisão de NPCs (Semanas 1–4) |
| **Módulo** | Módulo 1 — Como um NPC decide o que fazer? |
| **Tema** | Máquinas de Estado Finitas |
| **Pergunta Norteadora** | Como um NPC decide o que fazer? (parte 1) |
| **Tipo de semana** | 🔵 Regular (fundamentação e desenvolvimento do Micro Game) |

---

## Objetivos de Aprendizagem

Ao final da Semana 2, o estudante deverá ser capaz de:

1. **Explicar** o problema que a FSM resolve — organizar comportamentos mutuamente exclusivos ao longo do tempo, superando a falta de memória de contexto das cadeias de condicionais.
2. **Definir** com precisão os quatro conceitos elementares da FSM: estado, transição, evento (guarda de transição) e ação.
3. **Relacionar** a FSM à sua raiz teórica nos autômatos finitos, justificando por que seu caráter finito e determinístico produz previsibilidade e depurabilidade.
4. **Distinguir** FSM baseada em polling de FSM baseada em eventos, indicando quando cada uma é mais adequada em termos de custo computacional.
5. **Aplicar** o ciclo enter/update/exit na descrição de um estado, evitando o erro clássico de colocar ações de entrada dentro do update.
6. **Reconhecer** o Animator Controller da Unity como uma implementação visual dos conceitos de estado, transição e guarda.
7. **Implementar**, em grupo, uma primeira versão do Micro Game NPC Decision utilizando uma FSM com no mínimo três estados.
8. **Identificar**, a partir da própria implementação, os primeiros sintomas da explosão de transições em uma FSM plana.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte II, Capítulo 3 da Apostila — Máquinas de Estado Finitas (FSM)**:

- o problema resolvido pela FSM (seção 3.1);
- estados, transições, eventos/guardas e ações (seção 3.2), incluindo a raiz nos autômatos finitos (3.2.1) e guardas de transição com prioridade (3.2.2);
- funcionamento da FSM: laço de avaliação por quadro, FSM por polling versus por eventos (3.3.1) e o ciclo enter/update/exit (3.3.2);
- exemplo canônico do inimigo guarda com cinco estados (3.4);
- vantagens e limitações da FSM, com destaque para a explosão de transições (3.5, 3.5.1);
- aplicações em jogos comerciais (3.6);
- materialização da FSM no Animator Controller e, brevemente, no Visual Scripting da Unity (3.7) — este último apenas citado como alternativa visual equivalente, sem prática dedicada nesta semana.

Não devem ser antecipados conteúdos de máquinas de estado hierárquicas (Capítulo 4) nem de árvores de comportamento (Capítulo 6): a explosão de transições deve ser apresentada como um problema em aberto, sem apresentar ainda sua solução.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte II, Apresentação e Capítulo 3 (completo); revisão da Parte I, seção 1.3 (ciclo Sentir-Pensar-Agir), para retomar a conexão com a Semana 1 |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo (criado na Semana 1) |
| **Cena Unity utilizada** | Cena de demonstração simples, com um único NPC (cápsula ou modelo provisório) e um ponto de referência para o jogador, usada para a demonstração de FSM no Encontro 1 |
| **Assets** | Nenhum asset de arte específico necessário; um modelo provisório (placeholder) é suficiente para o NPC |
| **Exemplos** | Exemplo do inimigo guarda de cinco estados (Patrulhar, Investigar, Perseguir, Atacar, Fugir), conforme tabela da seção 3.4 da Apostila; exemplo do ciclo econômico de uma unidade coletora de RTS, para reforçar a generalidade da técnica |
| **Vídeos** | Vídeo curto de gameplay de *Pac-Man* (1980), retomado da Semana 1, agora reinterpretado como FSM (estados *chase*, *scatter*, *frightened*) [VÍDEO NECESSÁRIO — a ser selecionado pelo professor entre fontes legítimas de gameplay] |
| **Jogos para Engenharia Reversa** | Não previsto nesta semana (ver seção "Engenharia Reversa" abaixo) |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação teórica de FSM e demonstração de uma FSM simples no Unity via Animator/scripting.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 10 min | Reconectar com a Semana 1 e apresentar a pergunta norteadora do módulo | Retoma o ciclo Sentir-Pensar-Agir e apresenta a pergunta "como um NPC decide o que fazer?", situando a FSM como primeira resposta | Relembram o ciclo Sentir-Pensar-Agir e antecipam hipóteses sobre como organizar decisões |
| 2. O problema da FSM | 10 min | Mostrar por que uma cadeia de condicionais reavaliada a cada quadro é insuficiente | Apresenta o pseudocódigo de condicionais da seção 3.1 e discute a falta de memória de contexto | Analisam em grupo o exemplo do guarda que precisa investigar um ruído antes de voltar a patrulhar |
| 3. Fundamentos: estado, transição, evento, ação | 20 min | Definir com precisão os quatro conceitos elementares da FSM e justificar por que o caráter finito e determinístico do autômato produz previsibilidade e depurabilidade | Apresenta a seção 3.2, com apoio no diagrama de três estados (Patrulhar, Perseguir, Atacar); introduz a raiz nos autômatos finitos (3.2.1), explicando que, por a máquina ser finita e determinística, todos os estados podem ser enumerados e todas as transições revisadas de antemão — é essa propriedade, e não acaso, que torna a FSM previsível e depurável | Identificam estados, transições, eventos e ações em exemplos de NPCs de jogos conhecidos; verbalizam, a partir de um exemplo dado, por que conseguem prever o comportamento do NPC apenas olhando seus estados e transições |
| 4. Guardas de transição e prioridade | 10 min | Explicar guardas de transição e o problema da prioridade entre transições concorrentes | Apresenta a seção 3.2.2, incluindo o exemplo de "distância < 2 m" versus "vida < 10%" | Discutem em duplas como resolveriam o desempate entre duas guardas verdadeiras simultaneamente |
| 5. Funcionamento: polling, eventos e enter/update/exit | 20 min | Apresentar o laço de execução da FSM e o ciclo enter/update/exit | Expõe o pseudocódigo da seção 3.3, contrasta FSM por polling e por eventos (3.3.1), e detalha o ciclo enter/update/exit (3.3.2), incluindo o erro comum do som de alerta no update | Classificam, para o exemplo do guarda, quais condições convêm por polling e quais por evento |
| 6. Exemplo consolidado e aplicações em jogos | 10 min | Consolidar os conceitos no exemplo canônico do guarda de cinco estados e reconhecer a FSM em jogos comerciais | Apresenta a tabela do guarda de cinco estados (Patrulhar, Investigar, Perseguir, Atacar, Fugir — seção 3.4) e os exemplos de *Pac-Man* e *Half-Life* (seção 3.6), destacando também as vantagens gerais da FSM (simplicidade, baixo custo, previsibilidade, depurabilidade, autoria visual — seção 3.5) como síntese antes da demonstração no Unity | Relacionam cada estado e transição do exemplo do guarda aos quatro conceitos elementares; reconhecem estados equivalentes nos exemplos de mercado apresentados |
| 7. Demonstração no Unity (Animator) | 10 min | Mostrar a FSM materializada no Animator Controller | Demonstra ao vivo um Animator Controller simples com dois ou três estados e transições com parâmetros (guardas), mapeando cada elemento aos conceitos da seção 3.7; menciona brevemente o Visual Scripting como alternativa visual equivalente, sem se deter nele | Observam a demonstração e relacionam estado/transição/guarda aos elementos do editor |

---

## Encontro 2 (1h30)

**Foco:** Implementação guiada da primeira versão do Micro Game NPC Decision usando FSM, com discussão sobre os limites de uma FSM plana.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando os quatro conceitos elementares e o ciclo enter/update/exit | Respondem perguntas de verificação oral |
| 2. Do esboço ao design da FSM | 15 min | Traduzir o esboço conceitual do Micro Game 1 (Semana 1) em uma FSM concreta | Orienta cada grupo a listar os estados, transições e guardas do próprio NPC, a partir do esboço já produzido | Definem, em grupo, de três a cinco estados para o NPC do Micro Game, com suas transições e prioridades |
| 3. Implementação guiada | 40 min | Implementar a primeira versão funcional da FSM no Unity | Acompanha os grupos na implementação (via Animator, script com `enum`/`switch`, ou padrão *State* em C#, conforme o nível de cada grupo), reforçando o ciclo enter/update/exit | Implementam os estados definidos e testam as transições no Micro Game |
| 4. Testes e ajustes | 10 min | Verificar se o comportamento implementado corresponde ao esperado | Circula entre os grupos, questionando "por que o NPC está fazendo isso agora?" para verificar depurabilidade | Testam a FSM implementada e corrigem transições incorretas ou ausentes |
| 5. Discussão técnica: limites da FSM plana | 10 min | Introduzir, a partir da prática, a explosão de transições | Pergunta aos grupos o que aconteceria se fossem adicionados mais estados (por exemplo, "esconder-se", "chamar reforços"); conduz a leitura conjunta da seção 3.5.1 | Estimam quantas transições seriam necessárias e percebem o crescimento quadrático |
| 6. Encerramento | 5 min | Fechar a semana e indicar o caminho da próxima | Recapitula o que foi implementado e anuncia o tema da Semana 3 (Máquinas de Estado Hierárquicas), como resposta à explosão de transições | Registram pendências e dúvidas para o próximo encontro |

---

## Micro Game

**Micro Game em desenvolvimento:** NPC Decision (Módulo 1).

**Objetivo pedagógico:** demonstrar como um NPC decide o que fazer, evoluindo de uma Máquina de Estados Finita simples até uma Árvore de Comportamento com Blackboard ao longo do Módulo 1.

**Estado ao final da Semana 2:** primeira versão implementada, contendo:

- de três a cinco estados definidos a partir do esboço da Semana 1 (por exemplo: Patrulhar, Perseguir, Atacar);
- transições com guardas explícitas e prioridade definida entre elas;
- ações de entrada, permanência e saída implementadas para cada estado (ciclo enter/update/exit);
- comportamento observável e testável em tempo de execução no Unity.

**Relação com módulos anteriores:** dá continuidade direta ao esboço conceitual produzido na Semana 1, sendo a primeira implementação efetiva do Micro Game 1. Servirá de base para a evolução prevista na Semana 3, quando a mesma FSM será reestruturada em uma HFSM.

---

## Engenharia Reversa

Não há atividade formal de Engenharia Reversa prevista para a Semana 2, conforme o Cronograma — o primeiro momento formal ocorre na Semana 4, junto à apresentação da metodologia de Engenharia Reversa (Capítulo 14 da Apostila).

O exemplo de *Pac-Man* utilizado na seção "Aplicações e jogos conhecidos" (3.6) da Apostila deve ser tratado como **ilustração conceitual** da FSM, e não como exercício estruturado de Engenharia Reversa. O professor pode reconectar esse exemplo ao já discutido na Semana 1, agora nomeando formalmente os estados *chase*, *scatter* e *frightened*, mas sem aprofundar hipóteses de arquitetura — essa prática estruturada permanece reservada à Semana 4.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Animator Controller** | Demonstração da FSM materializada visualmente, com estados, transições e parâmetros como guardas |
| **Scripting C#** | Implementação da FSM do NPC Decision, via `enum`/`switch` ou padrão de projeto *State*, conforme o nível de cada grupo |

Nenhuma ferramenta de terceiros é apresentada nesta semana — a comparação com soluções como NodeCanvas e Behavior Designer é reservada ao Capítulo 6 (Semana 4), quando se discutem árvores de comportamento.

---

## Atividade de Laboratório

**Objetivo:** implementar a primeira versão funcional do Micro Game NPC Decision utilizando uma Máquina de Estados Finita.

**Etapas:**

1. A partir do esboço da Semana 1, cada grupo lista de três a cinco estados para o NPC, com suas transições e a prioridade entre elas.
2. Implementação dos estados no Unity (Animator, script próprio ou padrão *State*), com ações de entrada, permanência e saída claramente separadas.
3. Teste do comportamento resultante, verificando se as transições ocorrem nas condições esperadas e se a prioridade entre guardas concorrentes está correta.
4. Reflexão em grupo sobre o que aconteceria à FSM caso novos estados fossem adicionados, antecipando a discussão da explosão de transições.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma FSM funcional de três a cinco estados implementada no Micro Game NPC Decision, com comportamento observável e testável, ainda sem qualquer estrutura hierárquica.

---

## Verificação da Aprendizagem

O Módulo 1 se encerra formalmente apenas na Semana 4, quando ocorrem o Desafio de Escolha Tecnológica, o AI Design Log e a Engenharia Reversa do módulo. A verificação nesta semana é, portanto, **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes definem corretamente estado, transição, evento e ação, e se relacionam a FSM à sua raiz nos autômatos finitos (critério **Compreensão Conceitual** da Rubrica);
- observação da implementação guiada no Encontro 2, verificando se o comportamento da FSM corresponde ao esperado e se o ciclo enter/update/exit foi corretamente aplicado (primeiro indício do critério **Aplicação Prática**, formalmente avaliado na consolidação do Micro Game na Semana 4);
- discussão técnica de encerramento, avaliando se os grupos conseguem antecipar, com argumentos próprios, os limites da FSM plana diante de um número crescente de estados (indício inicial do critério **Tomada de Decisão**);
- observação do uso correto do Animator Controller na demonstração e na implementação, quando aplicável (indício inicial do critério **Uso da Unity e do Ecossistema**).

Nenhuma nota é atribuída nesta semana, conforme os Critérios de Notas da disciplina, que vinculam a composição da nota aos módulos encerrados nas Semanas 4, 7, 9, 11, 13 e 16, ao checkpoint da Semana 8 e à apresentação final da Semana 17.

---

## Entregas

Não há entrega formal prevista para a Semana 2, conforme o Cronograma.

A primeira versão implementada da FSM do Micro Game NPC Decision permanece com os grupos, para evolução na Semana 3 (transição para HFSM) e consolidação na Semana 4, quando passa a compor o Micro Game entregável, o AI Design Log e o Desafio de Escolha Tecnológica do Módulo 1.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir ação de permanência (update) com ações de entrada/saída, repetindo efeitos que deveriam ocorrer uma única vez (ex.: som de alerta a cada quadro) | Retomar a pergunta orientadora da seção 3.3.2: "isto deve acontecer uma vez, ao mudar de modo, ou continuamente, enquanto estou neste modo?" |
| Definir transições sem prioridade explícita, resultando em comportamento inconsistente quando duas guardas são verdadeiras ao mesmo tempo | Usar o exemplo "distância < 2 m" versus "vida < 10%" da Apostila para tornar concreta a necessidade de uma ordem de prioridade definida conscientemente |
| Tentar implementar, já na primeira versão, um número excessivo de estados, antecipando a explosão de transições antes da hora | Redirecionar o grupo para um escopo de três a cinco estados, reforçando os critérios de escopo reduzido definidos para os Micro Games |
| Dificuldade em decidir entre Animator, script próprio ou padrão *State* para a implementação | Orientar conforme o nível técnico do grupo: Animator para maior familiaridade visual; script/`switch` para grupos com mais domínio de C#; deixar claro que o conceito avaliado é o mesmo em qualquer abordagem |

---

## Preparação para a Próxima Semana

Para a Semana 3 (Máquinas de Estado Hierárquicas), o professor deve:

- solicitar a leitura prévia do Capítulo 4 da Apostila (Máquinas de Estado Hierárquicas);
- garantir que todos os grupos tenham, de fato, uma FSM funcional implementada no Micro Game NPC Decision ao final da Semana 2;
- revisar rapidamente a FSM de cada grupo antes do próximo encontro, identificando quais já apresentam sinais de explosão de transições, para usá-los como exemplos concretos na fundamentação da Semana 3;
- não é necessária nenhuma instalação ou configuração adicional de ferramentas: a Semana 3 dá continuidade ao uso de Scripting C# já iniciado nesta semana.
