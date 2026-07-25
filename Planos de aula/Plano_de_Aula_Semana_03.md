# Plano de Aula — Semana 3

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 3 de 17 |
| **Unidade** | Unidade I — Fundamentos e Decisão de NPCs (Semanas 1–4) |
| **Módulo** | Módulo 1 — Como um NPC decide o que fazer? |
| **Tema** | Máquinas de Estado Hierárquicas |
| **Pergunta Norteadora** | Como organizar decisões cada vez mais complexas de um NPC? |
| **Tipo de semana** | 🔵 Regular (fundamentação e desenvolvimento do Micro Game) |

---

## Objetivos de Aprendizagem

Ao final da Semana 3, o estudante deverá ser capaz de:

1. **Explicar** o problema que motiva a HFSM — a explosão de transições e a redundância de regras repetidas em FSMs planas grandes — retomando concretamente o limite identificado na Semana 2.
2. **Definir** com precisão os conceitos elementares da HFSM: superestado, subestado, configuração ativa (pilha de estados ativos) e estado inicial de cada nível.
3. **Explicar** o mecanismo de herança de transições e sua origem na avaliação em cascata, do nível externo (superestado) para o nível interno (subestado).
4. **Diferenciar** histórico raso de histórico profundo, e **justificar** em que situações o estado de histórico é indispensável para a credibilidade do comportamento e em que situações reiniciar pelo subestado inicial é a escolha correta.
5. **Aplicar** corretamente a ordem de disparo das ações enter/exit em transições que cruzam níveis da hierarquia, evitando o erro de omitir enter/exit de níveis intermediários.
6. **Reestruturar**, em grupo, a FSM plana implementada na Semana 2 em uma HFSM, agrupando estados em ao menos dois superestados coerentes.
7. **Comparar** tecnicamente FSM plana e HFSM, reconhecendo que a hierarquia administra a complexidade, mas não elimina o acoplamento nem a rigidez estrutural da família FSM.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte II, Capítulo 4 da Apostila — Máquinas de Estado Hierárquicas (HFSM)**:

- o problema resolvido pela HFSM: a explosão de transições e a redundância de regras comuns em FSMs planas grandes (seção 4.1);
- fundamentos da hierarquia: superestado, subestado, configuração ativa, estado inicial de cada nível e estado de histórico (seção 4.2);
- funcionamento: avaliação em cascata das transições do nível externo para o interno, herança de transições, transições entre níveis e a ordem correta das ações enter/exit (seções 4.3, 4.3.1);
- estado de histórico — histórico raso versus histórico profundo (seção 4.3.2);
- exemplo do inimigo com combate em camadas, organizado nos superestados Pacífico e Combate (seção 4.4);
- vantagens e limitações da HFSM, com destaque para o que ela *não* resolve — acoplamento e rigidez estrutural (seção 4.5);
- materialização da HFSM em sub-state machines e camadas de animação do Animator (seção 4.7).

