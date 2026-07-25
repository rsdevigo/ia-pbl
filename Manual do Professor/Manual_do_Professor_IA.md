# Manual do Professor

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)
**Documentos de referência:** Apostila da disciplina, Plano de Ensino, Cronograma, Rubrica de Avaliação, Critérios de Notas

---

## Como Utilizar Este Manual

Este Manual não substitui a Apostila, o Plano de Ensino, o Cronograma ou os Planos de Aula. Ele cumpre um papel diferente: orientar a prática docente, explicando *como* conduzir a disciplina, *por que* ela está organizada da forma como está, e *o que fazer* diante das situações mais comuns de sala de aula. Sempre que este documento mencionar um conteúdo específico de módulo, semana ou capítulo, o professor deve consultar o documento de origem correspondente — este Manual apenas explica a lógica de utilização desses documentos, sem reproduzir seu conteúdo.

---

## 1. Apresentação

### 1.1 Objetivo da Disciplina

Inteligência Artificial e Ilusão de Inteligência não é uma disciplina sobre algoritmos, nem sobre ferramentas. É uma disciplina sobre decisão técnica. Seu propósito é formar estudantes capazes de compreender um problema de comportamento de NPC ou de sistema de jogo, reconhecer quais famílias de técnicas de IA poderiam resolvê-lo, e escolher — com justificativa — a mais adequada ao contexto. A implementação correta de cada técnica na Unity é condição necessária, mas não suficiente: o que a disciplina avalia, em última instância, é a capacidade de justificar escolhas.

Essa orientação deve estar presente na postura do professor em todo encontro. Perguntas como "por que você escolheu essa solução, e não outra?" são tão importantes quanto perguntas como "isso está funcionando?".

### 1.2 Perfil Esperado do Estudante ao Final

Ao concluir a disciplina, espera-se que o estudante seja capaz de olhar para um problema de IA em jogos e, antes de abrir a Unity, responder: qual é o problema real, quais técnicas resolvem problemas dessa família, quais são os requisitos e limitações do projeto, e qual solução equilibra melhor esses fatores. Esse estudante deve saber operar as ferramentas oficiais da Unity relacionadas a cada técnica, reconhecer alternativas relevantes do ecossistema, e comunicar suas decisões oralmente e por escrito com o vocabulário técnico apropriado.

O professor deve ter em mente que o critério de sucesso não é "o estudante decorou o funcionamento do Behavior Tree", mas "o estudante sabe quando um Behavior Tree é a escolha certa, e quando não é".

### 1.3 Competências Desenvolvidas

As competências trabalhadas ao longo do semestre — detalhadas no Plano de Ensino — cobrem desenvolvimento de jogos, engenharia de software aplicada a sistemas de decisão, domínio conceitual de IA clássica para jogos, tomada de decisão técnica, resolução estruturada de problemas, trabalho em equipe e documentação técnica. O professor deve observar que essas competências não se desenvolvem em paralelo, mas de forma integrada: um Micro Game malfeito quase sempre revela uma fragilidade conceitual, e um AI Design Log raso quase sempre revela dificuldade de justificar decisões, não apenas de escrever.

### 1.4 Papel da Disciplina no Curso

Dentro do curso Superior de Tecnologia em Jogos Digitais, esta disciplina é o ponto em que o estudante deixa de tratar IA como uma "funcionalidade a mais" do jogo e passa a tratá-la como uma área de decisão de design com trade-offs próprios — de produção, de desempenho e de experiência do jogador. O professor atua como uma referência que combina, ao mesmo tempo, o rigor técnico de um Game AI Engineer, a clareza didática de um professor universitário, a intencionalidade pedagógica de um designer instrucional e o olhar crítico de um revisor técnico. Nenhuma dessas frentes deve prevalecer isoladamente sobre as demais na condução da disciplina.

---

## 2. Filosofia da Disciplina

### 2.1 Ensino Baseado em Problemas

A disciplina é organizada por perguntas, não por algoritmos. Cada módulo começa com uma pergunta de design ("como um NPC decide o que fazer?", "como um agente encontra seu destino?") e só depois apresenta as técnicas que respondem a essa pergunta. O professor deve resistir à tentação de abrir um módulo apresentando uma ferramenta ou uma API — mesmo quando isso pareceria mais rápido ou mais motivador para a turma. Abrir pela ferramenta inverte a lógica da disciplina e reforça memorização em vez de compreensão.

Essa sequência didática — problema, fundamentos, aplicações em jogos, ferramentas, Micro Game — deve ser reconhecível pelo estudante em todos os módulos. Se o estudante conseguir prever essa sequência, isso é um sinal de que a filosofia da disciplina está sendo internalizada, não apenas aplicada pelo professor.

### 2.2 Project-Based Learning

O PBL não é usado aqui como uma atividade avaliativa isolada, mas como o eixo estruturador do semestre inteiro. Isso tem uma consequência prática importante: nenhuma entrega deve ser tratada pelo professor como um evento pontual e encerrado. Uma consolidação de Micro Game na Semana 4 não é "o fim" daquele conteúdo — é uma evidência dentro de um processo contínuo que segue até a Semana 17. O professor deve manter, para cada grupo, uma noção acumulada de trajetória, não apenas uma lista de entregas corrigidas.

### 2.3 O AI Playground e os Micro Games

O AI Playground é o Projeto Integrador único do semestre: um ambiente Unity composto por Micro Games independentes, cada um demonstrando uma família de técnicas de IA. É fundamental que o professor comunique, desde a Semana 1, que o objetivo não é produzir um jogo completo e polido, mas um conjunto de experimentos de IA claros, comparáveis e modificáveis. Grupos que investem tempo excessivo em arte, narrativa ou mecânicas não relacionadas à IA devem ser redirecionados — não porque esses aspectos sejam desimportantes em geral, mas porque desviam o foco pedagógico específico desta disciplina.

