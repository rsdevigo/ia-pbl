# Revisão da Semana 7 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_07.md` e `Slides/Semana 7/slides.md` (+ `semana_7_slides.pptx`/`.pdf` e `assets/mermaid-1.png`, `assets/mermaid-2.png`)
**Referência de verdade:** Apostila — Parte III, Capítulo 9 (JPS+ e Otimizações), seções 9.1 a 9.7; Encerramento da Parte III; Parte VII, Capítulo 14, seção 14.3 (roteiro de seis etapas)
**Observação:** não há Tutorial dedicado para a Semana 7 no repositório. Como nas semanas anteriores, isso é coerente com o estágio atual do projeto — a implementação prática é conduzida pela "Atividade de Laboratório" do próprio Plano — e não configura lacuna de documento.

---

## Resumo Geral

A Semana 7 encerra o Módulo 2 com um conteúdo teórico denso (Capítulo 9 completo — simetria de caminhos, JPS, JPS+, comparação de desempenho e panorama de outras otimizações) somado a quatro entregas avaliadas no Encontro 2 (Micro Game consolidado, AI Design Log, Desafio de Escolha Tecnológica e 2º momento de Engenharia Reversa). O Plano de Aula é preciso e bem ancorado à Apostila: segue a sequência 9.1 → 9.2 → 9.2.1 → 9.2.2 → 9.3 → 9.4 exatamente na ordem do capítulo, não antecipa a Unidade III, não exige implementação própria de JPS/JPS+ (coerente com a Apostila e com a filosofia da disciplina) e fecha os dois encontros exatamente em 90 minutos cada. Os pesos das quatro entregas somam 100% do módulo e o percentual de 11,67% do módulo na nota final confere com os Critérios de Notas.

O problema central desta revisão está nos Slides, não no Plano. O conceito mais sutil e mais importante do capítulo — a distinção entre vizinho natural, vizinho podado e vizinho forçado, e a definição de jump point que dela decorre (Objetivo de Aprendizagem 2) — é o único conceito da semana que recebe um diagrama dedicado na Apostila, e o diagrama produzido nos Slides (`mermaid-1.png`) não reproduz essa distinção: mostra apenas uma cadeia linear "Origem → Salto → Jump Point → vizinho forçado → Destino", sem vizinho natural, sem vizinho podado, sem comparação entre terreno aberto e terreno com obstáculo. Como esse é o ponto de maior dificuldade conceitual do capítulo (a Apostila dedica a ele um "quadro de Atenção" e a Dificuldade Esperada 2 do próprio Plano alerta para o risco de confusão), a lacuna tem prioridade Alta. Os demais problemas — ausência do diagrama comparativo de nós expandidos (seção 9.3), painel de "outras otimizações" sem nenhum texto de apoio, e ausência do diagrama de suavização de caminho — são de prioridade Média a Baixa e não comprometem a estrutura geral, que é sólida.

---

## Pontos Fortes

- **Sequência fiel à Apostila, sem saltos.** O problema da simetria de caminhos (9.1) → vizinhos naturais/podados/forçados e o procedimento de pulo (9.2, 9.2.1) → JPS+ e tabela de saltos (9.2.2) → comparação de desempenho (9.3) → panorama de outras otimizações (9.4) é seguida na mesma ordem no Plano e nos Slides.
- **Nenhuma antecipação da Unidade III.** Tanto o Plano quanto os Slides encerram apontando para a Semana 8 como checkpoint, sem antecipar Decision Trees, Influence Maps ou Utility AI — coerente com a determinação explícita do próprio Plano.
- **Nenhuma implementação de JPS/JPS+ fora de escopo.** O Plano é explícito ao afirmar que o tratamento é "conceitual e comparativo, não uma nova implementação", coerente com a Apostila (seção 9.7, que trata JPS como ausente nativamente na Unity) e com o princípio geral da disciplina de não implementar todos os algoritmos do zero.
- **Uso correto e fiel do quadro de Atenção central do capítulo.** Tanto o Plano (etapa 4 do Encontro 1) quanto os Slides (`<div class="tip">` após o diagrama de jump point, e o slide "Erro comum") reproduzem com precisão a mensagem mais importante da seção 9.2.1: JPS é o mesmo A*, com a mesma `f = g + h` e a mesma otimalidade — mudando apenas a geração de sucessores.
- **Boa Prática e Erro Comum de 9.2.2 e 9.3 corretamente incorporados.** O slide "Os três custos do pré-processamento" reproduz o Erro Comum sobre mundos dinâmicos, e o slide "Comparação de desempenho" reproduz a Boa Prática "medir antes de otimizar" — ambos citados literalmente e no contexto correto da Apostila.
- **Coerência entre Plano e Slides no fechamento do módulo.** Consolidação do Micro Game, Desafio de Escolha Tecnológica (cenário de mapa grande/aberto/estático) e Engenharia Reversa (StarCraft II, com o mesmo comportamento observado e o mesmo aviso sobre rótulos de confiança) aparecem de forma consistente nos dois documentos.
- **Escopo do Micro Game bem controlado.** Por ser uma semana de consolidação, nenhuma mecânica nova é exigida — apenas revisão, explicação conceitual e justificativa técnica — o que é apropriado para o encerramento de módulo e evita sobrecarregar a semana mais pesada em conteúdo teórico do semestre.
- **Referências ao Apêndice C corretas.** A citação ao Apêndice C.1 (tabela-decisão) e C.2 (tabela consolidada) na "Preparação do Professor" corresponde exatamente ao conteúdo desses apêndices na Apostila.