Não fazem parte do escopo desta semana as aplicações em jogos comerciais (seção 4.6) nem o panorama de ferramentas de terceiros — NodeCanvas, Behavior Designer, State Tree da Unreal (seção 4.8): ambas ficam reservadas para a Semana 4, quando o Cronograma já prevê a comparação pontual com soluções de terceiros. Não devem ser antecipados, tampouco, conteúdos de árvores de decisão (Capítulo 5) nem de árvores de comportamento e Blackboard (Capítulo 6): a limitação da HFSM quanto a comportamento sequenciado e reordenável deve ser apresentada como um problema em aberto, sem apresentar ainda sua solução.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte II, Capítulo 4 (completo); revisão da seção 3.5.1 (explosão de transições), para retomar o ponto exato onde a Semana 2 parou |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com a FSM da Semana 2 já implementada |
| **Cena Unity utilizada** | A mesma cena de demonstração da Semana 2 (NPC provisório e ponto de referência do jogador), reaproveitada para mostrar a reestruturação de FSM em HFSM |
| **Assets** | Nenhum asset de arte adicional; segue-se com o modelo provisório do NPC já utilizado |
| **Exemplos** | Exemplo do inimigo guarda enriquecido com comportamento de combate em camadas (seção 4.4 da Apostila), organizado nos superestados Pacífico e Combate; tabela da Apostila com a hierarquia completa |
| **Vídeos** | Não previsto especificamente; se desejar, o professor pode retomar rapidamente o vídeo de *Pac-Man* já usado na Semana 2, apenas para lembrar o ponto de partida, sem introduzir novo material audiovisual |
| **Jogos para Engenharia Reversa** | Não previsto nesta semana (ver seção "Engenharia Reversa" abaixo) |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação de HFSM como resposta ao crescimento descontrolado de estados e transições da FSM plana. Demonstração de reestruturação hierárquica.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 10 min | Reconectar com o limite identificado na Semana 2 | Retoma a discussão de encerramento da Semana 2 sobre a explosão de transições e apresenta a pergunta norteadora "como organizar decisões cada vez mais complexas?" | Relembram o crescimento quadrático de transições estimado na semana anterior |
| 2. O problema: redundância de regras comuns | 15 min | Mostrar que o problema central não é apenas o número de transições, mas a repetição de regras idênticas | Apresenta o exemplo da seção 4.1: o inimigo enriquecido com cinco estados de combate, todos precisando da mesma regra "vida < 20% → Fugir" | Identificam, no exemplo, quantas vezes a mesma transição precisaria ser replicada em uma FSM plana |
| 3. Fundamentos: superestado, subestado e configuração ativa | 20 min | Definir com precisão os conceitos elementares da hierarquia | Apresenta a seção 4.2, com apoio no diagrama de dois superestados (Pacífico e Combate); explica configuração ativa como pilha de estados ("Combate → Atirar") | Identificam, para o exemplo do guarda, qual seria a configuração ativa em diferentes momentos |
| 4. Herança de transições e avaliação em cascata | 20 min | Explicar como a avaliação em cascata do nível externo para o interno origina a herança de transições | Apresenta a seção 4.3 e 4.3.1, incluindo o pseudocódigo da avaliação em cascata e o cuidado com ações enter/exit de níveis intermediários (Erro Comum da Apostila) | Discutem em duplas por que a regra do superestado deve ser avaliada antes da regra do subestado |
| 5. Estado de histórico | 15 min | Explicar a memória de configuração e diferenciar histórico raso de profundo | Apresenta a seção 4.3.2, com o exemplo do inimigo interrompido em "Recarregando" que deve retomar de onde parou | Discutem em grupo um caso em que o histórico seria indispensável e outro em que reiniciar pelo estado inicial seria mais correto |
| 6. Demonstração no Unity (sub-state machines) | 10 min | Mostrar a hierarquia materializada em sub-state machines no Animator | Demonstra ao vivo a criação de uma sub-state machine simples no Animator, agrupando dois ou três estados sob um superestado, mapeando aos conceitos da seção 4.7 | Observam a demonstração e relacionam superestado/subestado/transição herdada aos elementos do editor |

---

## Encontro 2 (1h30)