### 2.4 Integração entre Teoria e Prática

Cada módulo entrelaça fundamentação teórica, demonstração, implementação guiada e discussão técnica. O professor deve evitar dois extremos igualmente problemáticos: aulas inteiramente expositivas, que produzem compreensão sem prática, e aulas inteiramente práticas, que produzem código funcional sem compreensão. O equilíbrio pretendido está descrito na Estrutura dos Encontros (Capítulo 4).

### 2.5 Tomada de Decisão como Competência Central

Diferente de disciplinas centradas em implementação, esta disciplina trata a tomada de decisão técnica como resultado de aprendizagem em si — não como consequência automática de saber programar. Por isso o Desafio de Escolha Tecnológica existe ao final de cada módulo, e por isso a Rubrica de Avaliação dedica um critério inteiro a esse aspecto. O professor deve tratar a pergunta "por que essa solução, e não outra?" como uma das ferramentas pedagógicas mais importantes de que dispõe, usando-a de forma recorrente — não apenas nos momentos formais de avaliação.

---

## 3. Organização do Semestre

O semestre é organizado em seis módulos de conteúdo, cada um respondendo a uma pergunta central de design de IA, seguidos por uma unidade de encerramento dedicada ao projeto final. A lógica de progressão segue um encadeamento intencional, e não uma sequência arbitrária de técnicas — a ordem dos documentos institucionais (Cronograma, Planos de Aula) deve ser consultada para os detalhes semana a semana; aqui interessa apenas a lógica que os conecta.

### 3.1 Lógica de Progressão dos Módulos

A disciplina caminha da decisão mais simples para a mais sofisticada. O primeiro módulo trata de como um único NPC decide entre estados e ações discretas — o problema de decisão mais elementar. O segundo módulo desloca o foco de "o que fazer" para "como chegar", introduzindo navegação e busca de caminhos. O terceiro módulo recombina os dois anteriores em um problema de escolha tática, no qual o NPC pondera múltiplos fatores simultâneos. O quarto módulo introduz a existência de um adversário com objetivos opostos, deslocando o problema de decisão individual para decisão adversarial. O quinto módulo desloca o papel do designer: em vez de codificar diretamente o comportamento, o estudante aprende a fazer com que boas soluções emerjam automaticamente. O sexto módulo completa essa progressão levando o próprio agente a aprender a partir da experiência, em vez de seguir regras ou heurísticas definidas a priori.

O professor deve tornar essa progressão explícita para a turma, especialmente nas transições entre módulos: cada novo módulo deve ser apresentado também como uma evolução da pergunta anterior, e não apenas como "um novo assunto".

### 3.2 Relação entre os Micro Games

Os seis Micro Games não são unidades isoladas dentro do AI Playground: eles compartilham, sempre que possível, o mesmo agente, o mesmo cenário-base ou os mesmos NPCs, para que o estudante perceba a evolução de um único sistema de IA ao longo do semestre — e não seis miniprojetos desconectados. Quando a arquitetura permitir, o professor deve incentivar os grupos a reaproveitar estruturas de um Micro Game no seguinte (por exemplo, reaproveitar o NPC de decisão do Módulo 1 como agente de navegação no Módulo 2). Esse reaproveitamento reforça, na prática, a ideia de que técnicas de IA se combinam em sistemas maiores, e não que existem isoladamente.

### 3.3 Evolução Esperada do Estudante

Nos primeiros módulos, é esperado — e aceitável — que o estudante ainda dependa fortemente da estrutura fornecida pelo professor para justificar suas escolhas técnicas. À medida que o semestre avança, especialmente a partir dos Desafios de Escolha Tecnológica intermediários, a expectativa é de autonomia crescente: comparações mais completas entre alternativas, reconhecimento espontâneo de limitações, e AI Design Logs cada vez mais consistentes. O critério de Evolução ao Longo do Semestre, previsto na Rubrica, existe justamente para capturar essa trajetória — o professor deve observá-la de forma ativa, e não apenas registrá-la ao final.

---

## 4. Estrutura dos Encontros

Cada semana possui dois encontros de 1h30. Sempre que possível, o primeiro encontro é dedicado a fundamentação, demonstração e implementação guiada, e o segundo, à revisão do que foi desenvolvido, ao avanço do Micro Game, à discussão técnica e ao encerramento. Essa divisão, definida no Cronograma, deve ser entendida pelo professor como uma orientação de peso pedagógico, não como uma grade rígida de minutos.

### 4.1 Apresentação da Teoria

A fundamentação teórica deve ser breve o suficiente para não consumir o encontro inteiro, mas suficiente para que o estudante compreenda o problema antes de ver qualquer ferramenta. Recomenda-se abrir cada encontro teórico retomando a pergunta norteadora do módulo, e só então apresentar o conteúdo do capítulo da Apostila correspondente. Evitar slides longos com definições isoladas; preferir exemplos de jogos reais que tornem o conceito concreto desde o início.

### 4.2 Demonstrações

As demonstrações devem ser feitas ao vivo, na Unity, sempre que o conteúdo permitir. Uma demonstração ao vivo — mesmo com pequenas falhas — tem valor pedagógico maior do que um vídeo gravado, porque expõe o processo de decisão do professor diante de problemas reais (por exemplo, ajustar uma transição de FSM que não dispara como esperado). O professor deve narrar seu próprio raciocínio durante a demonstração, tornando visível não apenas o resultado, mas o processo de diagnóstico.

### 4.3 Atividades Práticas

