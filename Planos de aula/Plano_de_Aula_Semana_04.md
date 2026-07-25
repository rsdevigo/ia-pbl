# Plano de Aula — Semana 4

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 4 de 17 |
| **Unidade** | Unidade I — Fundamentos e Decisão de NPCs (Semanas 1–4) |
| **Módulo** | Módulo 1 — Como um NPC decide o que fazer? |
| **Tema** | Árvores de Comportamento, Blackboard e Engenharia Reversa |
| **Pergunta Norteadora** | Como tornar a decisão do NPC modular e escalável? |
| **Tipo de semana** | 🔴 Encerramento de módulo (Desafio de Escolha Tecnológica + Engenharia Reversa) |

---

## Objetivos de Aprendizagem

Ao final da Semana 4, o estudante deverá ser capaz de:

1. **Explicar** o problema consolidado que a Árvore de Comportamento resolve — o acoplamento e a rigidez de reordenação herdados de FSM/HFSM, e a ausência de tempo, sequência e reutilização herdada da árvore de decisão.
2. **Diferenciar** com precisão os três nós compostos (sequência, seletor, paralelo), explicando como cada um reage aos estados de retorno de seus filhos.
3. **Explicar** a função de decoradores (inversor, repetidor, cooldown, entre outros) e de nós de folha (ações e condições) na composição de uma árvore de comportamento.
4. **Descrever** o papel do Blackboard como memória compartilhada que preserva o desacoplamento entre nós, e reconhecer o risco de tratá-lo sem disciplina.
5. **Explicar** o mecanismo de *tick* e o significado dos três estados de retorno (sucesso, falha, em execução), justificando por que o estado "em execução" confere à BT uma noção de duração ausente na árvore de decisão.
6. **Reestruturar**, em grupo, a HFSM implementada na Semana 3 em uma Árvore de Comportamento com Blackboard, utilizando o pacote Unity Behavior.
7. **Aplicar** o roteiro de seis etapas da metodologia de Engenharia Reversa de IA (definição do problema, coleta de evidências, registro, formulação de hipóteses, validação e documentação) a um jogo comercial com IA de decisão visível.
8. **Justificar** tecnicamente, por escrito e oralmente, a escolha de uma solução de IA para um cenário de decisão de NPC, comparando ao menos duas alternativas no Desafio de Escolha Tecnológica do Módulo 1.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte II, Capítulo 6 da Apostila — Árvores de Comportamento (Behavior Trees)** e à **Parte VII, Capítulo 14 — Metodologia de Engenharia Reversa de IA**:

- o problema resolvido pela árvore de comportamento: acoplamento e rigidez de reordenação (herdados de FSM/HFSM) e ausência de tempo, sequência e reutilização (herdados da árvore de decisão) — seção 6.1;
- fundamentos: nós compostos — sequência, seletor e paralelo (seção 6.2.1); decoradores e nós de folha, ação e condição (seção 6.2.2); Blackboard como memória compartilhada (seção 6.2.3);
- funcionamento: o mecanismo de *tick*, os três estados de retorno (sucesso, falha, em execução) e a reatividade via reavaliação e decoradores de interrupção (seção 6.3);
- exemplo do inimigo guarda reexpresso como árvore de comportamento, com comparação às versões FSM (Cap. 3) e HFSM (Cap. 4) do mesmo agente (seção 6.4);
- vantagens e limitações da árvore de comportamento (seção 6.5);
- ferramentas: o pacote oficial **Unity Behavior**, com comparação pontual a **NodeCanvas** e **Behavior Designer** (seção 6.10);
- metodologia de Engenharia Reversa de IA: por que os estúdios raramente publicam os detalhes de sua IA (seção 14.1); observação sistemática, estímulo e resposta, e sinais de identificação de técnicas (seção 14.2); o roteiro de seis etapas — definição do problema, coleta de evidências, registro das observações, formulação de hipóteses, validação e documentação (seção 14.3); ética e limites da engenharia reversa comportamental, com os rótulos [Documentado], [Inferência] e [Especulação] (seção 14.4).