**Foco:** Evolução do Micro Game NPC Decision de FSM para HFSM, reaproveitando a implementação da Semana 2. Discussão técnica comparando as duas abordagens.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando superestado, subestado, herança de transições e histórico | Respondem perguntas de verificação oral |
| 2. Análise da FSM de cada grupo | 15 min | Identificar, na própria FSM da Semana 2, famílias de estados que compartilham transições | Orienta cada grupo a revisar sua FSM e perguntar: "quais estados compartilham as mesmas transições de saída?" (pergunta-chave da seção 4.1) | Analisam a própria implementação e listam candidatos a superestado (por exemplo, estados de combate versus estados pacíficos) |
| 3. Redesenho hierárquico | 15 min | Projetar a nova estrutura em superestados e subestados antes de implementar | Acompanha cada grupo na definição de pelo menos dois superestados, suas transições próprias e quais transições devem ser herdadas | Redesenham, em papel ou diagrama, a HFSM do próprio NPC, definindo estado inicial de cada nível e decidindo onde aplicar histórico |
| 4. Implementação guiada | 35 min | Reestruturar a implementação existente em HFSM | Acompanha os grupos na refatoração (via sub-state machines do Animator ou extensão do padrão *State* em C# para estados que contêm submáquinas), reforçando a ordem correta de enter/exit entre níveis | Reestruturam a FSM da Semana 2 em HFSM, testando as transições herdadas e, quando aplicável, o estado de histórico |
| 5. Testes e ajustes | 5 min | Verificar se o comportamento reestruturado corresponde ao esperado | Circula entre os grupos, testando especificamente a transição herdada e perguntando "essa regra vale para todos os subestados?" | Testam a HFSM implementada e corrigem transições herdadas ausentes ou mal posicionadas |
| 6. Discussão técnica: FSM plana versus HFSM | 5 min | Comparar tecnicamente as duas abordagens a partir da prática | Conduz uma discussão rápida sobre o que melhorou (redundância, manutenibilidade) e o que a HFSM ainda não resolve (acoplamento, rigidez), antecipando a leitura da seção 4.5 | Comparam a quantidade de transições escritas antes e depois da reestruturação |
| 7. Encerramento | 5 min | Fechar a semana e indicar o caminho da próxima | Recapitula a evolução de FSM para HFSM e anuncia que a Semana 4 apresentará Árvores de Comportamento e Blackboard como resposta às limitações discutidas | Registram pendências e dúvidas para o próximo encontro |

---

## Micro Game

**Micro Game em desenvolvimento:** NPC Decision (Módulo 1).

**Objetivo pedagógico:** demonstrar como um NPC decide o que fazer, evoluindo de uma Máquina de Estados Finita simples até uma Árvore de Comportamento com Blackboard ao longo do Módulo 1.

**Estado ao final da Semana 3:** FSM da Semana 2 reestruturada em HFSM, contendo:

- pelo menos dois superestados coerentes (por exemplo, "Pacífico" e "Combate"), cada um agrupando os subestados relacionados definidos na Semana 2;
- ao menos uma transição herdada, ancorada na borda de um superestado e válida para todos os seus subestados;
- estado inicial definido para cada nível da hierarquia;
- decisão explícita, para cada superestado, sobre o uso ou não de estado de histórico;
- ações enter/exit disparadas na ordem correta em transições que cruzam níveis da hierarquia.

**Relação com módulos anteriores:** dá continuidade direta à FSM implementada na Semana 2, reestruturando-a sem alterar seu comportamento observável — o ganho é de organização, não de novo comportamento. Servirá de base para a evolução prevista na Semana 4, quando a hierarquia será substituída por uma Árvore de Comportamento com Blackboard.

---

## Engenharia Reversa

Não há atividade formal de Engenharia Reversa prevista para a Semana 3, conforme o Cronograma — o primeiro momento formal ocorre na Semana 4, junto à apresentação da metodologia de Engenharia Reversa (Capítulo 14 da Apostila).

O professor pode citar rapidamente, a título de contextualização, que a organização hierárquica de comportamento é comum em NPCs de jogos de ação e tiro (seção 4.6 da Apostila), mas sem conduzir exercício estruturado de análise nesta semana — essa prática permanece reservada à Semana 4.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C# (HFSM)** | Reestruturação da FSM do NPC Decision em uma HFSM, estendendo o padrão *State* da Semana 2 para estados que contêm submáquinas internas, conforme o nível de cada grupo |
| **Sub-state machines do Animator** | Demonstração da HFSM materializada visualmente no Encontro 1, para grupos que optarem por essa abordagem na implementação |

A comparação com ferramentas de terceiros (NodeCanvas, Behavior Designer) e com o State Tree da Unreal é apresentada apenas como panorama teórico (seção 4.8 da Apostila), sem uso prático nesta semana — o foco permanece na implementação própria em C#, conforme indicado no Cronograma.

---

## Atividade de Laboratório

**Objetivo:** reestruturar a FSM do Micro Game NPC Decision, implementada na Semana 2, em uma Máquina de Estados Hierárquica.

**Etapas:**

1. Cada grupo revisa sua FSM da Semana 2 e identifica famílias de estados que compartilham as mesmas transições de saída.
2. Definição de pelo menos dois superestados, com seus subestados, estado inicial de cada nível e decisão sobre o uso de estado de histórico.
3. Reestruturação da implementação (sub-state machines do Animator ou extensão do padrão *State* em C#), migrando transições comuns para a borda dos superestados.
4. Teste do comportamento resultante, verificando se a transição herdada dispara corretamente a partir de qualquer subestado do superestado correspondente e se as ações enter/exit ocorrem na ordem correta entre níveis.
5. Reflexão em grupo comparando o número de transições escritas antes e depois da reestruturação.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma HFSM funcional no Micro Game NPC Decision, com pelo menos dois superestados e uma transição herdada, preservando o comportamento observável já validado na Semana 2, porém com estrutura mais organizada e manutenível.

---

## Verificação da Aprendizagem

O Módulo 1 se encerra formalmente apenas na Semana 4, quando ocorrem o Desafio de Escolha Tecnológica, o AI Design Log e a Engenharia Reversa do módulo. A verificação nesta semana é, portanto, **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes definem corretamente superestado, subestado, configuração ativa e herança de transições, e se diferenciam histórico raso de profundo (critério **Compreensão Conceitual** da Rubrica);
- observação da reestruturação guiada no Encontro 2, verificando se a HFSM resultante preserva o comportamento da FSM original e se as transições herdadas e as ações enter/exit entre níveis foram implementadas corretamente (indício de **Aplicação Prática**, formalmente avaliado na consolidação do Micro Game na Semana 4);
- discussão técnica de comparação entre FSM e HFSM, avaliando se os grupos conseguem articular, com argumentos próprios, o que a hierarquia resolve e o que ela ainda não resolve — acoplamento e rigidez (indício de **Tomada de Decisão**);
- observação do uso correto de sub-state machines no Animator, quando aplicável (indício de **Uso da Unity e do Ecossistema**).

Nenhuma nota é atribuída nesta semana, conforme os Critérios de Notas da disciplina, que vinculam a composição da nota aos módulos encerrados nas Semanas 4, 7, 9, 11, 13 e 16, ao checkpoint da Semana 8 e à apresentação final da Semana 17.

---

## Entregas

Não há entrega formal prevista para a Semana 3, conforme o Cronograma.

A HFSM reestruturada do Micro Game NPC Decision permanece com os grupos, para evolução na Semana 4 (transição para Árvore de Comportamento com Blackboard) e consolidação nessa mesma semana, quando passa a compor o Micro Game entregável, o AI Design Log e o Desafio de Escolha Tecnológica do Módulo 1.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Escolher superestados de forma arbitrária, sem que os estados agrupados de fato compartilhem transições comuns | Retomar a pergunta-chave da seção 4.1: "há um conjunto de estados que compartilham as mesmas transições de saída?" — se a resposta for não, reconsiderar o agrupamento |
| Esquecer de disparar ações enter/exit dos níveis intermediários ao transitar entre hierarquias, causando inicializações perdidas | Usar o Erro Comum da seção 4.3.1 como referência direta; orientar o grupo a listar explicitamente a cadeia de exit (de dentro para fora) e de enter (de fora para dentro) antes de codificar |
| Aplicar estado de histórico indiscriminadamente a todos os superestados, produzindo comportamento "grudento" onde reiniciar seria mais correto | Retomar o Atenção da seção 4.3.2: decidir, superestado por superestado, se memória ou reinício é o comportamento correto para aquele caso específico |
| Acreditar que a HFSM elimina de vez os problemas da FSM, sem perceber que acoplamento e rigidez permanecem | Conduzir a discussão técnica de encerramento com perguntas diretas: "o que ainda seria trabalhoso reordenar ou reutilizar nesta HFSM?", preparando o terreno para a Semana 4 |

---

## Preparação para a Próxima Semana

Para a Semana 4 (Árvores de Comportamento, Blackboard e Engenharia Reversa), o professor deve:

- solicitar a leitura prévia do Capítulo 6 da Apostila (Árvores de Comportamento) e do Capítulo 14 (Metodologia de Engenharia Reversa de IA), além de revisar rapidamente o Capítulo 5 (Árvores de Decisão), citado como ponte conceitual;
- garantir que todos os grupos tenham, de fato, uma HFSM funcional implementada no Micro Game NPC Decision ao final da Semana 3;
- revisar rapidamente a HFSM de cada grupo antes do próximo encontro, identificando exemplos concretos de acoplamento ou rigidez para usar como gancho na fundamentação de Árvores de Comportamento;
- providenciar acesso ao pacote **Unity Behavior** nos projetos de cada grupo, já que a Semana 4 realiza a primeira demonstração prática dessa ferramenta;
- selecionar previamente o jogo comercial a ser utilizado no primeiro momento de Engenharia Reversa, garantindo que sua IA de decisão seja suficientemente visível para sustentar a discussão.