A implementação guiada do primeiro encontro deve ser suficientemente estruturada para que nenhum grupo termine o encontro sem ter produzido algo funcional, mas suficientemente aberta para permitir pequenas variações entre grupos. O segundo encontro, dedicado ao desenvolvimento do Micro Game, deve ter menor intervenção direta do professor e maior circulação entre os grupos, identificando dificuldades individuais antes que se tornem lacunas conceituais.

### 4.4 Discussões Técnicas

A discussão técnica prevista no segundo encontro de cada semana é um dos momentos mais valiosos da disciplina e não deve ser tratada como tempo residual. É nesse momento que o professor tem oportunidade de comparar soluções entre grupos, antecipar fragilidades antes da consolidação do módulo, e oferecer feedback informal — conforme recomendado na Rubrica de Avaliação. Perguntas dirigidas ("por que seu grupo optou por essa transição, e não por aquela?") rendem mais do que perguntas abertas ("alguma dúvida?").

### 4.5 Encerramento

Cada encontro deve terminar com uma síntese breve — o que foi resolvido, o que ficou pendente, e qual é o próximo passo. Em encontros de consolidação de módulo, o encerramento deve também apontar explicitamente a conexão com o próximo módulo, reforçando a lógica de progressão descrita no Capítulo 3.

### 4.6 Dimensionamento da Turma e dos Grupos

A disciplina é planejada para turmas de **até 40 estudantes**, podendo operar com cerca de 30, organizadas em grupos de **2 a 4** integrantes. Na prática, isso significa **10 a 14 grupos** por turma — número que deve orientar toda decisão de tempo do professor.

Recomenda-se formar grupos de 3 ou 4 estudantes sempre que a turma permitir. Grupos de 2 são aceitáveis em turmas menores, mas aumentam a carga por estudante em um projeto que atravessa seis módulos; grupos de 5 ou mais não são recomendados, porque tornam impraticável a verificação individual da compreensão conceitual prevista no Capítulo 11.

Esse dimensionamento tem uma consequência direta e frequentemente subestimada: **apresentações seriadas para toda a turma não cabem em um encontro de 1h30**. Com 12 grupos, 70 minutos de apresentação dão menos de 6 minutos por grupo, sem espaço para as perguntas técnicas que sustentam a avaliação. Por isso, os dois momentos formais de apresentação da disciplina — o checkpoint da Semana 8 e a apresentação final da Semana 17 — adotam formatos de **rodízio** e de **feira**, nos quais o professor circula entre as bancadas realizando arguições individuais de 4 a 5 minutos enquanto o restante da turma trabalha ou visita as demais estações. Os Planos de Aula das Semanas 8 e 17 detalham cada formato.

O professor que optar por manter apresentações seriadas deve refazer o cálculo de tempo a partir do número real de grupos, e não do plano — e reservar tempo adicional no Cronograma, que hoje não tem folga.

### 4.7 Gestão do Tempo

Como referência geral, recomenda-se reservar cerca de um terço do primeiro encontro para fundamentação teórica, deixando o restante para demonstração e prática guiada; e reservar a maior parte do segundo encontro ao desenvolvimento do Micro Game, com 15 a 20 minutos finais para discussão técnica e encerramento. Em semanas de Desafio de Escolha Tecnológica e Engenharia Reversa (identificadas no Cronograma), o segundo encontro exige tempo adicional para esses dois instrumentos — o professor deve planejar a consolidação do Micro Game de forma que ela não consuma o tempo necessário para ambos.

---

## 5. Papel da Apostila

A Apostila é a fonte da verdade conceitual da disciplina. Todo material produzido — planos de aula, slides, tutoriais — deve estar alinhado a ela, e em caso de conflito entre documentos, ela prevalece, salvo orientação explícita do professor responsável.

### 5.1 Leituras Antes da Aula

Recomenda-se indicar aos estudantes a leitura do capítulo correspondente da Apostila antes do primeiro encontro de cada semana, especialmente nos módulos que tratam de fundamentos mais densos (grafos, Minimax, algoritmos genéticos, aprendizagem por reforço). Essa leitura prévia não deve ser tratada como pré-requisito rígido de participação, mas como facilitador: turmas que chegam com a leitura feita permitem que o primeiro encontro avance mais rápido da fundamentação para a demonstração.

### 5.2 Leituras Após a Aula

Após o encontro de fundamentação, a releitura do capítulo funciona como consolidação, especialmente útil para os estudantes que terão dificuldade de acompanhar a implementação guiada no mesmo ritmo da turma. O professor pode indicar seções específicas do capítulo para revisão dirigida quando perceber lacunas conceituais recorrentes durante a discussão técnica.

### 5.3 Capítulos Obrigatórios e Complementares

Os capítulos que correspondem diretamente à pergunta norteadora de cada semana — indicados no Cronograma — são de leitura obrigatória. Seções marcadas na Apostila como *aprofundamento* mas efetivamente estudadas na disciplina — como a IA de utilidade (seção 6.7), retomada na Semana 9 ao lado dos mapas de influência — devem ser tratadas pelo professor como leitura obrigatória daquela semana, e não como material opcional. A bibliografia básica é complemento, não substituta: o conteúdo está na Apostila. Já os capítulos de síntese e estudos de caso, concentrados principalmente na Semana 17, têm caráter integrador e devem ser posicionados como complementares às leituras semanais, e não como conteúdo novo isolado.

### 5.4 Encerramentos de Parte e Apêndices — o material mais subutilizado da Apostila

A Apostila oferece, além dos capítulos, dois conjuntos de material que o professor deve incorporar deliberadamente à rotina do semestre, porque não aparecem no fluxo de leitura óbvio e por isso tendem a passar em branco.