---

## Problemas Encontrados

### Problema 1
- **Documento:** Slides (`assets/mermaid-1.png`)
- **Local:** Slide "Jump point: nó com vizinho forçado"
- **Descrição:** A especificação de diagrama da Apostila (seção 9.2.1) pede dois painéis: um em terreno aberto, mostrando o único vizinho **natural** (verde) e os demais vizinhos **podados** (cinza, riscados, com a legenda de que são alcançáveis por caminho canônico que não passa ali); outro com um obstáculo, mostrando como ele libera um vizinho **forçado** (laranja) e rotulando o nó como "JUMP POINT (tem vizinho forçado)" — além de uma ilustração do "pulo" atravessando células intermediárias sem expandi-las. O diagrama produzido (`mermaid-1.png`) mostra apenas uma cadeia linear de quatro caixas — "Origem → Salto → Jump Point → (vizinho forçado) → Destino" — sem qualquer distinção entre vizinho natural e podado, sem cores, sem o contraste terreno aberto/terreno com obstáculo, e sem mostrar de onde vem o vizinho forçado. Como este é exatamente o conceito que a Apostila trata como mais sutil do capítulo (dedica-lhe um quadro de Atenção específico) e que sustenta o Objetivo de Aprendizagem 2 ("definir com precisão vizinho natural, podado e forçado"), a simplificação do diagrama deixa a etapa 3 do Encontro 1 (20 min, "vizinhos naturais, podados e forçados") sem o apoio visual que a própria Apostila considera necessário para fixar a distinção.
- **Prioridade:** Alta

### Problema 2
- **Documento:** Slides (`slides.md`)
- **Local:** Ausência de slide/diagrama correspondente à seção 9.3 da Apostila
- **Descrição:** A Apostila (seção 9.3) especifica um diagrama ("Nós expandidos — A* versus JPS numa grade aberta") com duas grades lado a lado, mesma origem e destino: à esquerda, um leque denso de células "expandidas" pelo A*; à direita, apenas alguns jump points com os "pulos" retos entre eles, e uma barra comparativa "A*: N nós" contra "JPS: n ≪ N nós". Esse é o diagrama que evidencia visualmente **por que** o JPS é mais rápido — o argumento central da seção. Nos Slides, a seção 9.3 é representada apenas pela tabela "Comparação de desempenho" (tipo de mapa × ganho do JPS+), sem nenhuma representação visual da diferença no número de nós expandidos. O Objetivo de Aprendizagem 3 ("descrever o JPS como o mesmo A* com geração de sucessores podada") fica sem o reforço visual que haveria com esse diagrama.
- **Prioridade:** Média

### Problema 3
- **Documento:** Slides (`slides.md` e `assets/mermaid-2.png`)
- **Local:** Slide "Panorama de outras otimizações"
- **Descrição:** O diagrama `mermaid-2.png` mostra apenas três caixas — "Pathfinding hierárquico", "Flow fields - multidões" e "Suavização de caminho" — ligadas a um nó "Escala e desempenho", sem nenhum texto explicando o que cada técnica faz, que problema resolve ou a que custo. A Apostila (seção 9.4) dedica um parágrafo a cada uma das três técnicas, incluindo a analogia da viagem entre cidades para o pathfinding hierárquico e a explicação de por que flow fields economizam ao calcular o caminho "uma vez por destino, não por agente". No Plano, essa seção corresponde à etapa 7 do Encontro 1 (apenas 5 min, "reservando aprofundamento para o Encontro 2" — que, no entanto, não retoma esse conteúdo especificamente). Com um diagrama sem texto e apenas 5 minutos previstos, a compreensão de três técnicas distintas — necessária para o Objetivo de Aprendizagem 6 ("comparar A*, JPS/JPS+, pathfinding hierárquico, flow fields e suavização, identificando o problema específico que cada uma ataca") — depende quase inteiramente da exposição oral do professor, sem material de apoio equivalente ao dado aos demais tópicos da semana.
- **Prioridade:** Média