Não devem ser antecipados os aprofundamentos de GOAP (seção 6.6) e IA de Utilidade (seção 6.7). Os dois casos são diferentes e o professor deve deixar isso claro à turma: a **IA de Utilidade será estudada na Semana 9**, ao lado dos mapas de influência, com os quais compartilha a lógica de combinação ponderada; já o **GOAP não é estudado nesta disciplina** — é exclusão deliberada, justificada no Capítulo 6.5 do Manual do Professor, e permanece disponível na seção 6.6 como leitura de aprofundamento voluntário. Ambos aparecem nesta semana apenas no panorama comparativo do quadro da seção 6.8. Também não deve ser antecipado o Capítulo 15 (estudos de caso comentados) além do caso pontual utilizado no primeiro momento de Engenharia Reversa desta semana.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte II, Capítulo 6, seções 6.1 a 6.5, 6.8, 6.10 e 6.11 (essencial); Parte VII, Capítulo 14, completo; **Apêndice A (Glossário)** para consulta do vocabulário de BT e Blackboard. *Observação:* o **Encerramento da Parte II** ainda não deve ser indicado — a Parte só se completa na Semana 8, com o Capítulo 5 |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com a HFSM da Semana 3 implementada; pacote **Unity Behavior** instalado nos projetos; acesso a vídeo ou build do jogo escolhido para Engenharia Reversa |
| **Cena Unity utilizada** | A mesma cena de demonstração das Semanas 2 e 3 (NPC provisório e ponto de referência do jogador), reaproveitada para a migração de HFSM para Árvore de Comportamento |
| **Assets** | Nenhum asset de arte adicional; segue-se com o modelo provisório do NPC já utilizado nas semanas anteriores |
| **Exemplos** | Árvore de comportamento completa do inimigo guarda, com seletor-raiz de prioridades (Sobreviver, Combater, Investigar, Patrulhar), conforme seção 6.4 da Apostila; quadro comparativo FSM × HFSM × árvore de decisão × BT × GOAP × utilidade (seção 6.8) |
| **Vídeos** | Recomenda-se selecionar previamente trechos de vídeo (gameplay ou captura própria) do jogo escolhido para o primeiro momento de Engenharia Reversa, mostrando o comportamento de decisão do NPC de forma clara e repetível |
| **Jogos para Engenharia Reversa** | **Halo 2** (Bungie, 2004) é a sugestão da Apostila como caso didático padrão de árvore de comportamento documentada (seção 6.9 e Cap. 14); o professor pode substituir por outro jogo com IA de decisão visível, desde que a análise permaneça estritamente comportamental (seção 14.4) |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação de Árvores de Comportamento e Blackboard. Demonstração no Unity Behavior, com comparação pontual a soluções de terceiros. Apresentação formal da metodologia de Engenharia Reversa, que passa a ser reutilizada nos módulos seguintes.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 3 min | Reconectar com o limite identificado na Semana 3 | Retoma a discussão de encerramento da Semana 3: a HFSM organiza estados, mas não elimina acoplamento nem rigidez de reordenação | Relembram os exemplos concretos de acoplamento/rigidez levantados na própria HFSM |
| 2. O problema consolidado | 10 min | Apresentar o diagnóstico único que motiva a BT | Apresenta a seção 6.1: os dois problemas herdados de FSM/HFSM (acoplamento, rigidez) e os dois herdados da árvore de decisão (ausência de tempo/sequência, fraca reutilização); expõe a inversão conceitual — o fluxo mora na estrutura da árvore, não em transições | Relacionam cada problema a uma dificuldade concreta já sentida nas Semanas 2 e 3 |
| 3. Nós compostos | 15 min | Diferenciar sequência, seletor e paralelo | Apresenta a seção 6.2.1 com o diagrama dos três nós compostos e exemplos ("ir até a porta → abrir → atravessar"; "atirar à distância ? corpo a corpo ? fugir") | Classificam, em duplas, pequenos exemplos de comportamento como sequência, seletor ou paralelo |
| 4. Decoradores, folhas e Blackboard | 15 min | Explicar o papel de decoradores, ações/condições e da memória compartilhada | Apresenta a seção 6.2.2 (inversor, repetidor, cooldown) e a seção 6.2.3, com o diagrama de leitura/escrita no Blackboard; alerta sobre o risco do "Blackboard lata de lixo" | Identificam quais chaves de Blackboard seriam necessárias para o NPC guarda (posição do jogador, munição, alerta) |
| 5. Funcionamento: tick e estados de retorno | 10 min | Explicar o mecanismo de tick e a noção de duração | Apresenta a seção 6.3, o pseudocódigo de sequência e seletor, e a diferença entre sucesso, falha e em execução | Discutem por que o estado "em execução" permite à sequência "lembrar" onde parou, sem estado persistente ao estilo FSM |
| 6. Demonstração no Unity Behavior, exemplo completo e vantagens/limitações | 14 min | Mostrar a BT materializada em ferramenta oficial; apresentar a árvore completa do guarda em comparação a FSM/HFSM; fechar com vantagens e limitações da BT | Demonstra ao vivo a criação de uma árvore simples no Unity Behavior (seletor com dois ou três filhos e uma condição), mapeando aos conceitos vistos; cita rapidamente NodeCanvas e Behavior Designer como alternativas de terceiros (seção 6.10); em seguida, apresenta de forma sintética a árvore completa do guarda com suas quatro subárvores de prioridade (Sobreviver, Combater, Investigar, Patrulhar — exemplo da Apostila, seção 6.4, distinto dos superestados do Micro Game da turma), comparando-a às versões FSM (Cap. 3) e HFSM (Cap. 4) do mesmo agente; fecha com o quadro de vantagens (modularidade, legibilidade, autoria visual, reatividade, escalabilidade) e limitações (natureza prescritiva, decisão booleana/ordinal, não generalização) da seção 6.5 | Observam a demonstração e relacionam nós compostos, decoradores e Blackboard aos elementos do editor; comparam mentalmente o exemplo do guarda às versões FSM/HFSM já estudadas; identificam ao menos uma vantagem e uma limitação da BT |
| 7. Metodologia de Engenharia Reversa | 20 min | Apresentar formalmente o roteiro de seis etapas, reutilizado nos módulos seguintes | Apresenta as seções 14.1 a 14.3: por que a IA de jogos raramente é documentada; observação sistemática (controle, repetição, isolamento de variáveis, registro); os sinais de identificação por família de técnica; o roteiro de seis etapas (definição do problema, coleta, registro, hipóteses, validação, documentação); introduz os rótulos [Documentado], [Inferência] e [Especulação] | Registram o roteiro de seis etapas como referência permanente; relacionam os sinais de FSM/HFSM/BT apresentados aos conceitos já estudados no módulo |
| 8. Fechamento | 3 min | Preparar a ponte para o Encontro 2 | Anuncia que o Encontro 2 consolidará a BT no Micro Game, aplicará o Desafio de Escolha Tecnológica e realizará o primeiro momento formal de Engenharia Reversa | Anotam dúvidas e organizam-se em grupo para o encontro seguinte |