**Encerramentos de Parte.** Cada Parte (exceto a IV, que tem um único capítulo) encerra com Resumo Geral, Principais Conceitos, **Questões de Revisão**, **Exercícios Conceituais**, **Exercícios de Integração** e, em vários casos, uma **tabela comparativa consolidada** — Representações do Espaço e Algoritmos de Busca na Parte III; Minimax × Alfa-Beta × MCTS na Parte V; Q-Learning × Deep RL × Algoritmos Genéticos na Parte VI; FSM × HFSM × árvore de decisão × BT na Parte II. Esses exercícios são a principal fonte de verificação formativa da disciplina, e as tabelas são o melhor apoio disponível para as discussões técnicas e para os Desafios de Escolha Tecnológica. Os Planos de Aula das semanas de encerramento de módulo já indicam qual Encerramento usar em cada caso; note que o Encerramento de uma Parte só deve ser indicado quando **todos** os seus capítulos já tiverem sido estudados — o que, por causa das inversões de ordem sinalizadas no Cronograma, nem sempre coincide com o fim da Unidade.

**Apêndices.** São quatro, todos de uso prático imediato:

- **Apêndice A — Glossário.** Vale distribuir na Semana 1 e retomar como referência permanente. A disciplina depende fortemente de consistência terminológica, e o Glossário é o árbitro dela.
- **Apêndice B — Guia Rápido de Ferramentas Unity de IA.** A tabela B.1 mapeia conceito → ferramenta oficial → alternativa de terceiros. É o apoio direto ao Capítulo 6 deste Manual.
- **Apêndice C — Tabela-Decisão e Tabelas de Consulta.** A tabela **C.1 — "dado este problema de jogo, qual técnica usar?"** é, literalmente, o instrumento de apoio do Desafio de Escolha Tecnológica; a **C.2** consolida arquiteturas e algoritmos para a comparação de alternativas exigida pelo modelo de entrega; a **C.3** traz a linha do tempo da IA em jogos; e a **C.4** é um **checklist para o professor**, que vale percorrer na preparação de cada módulo.
- **Apêndice D — Referências e Leituras.** A seção D.2 organiza leituras complementares por tema, útil para atender estudantes que pedem aprofundamento sem improvisar indicações.

**Projeto Integrador Final da Apostila.** O Encerramento da Parte VII propõe um projeto culminante — a engenharia reversa de um jogo à escolha do estudante, com roteiro detalhado de seis etapas e entregáveis por etapa. A disciplina **não** o adota como instrumento avaliativo próprio, porque o seu Projeto Integrador é o AI Playground e porque acrescentar um segundo projeto de porte comprometeria o Cronograma. O professor deve, ainda assim, conhecê-lo e usá-lo de duas formas: como fonte de estrutura para o sexto momento de Engenharia Reversa (Semana 16), cujo roteiro pode ser enriquecido com as etapas descritas ali, e como sugestão de aprofundamento voluntário para estudantes com interesse específico no tema.

Quando um mesmo capítulo da Apostila for utilizado em mais de uma semana não consecutiva — como ocorre com o capítulo de heurísticas e algoritmos genéticos —, o professor deve sinalizar isso explicitamente à turma, evitando a impressão de que o capítulo foi "concluído" antes da hora.

---

## 6. Utilização da Unity

A Unity é a ferramenta oficial da disciplina e deve ser utilizada de forma consistente ao longo de todo o semestre, tanto pelo professor quanto pelos grupos.

### 6.0 Ambiente Técnico de Referência

Antes de qualquer decisão pedagógica, o professor deve **fixar e registrar** as versões usadas no semestre. A disciplina não prescreve versões específicas — elas mudam mais rápido do que este Manual —, mas prescreve que sejam **fixadas, registradas e verificadas antes da Semana 1**, porque as Semanas 14 a 16 dependem de uma cadeia versionada e frágil: pacote ML-Agents ↔ ambiente Python ↔ formato `.onnx` ↔ pacote de inferência.

Preencher e manter atualizada a tabela abaixo:

| Item | Versão adotada no semestre | Verificado em |
|---|---|---|
| Unity (Editor) | | |
| AI Navigation (`com.unity.ai.navigation`) | | |
| Unity Behavior (`com.unity.behavior`) | | |
| ML-Agents — pacote Unity (`com.unity.ml-agents`) | | |
| ML-Agents — pacote Python (`mlagents`) | | |
| Python (ambiente de treinamento) | | |
| Sentis / Inference Engine (`com.unity.ai.inference`) | | |

Três observações práticas sobre essa tabela:

- **O pacote de inferência mudou de identificador.** O antigo `com.unity.sentis` foi substituído por **`com.unity.ai.inference`**. O nome de exibição oscilou entre "Sentis" e "Inference Engine" ao longo das versões, o que confunde a busca no Package Manager: **procurar pelo identificador**, não pelo nome. A documentação vive em `docs.unity3d.com/Packages/com.unity.ai.inference@latest`.
- **A documentação web do ML-Agents foi depreciada** em favor da documentação de pacote da Unity. Preferir esta última ao indicar leitura aos estudantes.
- **O par ML-Agents ↔ Python é o ponto frágil.** Fixe as duas versões juntas, teste a instalação completa antes da Semana 14 e mantenha um ambiente de reserva já configurado em pelo menos uma máquina do laboratório. O Plano de Aula da Semana 14 já recomenda antecipar a instalação; esta tabela é o que torna essa recomendação verificável de um semestre para o outro.

Revisar esta tabela a cada oferta da disciplina é a forma mais barata de detectar que o material quebrou — sem ela, não há como saber o que revisar nem quando.

### 6.1 Organização dos Projetos

Recomenda-se que cada grupo trabalhe em um único projeto Unity, estruturado desde a Semana 1 para comportar múltiplas cenas — uma por Micro Game — dentro do mesmo AI Playground. Pastas e nomenclaturas devem refletir os módulos da disciplina, facilitando tanto a navegação pelo professor durante as correções quanto a apresentação final na Semana 17, quando todos os Micro Games precisam ser reunidos e demonstrados em sequência.

