# Revisão da Semana 8 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_08.md` e `Slides/Semana 8/slides.md` (+ `semana_8_slides.pptx`/`.pdf` e `assets/mermaid-1.png`)
**Referência de verdade:** Apostila — Parte II, Capítulo 5 (Árvores de Decisão), completo; Parte IV, Capítulo 10 (Mapas de Influência), seção 10.1 e início da 10.2; Encerramento da Parte II (Tabela Comparativa Consolidada); CLAUDE.md — seção "Micro Games — Exemplos de Implementação" (Módulo 3: Seleção de Alvo)
**Observação:** não há Tutorial dedicado para a Semana 8 no repositório. Como nas semanas anteriores, isso é coerente com o estágio atual do projeto — a implementação prática é conduzida pela "Atividade de Laboratório" do próprio Plano — e não configura lacuna de documento.

---

## Resumo Geral

A Semana 8 abre a Unidade III com um conteúdo bem dimensionado — o Capítulo 5 completo (árvore de decisão, capítulo de apoio e propositalmente enxuto) somado apenas à introdução do Capítulo 10 (seção 10.1 e início da 10.2), sem antecipar aprofundamento — e soma a isso o checkpoint técnico intermediário do Encontro 2, cuja logística de rodízio está corretamente ancorada no dimensionamento de turma do Manual do Professor (§4.6) e no peso de 10% dos Critérios de Notas. O Plano segue a sequência da Apostila com fidelidade (5.1 → 5.2 → 5.2.1 → 5.3.1 → 5.5 → 10.1 → início de 10.2), fecha os dois encontros exatamente em 90 minutos cada, e os Slides reproduzem a maior parte do conteúdo com boa correspondência de vocabulário e de quadros de Atenção/Erro Comum.

Dois problemas de fundo, no entanto, pesam mais do que os de forma. O primeiro é uma inconsistência interna entre o próprio Plano e os Slides: a etapa 3 do Encontro 1 descreve explicitamente "o diagrama do NPC (patrulhar/fugir/atacar/atirar)" — a árvore de quatro folhas e três testes (visão, vida, distância) que é o exemplo canônico da seção 5.2 da Apostila —, mas o diagrama efetivamente produzido (`mermaid-1.png`) tem apenas duas perguntas (visão, distância) e três folhas, sem o teste de vida e sem a folha "Fugir". O segundo, mais estrutural, é que o Micro Game Tactical AI apresentado nesta semana e continuado na Semana 9 implementa uma árvore de decisão de **seleção de ação** de um único NPC — não a **seleção de alvo entre múltiplos alvos** (jogador, aliados, por distância/vida/ameaça) que o CLAUDE.md do projeto fixa como o exemplo obrigatório do Módulo 3. Como o próprio projeto declara que "todo material de demonstração... deve utilizar exatamente estes exemplos", esse é um desvio de escopo que atravessa as Semanas 8 e 9, não apenas um detalhe de redação.

Os demais problemas — ausência de slide para a seção 5.3.2 (nota sobre árvores aprendidas/ID3), listada nos Conteúdos do Plano mas sem etapa dedicada nem slide correspondente — são de prioridade mais baixa e não comprometem a estrutura geral, que é sólida.

---

## Pontos Fortes