---

## Encontro 2 (1h30)

**Foco:** Consolidação do Micro Game NPC Decision com BT + Blackboard. Desafio de Escolha Tecnológica do Módulo 1. Primeiro momento de Engenharia Reversa, aplicando a metodologia a um jogo comercial com IA de decisão visível.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 5 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando nós compostos, decoradores, Blackboard e estados de retorno | Respondem perguntas de verificação oral |
| 2. Análise da HFSM de cada grupo | 15 min | Mapear a HFSM da Semana 3 para uma estrutura de árvore | Orienta cada grupo a identificar, na própria HFSM, quais superestados viram subárvores e qual ordem de prioridade cada um deve ter no seletor-raiz | Redesenham, em papel ou diagrama, a árvore de comportamento correspondente à HFSM já implementada |
| 3. Implementação guiada no Unity Behavior | 30 min | Construir a árvore e o Blackboard no Micro Game | Acompanha os grupos na criação da árvore no Unity Behavior (seletor-raiz, sequências, condições, ao menos um decorador) e na definição das chaves do Blackboard | Implementam a BT do NPC Decision, migrando o comportamento da HFSM sem alterar o resultado observável |
| 4. Testes e ajustes | 10 min | Verificar se a BT reproduz o comportamento esperado | Circula entre os grupos, testando a reavaliação de prioridades (por exemplo, interrompendo uma subárvore de menor prioridade ao simular uma ameaça) | Testam a árvore implementada e corrigem prioridades ou chaves de Blackboard mal configuradas |
| 5. Desafio de Escolha Tecnológica do Módulo 1 | 15 min | Desenvolver a capacidade de justificar tecnicamente uma escolha de solução | Apresenta um cenário de decisão de NPC não idêntico ao Micro Game (por exemplo, um NPC de suporte que deve alternar entre curar, seguir e revidar) e solicita que cada grupo compare ao menos duas soluções possíveis (FSM/HFSM/BT) e justifique a escolhida | Analisam o cenário, comparam alternativas com base em requisitos e limitações, e registram a justificativa por escrito |
| 6. Primeiro momento de Engenharia Reversa | 12 min | Aplicar o roteiro de seis etapas a um caso real | Apresenta trechos de vídeo do jogo escolhido (por exemplo, *Halo 2*), conduz a definição do problema e a observação orientada, e discute hipóteses de identificação de técnica com a turma, reforçando os rótulos [Documentado]/[Inferência]/[Especulação] | Aplicam as etapas 1 a 4 do roteiro (definição do problema, coleta, registro e hipóteses) ao comportamento observado, registrando evidências e hipóteses com nível de confiança |
| 7. Encerramento do Módulo 1 | 3 min | Fechar o módulo e indicar o caminho da próxima semana | Recapitula a evolução de FSM a BT ao longo do módulo, confirma as entregas da semana e anuncia que a Semana 5 abre a Unidade II com navegação | Registram pendências das quatro entregas do módulo para finalização até o prazo definido pelo professor |