### 6.2 Versionamento

O uso de controle de versão (Git) é fortemente recomendado desde o início do projeto, tanto por boas práticas de engenharia de software quanto porque o histórico de commits é evidência concreta de desenvolvimento contínuo — coerente com a filosofia de avaliação baseada em evidências produzidas ao longo do semestre. O professor deve orientar os grupos sobre arquivos que não devem ser versionados (pastas de build, cache do Unity) e sobre a importância de mensagens de commit que expliquem decisões, não apenas ações.

### 6.3 Boas Práticas

O professor deve reforçar práticas básicas de organização de cena e de script — nomenclatura consistente, separação de responsabilidades entre componentes, uso de comentários explicando decisões de IA (não de sintaxe) — sem transformar isso em um curso paralelo de engenharia de software. O critério de Qualidade Técnica da Solução, na Rubrica, avalia justamente esse equilíbrio: organização suficiente para sustentar comparação e extensão, sem exigir arquitetura de produção comercial.

### 6.4 Utilização das Ferramentas Oficiais

O **Apêndice B.1** da Apostila traz a tabela conceito → ferramenta oficial → alternativa de terceiros, e deve ser a primeira consulta do professor ao preparar cada módulo.


Sempre que existir uma solução oficial da Unity para a técnica estudada — AI Navigation, Unity Behavior, Blackboard, ML-Agents, Sentis, Animator —, ela deve ser apresentada e utilizada como referência principal, conforme indicado no Cronograma para cada módulo. Nos módulos em que não existe solução oficial equivalente (como Mapas de Influência, Utility AI, Minimax e Algoritmos Genéticos), isso deve ser comunicado explicitamente à turma como uma característica do problema, e não como uma lacuna da disciplina: parte da formação do Game AI Engineer é saber reconhecer quando é necessário implementar uma solução própria.

### 6.5 GOAP — uma exclusão deliberada

O planejamento orientado a objetivos (GOAP) aparece três vezes no material sem nunca ser estudado: nos slides da Semana 1, como a técnica de *F.E.A.R.*; no quadro comparativo da seção 6.8, usado na Semana 4; e na seção 15.2 da Apostila, como estudo de caso. **Isso é deliberado.** A seção 6.6 é marcada na própria Apostila como conteúdo de *aprofundamento*, e o Cronograma de 17 semanas não comporta um sétimo problema de decisão sem sacrificar profundidade nos seis existentes.

A consequência prática é que o professor deve **nomear a exclusão** em vez de deixá-la implícita. Quando GOAP surgir no quadro da seção 6.8 (Semana 4), vale dizer à turma: existe, é a arquitetura de *F.E.A.R.*, resolve o mesmo problema do Módulo 1 por planejamento em vez de enumeração, e está na seção 6.6 para quem quiser ler. Estudantes que perguntarem devem ser encaminhados à seção 6.6 e à 15.2, e — se quiserem experimentar — aos assets de GOAP do ecossistema Unity (CrashKonijn GOAP, ReGoap), sempre como aprofundamento voluntário, fora do escopo avaliado.

A Semana 17 aproveita essa lacuna a favor da disciplina: *F.E.A.R.* é o caso de contraste ideal do fechamento, justamente por ser o exemplo em que a hipótese intuitiva do observador é refutada pela documentação.

### 6.6 Integração de Ferramentas de Terceiros

Ferramentas do ecossistema (A* Pathfinding Project, Behavior Designer, NodeCanvas, entre outras) devem ser apresentadas de forma comparativa, nunca como substitutas obrigatórias das soluções oficiais. O objetivo pedagógico dessas comparações é sempre o mesmo: mostrar vantagens, limitações, cenários de uso e impacto na produção, para que o estudante desenvolva critério de escolha — e não apenas familiaridade com mais um plugin.

---

## 7. Condução dos Micro Games

### 7.1 Objetivo Pedagógico

Cada Micro Game existe para tornar tangível uma família específica de técnicas de IA, não para produzir um jogo comercialmente viável. O professor deve comunicar esse objetivo desde a apresentação de cada módulo, e retomá-lo sempre que perceber grupos desviando o foco para aspectos não relacionados à IA.

### 7.2 Escopo Esperado

O escopo de cada Micro Game deve ser reduzido o suficiente para ser compreendido, modificado e comparado entre grupos em poucos minutos de demonstração. Um Micro Game bem escopado permite que um colega de outro grupo entenda o comportamento de IA implementado sem precisar de explicação extensa sobre mecânicas de jogo alheias ao conteúdo do módulo.

### 7.3 Evolução

Os Micro Games evoluem de duas formas ao longo do semestre: dentro de um mesmo módulo (por exemplo, do primeiro encontro de implementação guiada até a consolidação no segundo encontro) e entre módulos, quando um Micro Game anterior é reaproveitado como base do seguinte (ver Capítulo 3.2). O professor deve valorizar explicitamente essa segunda forma de evolução, já que ela é o que mais evidencia o critério de Evolução ao Longo do Semestre previsto na Rubrica.

### 7.4 Erros Comuns

Os erros mais frequentes na condução dos Micro Games costumam ser: ampliar o escopo do jogo além do necessário para demonstrar a técnica; implementar a técnica de forma funcional, mas sem compreender por que ela funciona (frequentemente perceptível quando o grupo não consegue explicar uma decisão de parâmetro); e negligenciar a documentação do processo, deixando o AI Design Log para ser escrito apenas no momento da entrega, sem relação com as decisões realmente tomadas durante o desenvolvimento. O professor deve estar atento a esses sinais durante o segundo encontro de cada semana, e não apenas no momento da consolidação.