- **Sequência fiel à Apostila, sem saltos.** O problema da escolha instantânea de ação (5.1) → nós, ramos, folhas (5.2) → distinção árvore de decisão × árvore de comportamento (5.2.1) → ordenação de testes e limitações (5.3.1, 5.5) → transição para "onde ir?" (10.1, início de 10.2) é seguida na mesma ordem no Plano e nos Slides.
- **Nenhuma antecipação do restante do Capítulo 10.** Tanto o Plano quanto os Slides tratam fonte/propagação/decaimento apenas como introdução, remetendo explicitamente combinação de camadas e atualização em tempo real para a Semana 9 — coerente com a determinação textual do próprio Plano ("Não deve ser antecipado o restante do Capítulo 10...").
- **Distinção essencial (5.2.1) bem construída.** O quadro comparativo dos Slides, o quadro de Atenção/Erro Comum sobre tratar as duas árvores como sinônimos, e a retomada dos conceitos de estados de retorno e nós de controle de fluxo do Módulo 1 aparecem de forma consistente no Plano (etapa 4) e nos Slides.
- **Boa Prática de ordenação de testes (5.3.1) corretamente incorporada.** O slide "Ordenação de testes" reproduz com precisão o critério de "testes baratos e decisivos perto da raiz" e o efeito sobre custo (não sobre resultado), tal como a Apostila.
- **Nenhum uso de ferramenta fora da filosofia da disciplina.** O Plano e os Slides são explícitos ao afirmar que a Unity não tem ferramenta dedicada a árvore de decisão, situando corretamente C#/Visual Scripting como implementação e os nós de condição do Unity Behavior como reaparição do conceito no Capítulo 6 — fiel à seção 5.7.
- **Logística do checkpoint bem fundamentada.** O formato de rodízio (4 a 5 min por grupo), o número de 10 a 14 grupos e o cálculo de "56 dos 60 minutos" batem exatamente com o dimensionamento de turma do Manual do Professor (§4.6) e com a Ficha 5 dos Formulários de Avaliação (Comunicação Técnica + Evolução ao Longo do Semestre, 10% da nota final) — não há números inventados ou divergentes entre os documentos.
- **Bloco de especificação de figura corrigido.** Ao contrário do defeito identificado em `Revisao_Critica_da_Disciplina.md` (blocos `[!FIGURA]` renderizados literalmente em PDFs/PPTX de outras semanas), o slide "O que implementar hoje" usa comentário HTML (`<!-- FIGURA A PRODUZIR ... -->`), que o Marp de fato omite: a verificação do PDF (`semana_8_slides.pdf`, 22 páginas) não encontrou nenhuma ocorrência de "FIGURA", "Krita" ou "apresentador" — a nota de produção não vaza para o material do aluno.
- **Diagrama de apoio sem conteúdo inventado.** `mermaid-1.png` é o único asset da semana, referenciado exatamente uma vez, e a segunda figura mencionada nos Slides (árvore de decisão do NPC tático) é corretamente deixada como "FIGURA A PRODUZIR", sem inventar uma imagem inexistente — coerente com a instrução do projeto.
- **Encerramento e ponte para a Semana 9 bem alinhados.** Tanto o Plano quanto os Slides anunciam corretamente as quatro entregas da Semana 9 (Micro Game 50%, AI Design Log 25%, Desafio 15%, Engenharia Reversa 10%) e o aprofundamento de mapas de influência e Utility AI, sem antecipar conteúdo do Módulo 4.

---

## Problemas Encontrados

### Problema 1
- **Documento:** Slides (`assets/mermaid-1.png`) e Plano de Aula (`Plano_de_Aula_Semana_08.md`, Encontro 1, etapa 3)
- **Local:** Slide "Nós, ramos e folhas"
- **Descrição:** O Plano descreve textualmente a etapa 3 do Encontro 1 como a apresentação do "diagrama do NPC (patrulhar/fugir/atacar/atirar)" — o mesmo exemplo da seção 5.2 da Apostila, que tem três nós de decisão (visão do inimigo, vida > 30%, distância < 2 m) e quatro folhas (Patrulhar, Fugir, Atacar corpo a corpo, Atirar). O diagrama efetivamente produzido em `mermaid-1.png` tem apenas dois nós de decisão ("Vê o jogador?", "Distância curta?") e três folhas (Patrulhar, Atacar corpo a corpo, Atirar) — sem qualquer teste de vida e sem a folha "Fugir". Isso não é apenas uma simplificação editorial: a "Preparação do Professor" do próprio Plano lista "visão do jogador, distância, nível de vida" como as três condições de exemplo da semana (repetidas também nas "Funcionalidades esperadas" do Micro Game e nas "Dificuldades Esperadas"), e a Apostila dedica o teste de vida especificamente ao exemplo de "Fugir" — a única folha que ilustra o teste `vida > 30%?`. Sem essa folha, a árvore mostrada na etapa mais importante da fundamentação (a que "demonstra a descida da raiz até a folha") deixa de exemplificar uma das três condições que a própria semana promete ensinar, e simplifica a estrutura de referência da Apostila sem que o Plano ou os Slides sinalizem a simplificação.
- **Prioridade:** Alta

### Problema 2
- **Documento:** Plano de Aula (`Plano_de_Aula_Semana_08.md`, seção Micro Game) e Slides (`slides.md`, seção "Micro Game Tactical AI")
- **Local:** Escopo do Micro Game 3 — Tactical AI
- **Descrição:** O CLAUDE.md do projeto, na seção "Micro Games — Exemplos de Implementação", fixa o exemplo obrigatório do Módulo 3 como "Tactical AI: Seleção de Alvo — Um NPC escolhe entre múltiplos alvos (jogador, aliados) conforme distância, vida e ameaça", e determina que "todo material de demonstração (planos de aula, slides, tutoriais) deve utilizar exatamente estes exemplos, mantendo consistência entre os documentos". O Micro Game efetivamente descrito na Semana 8 (e continuado, sem alteração de escopo, na Semana 9) não é uma seleção de alvo entre múltiplos candidatos: é uma árvore de decisão de **seleção de ação** para um único NPC, com folhas do tipo "patrulhar/fugir/atacar/atirar" — mais próxima, conceitualmente, de uma decisão de comportamento do que de uma escolha de alvo. Não há, em nenhuma etapa do Plano ou em nenhum slide, menção a múltiplos alvos candidatos (jogador e aliados) nem a uma pontuação por distância/vida/ameaça que os compare entre si — o critério de "ameaça" citado no CLAUDE.md sequer aparece no vocabulário da semana. Como esse desvio de escopo já está presente na concepção do Micro Game (não é um detalhe pontual de um slide) e se propaga também à Semana 9 — onde a mesma árvore é apenas estendida com mapa de influência e Utility AI, ainda sem seleção de alvo —, ele compromete a rastreabilidade entre o "Fonte da Verdade" do projeto e o material efetivamente produzido para o Módulo 3 inteiro.
- **Prioridade:** Alta