---

## Micro Game

**Micro Game em desenvolvimento:** NPC Decision (Módulo 1) — **consolidação final**.

**Objetivo pedagógico:** demonstrar como um NPC decide o que fazer, evoluindo de uma Máquina de Estados Finita simples (Semana 2) até uma Árvore de Comportamento com Blackboard (Semana 4), consolidando o Módulo 1 do AI Playground.

**Estado ao final da Semana 4:** HFSM da Semana 3 migrada para uma Árvore de Comportamento no Unity Behavior, contendo:

- um seletor-raiz de prioridades, com subárvores correspondentes aos dois superestados definidos na Semana 3 ("Pacífico" e "Combate"), cada um subdividido internamente conforme os subestados já implementados;
- ao menos um nó de sequência, um seletor interno e um decorador aplicado de forma justificada;
- um Blackboard documentado, com as chaves utilizadas e os nós que as leem e escrevem;
- comportamento observável equivalente ao da HFSM da Semana 3, com prioridade explícita na ordem dos filhos do seletor-raiz.

**Relação com módulos anteriores:** encerra a trajetória iniciada na Semana 2 (FSM) e continuada na Semana 3 (HFSM), demonstrando a mesma decisão de NPC sob três arquiteturas progressivamente mais modulares. É esta versão — a Árvore de Comportamento — que compõe o Micro Game entregável do Módulo 1, avaliado nesta semana conforme os Critérios de Notas da disciplina.

---

## Engenharia Reversa

**Primeiro momento formal de Engenharia Reversa da disciplina**, conforme o Cronograma e a metodologia apresentada na seção 14.3 da Apostila.

**Jogo analisado:** *Halo 2* (Bungie, 2004), sugerido pela Apostila como caso didático de árvore de comportamento com fonte documentada (palestra de Damian Isla, GDC 2005). O professor pode substituir por outro jogo com IA de decisão visível, mantendo a análise estritamente comportamental.

**Comportamento observado:** decisão de combate dos inimigos — alternância entre avançar, buscar cobertura, recuar e coordenar-se com outros NPCs diante de mudanças de ameaça.

**Perguntas para discussão:**

- Quantos "modos" distintos de comportamento é possível identificar por observação, e o que dispara cada transição?
- As decisões parecem seguir uma ordem de prioridade fixa e visível (sinal de seletor de prioridades) ou uma lógica mais graduada?
- O NPC retoma naturalmente uma atividade interrompida por uma ameaça maior, ou reinicia do zero? O que esse sinal indica sobre reatividade e Blackboard?
- Que evidências sustentam a hipótese de árvore de comportamento, e com que nível de confiança? O que é [Documentado] pela palestra de Isla e o que permanece [Inferência]?