### 7.5 Incentivo à Experimentação

Modificações e variações devem ser incentivadas sempre que não desviarem do foco pedagógico do módulo — por exemplo, testar diferentes funções heurísticas em A*, ou diferentes pesos em um Mapa de Influência, comparando os resultados. Esse tipo de experimentação é o que diferencia um desempenho "Proficiente" de um "Excelente" no critério de Aplicação Prática da Rubrica, e deve ser sugerido pelo professor mesmo quando o grupo não o propõe espontaneamente.

---

## 8. Engenharia Reversa

### 8.1 Papel na Disciplina

A Engenharia Reversa não é um bloco isolado ao final do semestre: ela ocorre ao final de cada módulo de conteúdo, sempre associada ao Desafio de Escolha Tecnológica correspondente, e é retomada de forma integrada na Semana 17. Seu papel é relacionar teoria e prática por meio da análise de jogos comerciais, exercitando a mesma capacidade de análise técnica que a disciplina busca desenvolver — só que aplicada a sistemas dos quais o estudante não tem acesso ao código-fonte.

### 8.2 Estratégias para Discutir Jogos Comerciais em Sala

O professor deve selecionar, para cada momento de Engenharia Reversa, um jogo (ou trecho de jogo, via vídeo ou sessão de jogo em sala) cujo comportamento de IA seja claramente observável e relacionado à técnica do módulo em questão. É mais produtivo conduzir a análise com perguntas dirigidas — "o que este NPC parece considerar antes de agir?", "esse comportamento parece guiado por estados discretos ou por uma pontuação contínua?" — do que pedir uma análise aberta, que tende a gerar respostas superficiais.

### 8.3 Análise Crítica das Soluções

O objetivo não é adivinhar com certeza a arquitetura real utilizada pelo estúdio, mas formular hipóteses plausíveis, fundamentadas nos conceitos estudados, e reconhecer os limites dessas hipóteses diante da falta de acesso ao código. O professor deve valorizar respostas que reconheçam múltiplas arquiteturas possíveis para o mesmo comportamento observado, tanto quanto respostas que cheguem a uma hipótese específica bem justificada — essa é, inclusive, a lógica avaliada pelo critério de Tomada de Decisão aplicado à Engenharia Reversa, conforme descrito na Rubrica.

---

## 9. Avaliação

### 9.1 Como Utilizar a Rubrica

A Rubrica de Avaliação é o instrumento único de avaliação da disciplina, aplicado de forma recorrente a cada módulo, e não apenas ao final do semestre. O papel do professor é utilizá-la como ferramenta formativa: ao observar o desempenho de um grupo em cada critério, o feedback mais útil não é apenas "qual nível foi atingido", mas "o que seria necessário para alcançar o nível seguinte". Essa orientação deve ser comunicada ao estudante de forma explícita, idealmente logo após cada consolidação de módulo, e não apenas no fechamento do semestre.

A conversão dos níveis qualitativos da Rubrica em valores numéricos, os pesos de cada instrumento dentro do módulo e o cálculo da nota final do semestre estão definidos nos Critérios de Notas — o professor deve aplicar esse documento em conjunto com a Rubrica, sem redefinir pesos ou fórmulas por conta própria.

### 9.2 Feedback Contínuo

O momento mais natural para o feedback contínuo é a discussão técnica do segundo encontro de cada semana (ver Capítulo 4.4). Antecipar fragilidades nesse momento — antes da consolidação formal do módulo — reduz surpresas negativas na avaliação e reforça o caráter formativo da disciplina. Recomenda-se também estimular a autoavaliação dos grupos a partir dos próprios descritores da Rubrica, especialmente antes de apresentações técnicas e entregas do AI Design Log.

### 9.3 Acompanhamento do Projeto

Como a avaliação acompanha um único Projeto Integrador ao longo de 17 semanas, o professor deve manter algum registro contínuo do progresso de cada grupo — mesmo que informal — permitindo comparar o desempenho observado em um módulo com o de módulos anteriores. Esse registro é o que sustenta, na prática, a aplicação do critério de Evolução ao Longo do Semestre.

### 9.4 AI Design Log

O AI Design Log deve ser tratado como parte inseparável da solução técnica, não como um anexo burocrático. O professor deve orientar os grupos a escrevê-lo ao longo do desenvolvimento do Micro Game — registrando decisões no momento em que são tomadas —, e não apenas no fechamento do módulo, quando o raciocínio original já foi parcialmente esquecido. Um bom indicador de qualidade do AI Design Log é a presença de alternativas efetivamente consideradas e descartadas, não apenas a descrição da solução final.

### 9.5 Apresentações

O checkpoint intermediário da Semana 8 e a apresentação final da Semana 17 devem ser conduzidos como momentos formais de comunicação técnica, nos quais o estudante explica e defende suas decisões diante de perguntas — do professor e, quando possível, da própria turma. O professor deve preparar perguntas específicas para cada grupo com antecedência, a partir do acompanhamento contínuo do projeto, evitando que a apresentação se resuma a uma demonstração sem defesa técnica.

Ambos adotam formato de arguição individualizada, pelas razões de dimensionamento explicadas no Capítulo 4.6: **rodízio durante o laboratório** na Semana 8 e **feira em estações** na Semana 17, com 4 a 5 minutos por grupo em cada caso. Esse tempo é suficiente para a defesa, mas não para produzir sozinho evidência dos oito critérios da Rubrica na apresentação final — daí a importância do registro contínuo tratado em 9.3, que é o que sustenta os critérios de Aplicação Prática, Uso da Unity, Qualidade Técnica e Evolução na nota do encerramento.

### 9.6 Desafio de Escolha Tecnológica