### Problema 4
- **Documento:** Slides (`slides.md`)
- **Local:** Ausência de slide/diagrama correspondente à suavização de caminho (seção 9.4)
- **Descrição:** A Apostila especifica um diagrama próprio para a suavização de caminho ("Suavização de caminho por linha de visão"), mostrando o caminho bruto "escadinha" versus o caminho suavizado, com testes de linha de visão (✓/✗) contornando um obstáculo. A suavização está listada nos Conteúdos do Plano e é mencionada na tabela do slide "Ferramentas" (linha "Suavização nativa de caminho → NavMesh Agent"), mas não há nenhum diagrama ou explicação de **como** o algoritmo de string pulling/funnel funciona — apenas a menção de que ele existe. A Apostila chama esse pós-processamento de "central para a ilusão de inteligência" (Parte I), o que sugere um peso conceitual maior do que o tratamento atual, puramente factual, sugere.
- **Prioridade:** Baixa

### Problema 5
- **Documento:** Slides (`slides.md`)
- **Local:** Slide "Objetivos da aula"
- **Descrição:** O slide lista 5 objetivos, cobrindo apenas os Objetivos de Aprendizagem 1 a 5 do Plano (simetria, vizinhos, JPS, JPS+, quando é apropriado). Os Objetivos 6 a 9 do Plano — comparar as demais otimizações, consolidar o Micro Game, o Desafio de Escolha Tecnológica e a Engenharia Reversa — não aparecem na abertura da aula, embora ocupem a maior parte do Encontro 2. Isso é consistente com a prática de a semana concentrar os "objetivos de conhecimento" no slide inicial e tratar as atividades do Encontro 2 apenas na hora, mas deixa esses quatro compromissos da semana sem menção explícita logo na abertura.
- **Prioridade:** Baixa

### Problema 6
- **Documento:** Slides (`slides.md`)
- **Local:** `<div class="tip">` após "Jump point: nó com vizinho forçado" versus slide "Erro comum" (antes de "Consolidação do Micro Game Navigation")
- **Descrição:** A mensagem "JPS é o mesmo A* — mesma f = g + h, mesma garantia de otimalidade" aparece duas vezes nos Slides, quase sem variação de redação, sem que as Dificuldades Esperadas 2 a 5 do Plano (vizinho forçado sem obstáculo, JPS+ em mundo dinâmico, otimização como troféu, confundir navegação individual com a de multidões) recebam reforço visual equivalente — apenas a Dificuldade 1 é reforçada duas vezes. Repetir o mesmo quadro pode ser intencional como retomada entre os dois encontros, mas o desequilíbrio de cobertura entre as cinco Dificuldades Esperadas do Plano é o mesmo padrão observado na Semana 6.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Refazer `mermaid-1.png` com os dois painéis especificados pela Apostila (terreno aberto com vizinho natural em destaque e vizinhos podados riscados; terreno com obstáculo mostrando o vizinho forçado e o rótulo "JUMP POINT"), acompanhados da ilustração do "pulo" atravessando células intermediárias sem expandi-las.
- Adicionar um diagrama (mesmo que simplificado) para a seção 9.3, contrastando visualmente o número de nós expandidos por A* e por JPS numa mesma grade aberta, apoiando a etapa 7 do Encontro 1 e o Objetivo de Aprendizagem 3.
- Acrescentar, no slide "Panorama de outras otimizações" ou em um slide adicional, uma frase curta por técnica (pathfinding hierárquico, flow fields, suavização) explicando o problema que cada uma resolve, para que o material escrito não dependa inteiramente da exposição oral nos 5 minutos previstos.
- Considerar um diagrama simplificado de linha de visão (string pulling) para a suavização de caminho, ou ao menos uma frase explicando o mecanismo (não apenas a ferramenta que o executa), dado o peso que a Apostila atribui a esse conceito para a "ilusão de inteligência".
- Avaliar se o slide "Objetivos da aula" deve incluir, mesmo que resumidamente, os objetivos ligados ao Encontro 2 (consolidação, desafio, engenharia reversa), já que ocupam metade da semana.
- Se a repetição do quadro "JPS é o mesmo A*" for mantida como retomada intencional entre encontros, considerar dar tratamento visual equivalente a pelo menos uma das outras Dificuldades Esperadas do Plano (por exemplo, a exigência de mundo estático do JPS+, que já tem bom suporte textual mas nenhum reforço visual dedicado).