### Problema 3
- **Documento:** Plano de Aula (`Plano_de_Aula_Semana_08.md`, seção Conteúdos e Encontro 1) e Slides (`slides.md`)
- **Local:** Seção 5.3.2 da Apostila (árvores de decisão aprendidas / ID3-entropia)
- **Descrição:** A seção "Conteúdos" do Plano lista explicitamente a "nota de contexto sobre árvores de decisão aprendidas (ID3/entropia), apenas para situar a diferença entre a árvore autoral (usada em jogos) e a árvore induzida por dados — seção 5.3.2" como conteúdo previsto da semana. No entanto, nenhuma etapa da tabela do Encontro 1 aloca tempo a esse conteúdo (a etapa 5 cobre apenas 5.3.1 e 5.5), e os Slides não têm nenhum slide correspondente a essa distinção. O conteúdo é breve na própria Apostila (um parágrafo de contexto e um quadro de Atenção), então a ausência não compromete os Objetivos de Aprendizagem da semana — nenhum deles menciona ID3 ou aprendizado de máquina —, mas há uma promessa não cumprida entre a lista de Conteúdos e o que é efetivamente ensinado.
- **Prioridade:** Baixa

### Problema 4
- **Documento:** Slides (`slides.md`)
- **Local:** Slide "Árvore de decisão × árvore de comportamento"
- **Descrição:** O quadro comparativo da Apostila (seção 5.2.1) tem seis linhas ("Nós internos representam", "Folhas representam", "O que a avaliação produz", "Noção de tempo/duração", "Estados de retorno dos nós", "Objetivo típico"). O slide reproduz apenas quatro dessas seis dimensões (Propósito, Estados de retorno, Noção de tempo, Reutilização/composição) e substitui "Nós internos representam"/"Folhas representam" por uma linha genérica "Propósito", perdendo a comparação explícita entre "testes/condições" e "controle de fluxo" nos nós internos, e entre "ação escolhida" e "tarefas executáveis" nas folhas — justamente os dois pares que mais ajudam o estudante a associar a *forma* da árvore ao seu *conteúdo*. Não é um erro, mas é uma simplificação que reduz o poder didático do quadro mais importante da subseção mais importante do capítulo, sem compensação em outro slide.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Substituir `mermaid-1.png` pelo diagrama completo da seção 5.2 da Apostila (três nós de decisão, quatro folhas, incluindo "vida > 30%?" e "Fugir"), alinhando o slide ao texto da etapa 3 do próprio Plano e às três condições de exemplo (visão, vida, distância) usadas no restante do documento.
- Decidir, antes de prosseguir para a Semana 9 (onde o mesmo Micro Game é apenas estendido), se o escopo do Tactical AI será corrigido para "Seleção de Alvo" conforme o CLAUDE.md, ou se o CLAUDE.md será atualizado para refletir a decisão de produção efetivamente adotada (seleção de ação). Qualquer que seja a direção, a Semana 8 é o ponto de menor custo de correção, por ser onde o Micro Game é iniciado.
- Adicionar um slide breve (ou uma frase em um slide existente) cobrindo a nota de contexto da seção 5.3.2, ou remover a referência a 5.3.2 da lista de Conteúdos do Plano, para que a lista de conteúdos prometidos corresponda ao que é de fato apresentado.
- Se houver espaço, restaurar no quadro comparativo dos Slides as linhas "o que os nós internos representam" e "o que as folhas representam", que são as que mais diretamente sustentam o Objetivo de Aprendizagem 3 ("distinguir com clareza a árvore de decisão da árvore de comportamento").

---

## Parecer Final

**Classificação:** Necessita revisão moderada.

**Justificativa:** A estrutura geral da semana é sólida — sequência fiel à Apostila, tempos batendo exatamente com os 90 minutos de cada encontro, logística do checkpoint corretamente ancorada no Manual do Professor e nos Critérios de Notas, e o defeito de renderização de figuras identificado em outras semanas já não se repete aqui. O que impede uma classificação de "pronta com pequenos ajustes" são dois problemas que não são de forma, mas de conteúdo: o diagrama central da etapa mais importante do Encontro 1 não corresponde ao que o próprio Plano diz que ele mostra (Problema 1), e o Micro Game da semana — que se estende, sem alteração de escopo, até o encerramento do Módulo 3 na Semana 9 — não corresponde ao exemplo fixado como fonte de verdade do projeto para este módulo (Problema 2). Nenhum dos dois exige reescrever o Plano ou os Slides do zero, mas ambos exigem uma decisão editorial explícita antes de a Semana 9 dar continuidade ao mesmo Micro Game.