O Desafio de Escolha Tecnológica, presente ao final de cada módulo, é o instrumento mais diretamente ligado ao critério de Tomada de Decisão. O **Apêndice C.1** da Apostila — a tabela-decisão "dado este problema de jogo, qual técnica usar?" — e o **Apêndice C.2** são o andaime natural deste instrumento: entregá-los aos grupos não entrega a resposta, mas dá o vocabulário de comparação que o descritor "Proficiente" do critério pressupõe. O professor deve garantir que o problema proposto em cada desafio realmente admita mais de uma solução técnica plausível — caso contrário, o exercício de justificativa perde sentido. A correção deve valorizar a qualidade da comparação entre alternativas tanto quanto a solução final escolhida.

---

## 10. Recuperação

A recuperação da disciplina não se baseia em prova escrita isolada, e o professor deve conduzi-la em coerência com a metodologia PBL adotada durante todo o semestre.

### 10.1 Evolução do Projeto

Sempre que possível, a recuperação deve ocorrer por meio da evolução efetiva do Projeto Integrador — incorporando ao AI Playground a técnica de IA que não foi consolidada no módulo correspondente —, e não por meio de um instrumento avaliativo desconectado do projeto.

### 10.2 Revisão dos Conceitos

Antes de qualquer nova implementação, o professor deve revisar com o estudante os conceitos fundamentais em que houve maior fragilidade, priorizando os critérios de Compreensão Conceitual e Tomada de Decisão — que, segundo a Rubrica de Avaliação (seção 7), orientam prioritariamente o processo de recuperação. A conversão em nota e a substituição da nota do módulo seguem os Critérios de Notas (item 8).

### 10.3 Melhoria das Implementações e da Documentação

A recuperação deve exigir tanto a melhoria da implementação do Micro Game quanto a revisão do respectivo AI Design Log, corrigindo lacunas relacionadas a justificativa técnica, alternativas consideradas ou reflexão crítica. Ambas as frentes devem ser reavaliadas com a mesma Rubrica aplicada durante o semestre, permitindo comparação direta entre o desempenho anterior e o desempenho após a recuperação — em coerência com o critério de Evolução ao Longo do Semestre.

---

## 11. Dificuldades Frequentes

| Dificuldade | Estratégia de Intervenção |
|---|---|
| **Dificuldade em abstração** — o estudante entende o exemplo apresentado em aula, mas não consegue generalizá-lo para um problema diferente. | Apresentar, sempre que possível, mais de um exemplo de jogo para a mesma técnica, e pedir explicitamente ao estudante que identifique o que os dois exemplos têm em comum antes de avançar para a implementação. |
| **Dificuldade em decompor problemas** — o estudante tenta resolver o Micro Game "de uma vez", sem separar o problema em partes menores. | Durante a implementação guiada, tornar visível o processo de decomposição do professor, resolvendo o problema em etapas explícitas e nomeadas, em vez de apresentar a solução já pronta. |
| **Foco excessivo em programação** — o estudante trata a disciplina como um exercício de código, sem relacionar as decisões de implementação a conceitos de IA. | Retomar, durante a discussão técnica, perguntas conceituais antes de perguntas de implementação ("por que esse comportamento representa a técnica estudada?", antes de "como você programou isso?"). |
| **Dificuldade em justificar escolhas técnicas** — o estudante escolhe uma solução, mas não consegue explicar por que ela é melhor que as alternativas. | Exigir, nos Desafios de Escolha Tecnológica, a comparação explícita de ao menos duas alternativas antes de qualquer conclusão, seguindo o próprio descritor da Rubrica para o nível Proficiente. |
| **Dificuldade em relacionar teoria e prática** — o estudante entende a teoria isoladamente, mas não a reconhece quando observa um jogo comercial. | Utilizar os momentos de Engenharia Reversa de forma mais frequente e informal, para além dos momentos formais previstos no Cronograma, sempre que um jogo relevante surgir espontaneamente em discussão. |
| **Dependência excessiva de tutoriais externos** — o estudante busca replicar soluções prontas encontradas online sem compreender o motivo das escolhas feitas por terceiros. | Perguntar explicitamente ao estudante, diante de uma solução copiada, se ela atende aos requisitos específicos do Micro Game em questão — frequentemente a resposta revela que a cópia não foi adaptada ao problema real. |
| **Desequilíbrio entre grupos** — integrantes de um mesmo grupo com níveis de conhecimento técnico muito diferentes, gerando concentração de trabalho em uma única pessoa. | Distribuir responsabilidades de forma explícita dentro do grupo (implementação, documentação, apresentação), alternando essas responsabilidades entre módulos, e verificar individualmente a compreensão conceitual durante a discussão técnica. |

---

## 12. Recomendações Pedagógicas

### 12.1 Estimular Participação

Perguntas dirigidas a grupos específicos, a partir do que já foi observado em seu Micro Game, tendem a gerar mais participação do que perguntas abertas à turma inteira. Retomar, no início de cada encontro, um ponto observado no encontro anterior também ajuda a manter a sensação de continuidade do projeto.

### 12.2 Incentivar Experimentação

Sugerir variações concretas — um parâmetro diferente, uma heurística alternativa, uma condição de transição adicional — costuma ser mais eficaz do que apenas convidar o estudante a "experimentar". A experimentação orientada, especialmente nos módulos sem solução oficial da Unity, ajuda a consolidar a compreensão dos fundamentos antes de qualquer generalização.

### 12.3 Conduzir Discussões

Discussões técnicas produtivas partem de comparação entre soluções — entre grupos diferentes, ou entre a solução implementada e uma alternativa não escolhida —, e não de perguntas genéricas sobre o conteúdo teórico. O professor deve preparar, para cada discussão técnica, ao menos uma pergunta comparativa específica ao contexto da turma.