---

## Atualização

As sugestões desta revisão foram aplicadas em `Slides/Semana 7/slides.md` e em `Slides/Semana 7/assets/` (`mermaid-1.png`, `mermaid-3.png`, `mermaid-4.png`):

- **Problema 1 (corrigido):** `mermaid-1.png` foi refeito como os dois painéis especificados pela Apostila (seção 9.2.1) — Painel A (terreno aberto), com o vizinho natural em verde e os sete vizinhos podados riscados em cinza; Painel B (obstáculo), com o obstáculo bloqueando uma célula, o vizinho forçado resultante em laranja e o nó central rotulado "JUMP POINT". A legenda do slide foi ajustada para descrever os dois painéis.
- **Problema 2 (corrigido):** foi criado `mermaid-3.png` e um novo slide ("Por que o JPS é mais rápido: menos nós na lista aberta"), logo após "Comparação de desempenho", com duas grades lado a lado — o leque denso de nós expandidos pelo A* contra os poucos jump points e os "pulos" do JPS, com o mesmo caminho final nos dois painéis — reproduzindo o diagrama da seção 9.3 da Apostila. A nota "FIGURA A PRODUZIR" que já antecipava esse mesmo diagrama na seção do Micro Game foi removida, por estar agora resolvida.
- **Problema 3 (corrigido):** foi adicionada, logo abaixo do diagrama "Panorama de outras otimizações", uma tabela com três linhas (pathfinding hierárquico, flow fields, suavização de caminho), cada uma indicando o problema que a técnica ataca e seu custo — cobrindo por escrito o que antes dependia inteiramente da exposição oral nos 5 minutos da etapa 7 do Encontro 1.
- **Problema 4 (corrigido):** foi criado `mermaid-4.png` e um novo slide ("Suavização de caminho — string pulling"), inserido antes de "Ferramentas", com o caminho bruto "escadinha" contrastado com o caminho suavizado, contornando um obstáculo, e os testes de linha de visão (✓/✗) — reproduzindo o diagrama da seção 9.4 da Apostila.
- **Problema 5 (mitigado):** o slide "Objetivos da aula" ganhou uma linha citando os compromissos do Encontro 2 (consolidação, Desafio, Engenharia Reversa), e o "Resumo da semana" passou a citar explicitamente pathfinding hierárquico, flow fields e suavização como técnicas que atacam problemas diferentes.
- **Problema 6 (mitigado):** foi adicionado um quadro de aviso no slide "Perguntas para observação", cobrindo a Dificuldade Esperada 5 do Plano (confundir navegação individual com navegação de multidões na Engenharia Reversa), sem remover o quadro "Erro comum" já existente sobre JPS/otimalidade — que permanece como retomada intencional entre os dois encontros.

O `semana_7_slides.pptx` e o `semana_7_slides.pdf` não foram regenerados manualmente nesta sessão — como nas Semanas 4 a 6, esses arquivos são produzidos automaticamente pelo workflow `marp-slides.yml` a partir do `slides.md` atualizado, ao ser enviado ao repositório. Os três novos diagramas (`mermaid-1.png`, `mermaid-3.png`, `mermaid-4.png`) foram gerados diretamente como imagens (não via bloco ```mermaid` no `slides.md`), pela mesma razão prática que levaria o workflow a fazê-lo: a ferramenta de renderização Mermaid depende de um navegador Chromium que não estava disponível neste ambiente. O conteúdo, a estrutura e a paleta de cores dos diagramas seguem a especificação da Apostila e o padrão visual dos diagramas existentes.

---

## Parecer Final

**Pronta para aplicação.**

Com a reconstrução do diagrama de vizinhos naturais/podados/forçados, a adição do diagrama comparativo de nós expandidos (A* × JPS), a tabela de apoio ao panorama de outras otimizações, o novo diagrama de suavização de caminho e os ajustes pontuais de cobertura nos Objetivos, no Resumo e nas Dificuldades Esperadas, os seis problemas identificados nesta revisão foram resolvidos. A Semana 7 cumpre bem sua função de encerrar o Módulo 2 com fidelidade à Apostila (Capítulo 9 completo), sem antecipar a Unidade III, com as quatro entregas do módulo corretamente dimensionadas e com o material visual agora cobrindo os três diagramas que o próprio Plano de Aula já previa na "Preparação do Professor".