**Relação com os conceitos da semana:** aplica diretamente as etapas 1 a 4 do roteiro de seis etapas (definição do problema, coleta de evidências, registro das observações, formulação de hipóteses) e os sinais de identificação de árvore de comportamento apresentados na seção 14.2.3, exercitando o vocabulário de nós compostos, decoradores e Blackboard construído no Encontro 1. As etapas 5 (validação) e 6 (documentação) podem ser concluídas pelos grupos como parte da entrega, conforme orientação do professor.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Unity Behavior** (oficial) | Construção da Árvore de Comportamento e do Blackboard do Micro Game NPC Decision, migrando a HFSM da Semana 3 |
| **NodeCanvas / Behavior Designer** (terceiros) | Apresentados apenas como panorama comparativo (seção 6.10 da Apostila), sem uso prático nesta semana |

A comparação entre Unity Behavior e as soluções de terceiros deve discutir, conforme a filosofia da disciplina, vantagens, limitações, cenários de uso e impacto na produção — sem se aprofundar na operação de nenhuma ferramenta de terceiros nesta semana.

---

## Atividade de Laboratório

**Objetivo:** migrar a HFSM do Micro Game NPC Decision, implementada na Semana 3, para uma Árvore de Comportamento com Blackboard no Unity Behavior.

**Etapas:**

1. Cada grupo mapeia seus superestados da Semana 3 para subárvores, definindo a ordem de prioridade no seletor-raiz.
2. Construção da árvore no Unity Behavior: nós de sequência e seletor para cada subárvore, condições correspondentes às antigas transições, e ao menos um decorador aplicado com justificativa.
3. Definição e documentação das chaves do Blackboard, identificando quais nós leem e quais escrevem cada chave.
4. Teste do comportamento resultante, verificando se a árvore reproduz o comportamento observável da HFSM e se a reavaliação de prioridades interrompe corretamente subárvores de menor prioridade.
5. Reflexão em grupo comparando a facilidade de reordenar prioridades e reutilizar subárvores na BT frente à HFSM da semana anterior.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma Árvore de Comportamento funcional no Micro Game NPC Decision, com Blackboard documentado, prioridade explícita na ordem dos filhos do seletor-raiz e comportamento observável equivalente ao validado nas semanas anteriores — encerrando o Módulo 1 do AI Playground.

---

## Verificação da Aprendizagem

Ao contrário das Semanas 2 e 3, esta semana **encerra formalmente o Módulo 1**, e a verificação da aprendizagem passa a gerar nota, conforme os Critérios de Notas da disciplina. O professor deve aplicar a Rubrica de Avaliação aos quatro instrumentos previstos:

- **Micro Game (consolidação)** — avaliado principalmente por Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução, observando se a BT com Blackboard reproduz corretamente o comportamento esperado e se a arquitetura está bem organizada (peso 50% do módulo);
- **AI Design Log** — avaliado pelo critério de AI Design Log, verificando se o documento registra problema, alternativas consideradas ao longo do módulo, solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras (peso 25% do módulo);
- **Desafio de Escolha Tecnológica** — avaliado principalmente por Tomada de Decisão, apoiado por Compreensão Conceitual, verificando se o grupo comparou alternativas viáveis e justificou tecnicamente a escolha para o cenário proposto no Encontro 2 (peso 15% do módulo);
- **Engenharia Reversa** — avaliado por Compreensão Conceitual e Tomada de Decisão, verificando a qualidade das hipóteses formuladas sobre o comportamento de *Halo 2* e o uso correto dos rótulos [Documentado]/[Inferência]/[Especulação] (peso 10% do módulo).

A nota do Módulo 1 compõe 11,67% da nota final do semestre, conforme os Critérios de Notas. O professor deve registrar e comunicar aos estudantes a nota obtida em cada instrumento e a nota consolidada do módulo, conforme recomendado pela Rubrica.