### 12.4 Equilibrar Teoria e Prática

O tempo dedicado à teoria deve ser proporcional à complexidade conceitual do módulo, não fixo entre semanas. Módulos com fundamentos mais densos (como busca adversarial ou aprendizagem por reforço) podem exigir mais tempo de fundamentação no primeiro encontro, compensado por menor tempo de exploração livre no segundo.

### 12.5 Integrar Diferentes Níveis de Conhecimento da Turma

Em turmas com estudantes de níveis técnicos distintos, formar grupos heterogêneos costuma favorecer o compartilhamento de conhecimento, desde que o professor garanta — por meio da discussão técnica e da distribuição de responsabilidades sugerida no Capítulo 11 — que a compreensão conceitual seja verificada individualmente, e não apenas no nível do grupo.

---

## 13. Recursos Complementares

### 13.1 Documentação Oficial (Uso Obrigatório, conforme o módulo)

A documentação oficial da Unity referente a cada ferramenta apresentada no Cronograma — AI Navigation, Animator Controller, Unity Behavior, ML-Agents — deve ser indicada como leitura de apoio sempre que a ferramenta correspondente for utilizada em um módulo. O professor deve utilizar essa documentação como referência para as próprias demonstrações, garantindo que a terminologia empregada em aula seja consistente com a terminologia oficial.

### 13.2 Unity Learn (Complementar)

As trilhas oficiais do Unity Learn relacionadas a IA, navegação e ML-Agents são um recurso complementar valioso para estudantes que desejam aprofundar o uso técnico de uma ferramenta específica, mas não substituem a fundamentação teórica apresentada em aula, conforme a bibliografia básica indicada no Plano de Ensino.

### 13.3 Vídeos e Demonstrações Técnicas (Complementar)

Vídeos de análise de IA em jogos comerciais são um recurso útil para preparar os momentos de Engenharia Reversa, especialmente quando o jogo em questão não está disponível para sessão ao vivo em sala. Devem ser selecionados previamente pelo professor, garantindo que o comportamento de IA relevante seja claramente visível.

### 13.4 Apêndices da Apostila (Uso Recorrente)

Glossário (A), guia de ferramentas Unity (B), tabela-decisão e tabelas de consulta (C, incluindo o checklist do professor em C.4) e leituras por tema (D). Ver o Capítulo 5.4 deste Manual para o uso recomendado de cada um ao longo do semestre.

### 13.5 Livros (Bibliografia Básica e Complementar)

A bibliografia básica e complementar da disciplina, detalhada no Plano de Ensino, está disponível para consulta na pasta de referências do projeto. Os títulos de bibliografia básica devem ser tratados como leitura de apoio obrigatória para o professor na preparação de cada módulo; os de bibliografia complementar são indicados aos estudantes com maior interesse em aprofundamento teórico ou matemático.

### 13.6 Artigos Científicos (Complementar)

Artigos científicos e materiais fornecidos pelo professor ao longo do semestre devem ser utilizados de forma pontual, principalmente para embasar comparações entre abordagens divergentes de diferentes autores — situação que deve ser apresentada à turma de forma explícita, e não simplificada como se houvesse uma única resposta correta.

### 13.7 Documentação de Outras Engines (Comparação, Complementar)

A documentação de sistemas equivalentes em outras engines, como a Unreal Engine (State Tree, Behavior Tree, Environment Query System, Learning Agents), é um recurso complementar útil para fins comparativos, especialmente nos Desafios de Escolha Tecnológica, mas não deve deslocar o foco da disciplina, que permanece centrado na Unity como ferramenta oficial.

### 13.8 Ferramentas de Terceiros do Ecossistema Unity (Comparação, conforme o módulo)

Ferramentas como A* Pathfinding Project, Behavior Designer e NodeCanvas devem ser apresentadas nos módulos em que há uma solução oficial correspondente da Unity, sempre em caráter comparativo, conforme indicado no Capítulo 6.5.

### 13.9 Projetos Open Source (Complementar)

Projetos open source que implementem técnicas estudadas na disciplina podem ser indicados como leitura de código complementar, especialmente para estudantes que desejem observar implementações mais robustas do que as desenvolvidas em sala — sem substituir a implementação própria exigida nos Micro Games.

---

## 14. Considerações Finais

Este Manual reflete o estado atual da disciplina e das ferramentas que ela utiliza. Como a Unity e seu ecossistema de IA evoluem continuamente — novas versões de pacotes oficiais, mudanças em ML-Agents e Sentis, novos plugins relevantes de terceiros —, alguns aspectos deste documento exigem revisão periódica, especialmente:

- a lista de ferramentas oficiais indicadas para cada técnica, caso a Unity descontinue, substitua ou renomeie pacotes;
- as ferramentas de terceiros apresentadas como comparação, caso deixem de ser mantidas ou surjam alternativas mais relevantes;
- os exemplos de jogos comerciais utilizados na Engenharia Reversa, para manter relevância junto às turmas;
- a bibliografia complementar, à medida que novas edições ou novas obras de referência se tornem disponíveis.

A revisão desses aspectos deve ser feita preservando a filosofia central da disciplina — partir sempre do problema antes da ferramenta — mesmo quando as ferramentas específicas mudarem. É essa filosofia, mais do que qualquer ferramenta em particular, que garante a validade da disciplina ao longo dos próximos semestres.

---

*Este Manual do Professor é consistente com a Apostila, o Plano de Ensino, o Cronograma, a Rubrica de Avaliação e os Critérios de Notas da disciplina Inteligência Artificial e Ilusão de Inteligência, e deve ser utilizado como guia de prática docente por qualquer professor responsável por ministrá-la.*