**Instrumentos de verificação disponíveis na Apostila.** Antes de recorrer a questões próprias, o professor deve usar o material já pronto e alinhado: os **Exercícios de fixação** ao final do Capítulo 6, e — nas semanas de encerramento de Parte — as **Questões de Revisão**, os **Exercícios Conceituais** e os **Exercícios de Integração** do Encerramento correspondente. Recomenda-se aplicar duas ou três questões na abertura do Encontro 2, como verificação rápida antes do laboratório, e usar o quadro comparativo da seção 6.8 como apoio à discussão técnica. Esse material é a principal fonte de verificação formativa da disciplina, e não deve ficar sem uso.

---

## Entregas

Conforme o Cronograma e a matriz dos Critérios de Notas (item 4), esta semana encerra o Módulo 1 com **quatro** entregas avaliadas:

- **Micro Game 1 — NPC Decision consolidado (50%)** — versão em Árvore de Comportamento com Blackboard, funcional e demonstrável, avaliada pelos critérios de Compreensão Conceitual, Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução;
- **AI Design Log — Micro Game 1 (25%)** — documento contendo problema, requisitos, alternativas consideradas (FSM, HFSM, BT), solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras, conforme o modelo dos Modelos de Entrega do Aluno (§1);
- **Desafio de Escolha Tecnológica — Módulo 1 (15%)** — justificativa escrita comparando ao menos duas alternativas para o cenário de decisão de NPC apresentado no Encontro 2;
- **1º momento de Engenharia Reversa (10%)** — registro das etapas 1 a 4 (e, se orientado pelo professor, 5 e 6) do roteiro aplicado a *Halo 2* (ou ao jogo escolhido).

O Micro Game NPC Decision permanece no AI Playground de cada grupo como base para os módulos seguintes, mas a versão consolidada nesta semana é **entrega formal avaliada**, e não apenas um artefato de trabalho.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir sequência e seletor, invertendo a semântica de "todos precisam ter sucesso" e "um precisa ter sucesso" | Retomar o pseudocódigo da seção 6.3 e pedir que o grupo verbalize, para cada nó de sua árvore, "isto é um E ou um OU?" antes de implementar |
| Tratar o Blackboard como repositório indisciplinado, com chaves redundantes ou mal nomeadas | Exigir, antes da implementação, uma lista documentada de chaves com nome, tipo e quais nós leem/escrevem cada uma, conforme o Atenção da seção 6.2.3 |
| No Desafio de Escolha Tecnológica, escolher uma solução sem comparar alternativas de fato, apenas descrevendo a escolhida | Retomar o critério Tomada de Decisão da Rubrica e exigir explicitamente, no documento, ao menos duas alternativas com vantagens e limitações contrastadas |
| Na Engenharia Reversa, apresentar hipótese como certeza absoluta, sem distinguir observação de inferência | Reforçar os rótulos [Documentado]/[Inferência]/[Especulação] da seção 14.4 e pedir que cada afirmação do grupo seja etiquetada explicitamente |
| Superestimar a complexidade do mecanismo observado em *Halo 2*, atribuindo a coordenação de esquadrão a um sistema mais sofisticado do que o observável sustenta | Retomar o Erro Comum da seção 14.2.3 sobre comportamento emergente e a navalha de Occam: preferir a hipótese mais simples que explique a evidência |

---

## Preparação para a Próxima Semana

Para a Semana 5 (Grafos e Representação do Espaço — abertura da Unidade II), o professor deve:

- solicitar a leitura prévia do Capítulo 7 da Apostila (Grafos e Representação do Espaço);
- garantir que as quatro entregas do Módulo 1 (Micro Game consolidado, AI Design Log, Desafio de Escolha Tecnológica, Engenharia Reversa) estejam recebidas e avaliadas antes do início da Semana 5, registrando a nota do módulo conforme a matriz dos Critérios de Notas (item 4);
- confirmar que todos os grupos possuem, ao final da Semana 4, uma Árvore de Comportamento funcional no Micro Game NPC Decision, encerrando o Módulo 1 do AI Playground;
- providenciar acesso ao pacote **AI Navigation** nos projetos de cada grupo, já que a Semana 5 inicia a configuração da NavMesh no Micro Game Navigation;
- anunciar a transição de unidade: da pergunta "como um NPC decide o que fazer?" para "como um agente encontra seu destino?", situando a navegação como um novo problema, não uma continuação do Módulo 1.
