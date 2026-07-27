# Revisão da Semana 6 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_06.md` e `Slides/Semana 6/slides.md` (+ `semana_6_slides.pptx`/`.pdf` e `assets/mermaid-1.png`, `assets/mermaid-2.png`)
**Referência de verdade:** Apostila — Parte III, Capítulo 8 (Busca de Caminhos com A*), seções 8.1 a 8.7
**Observação:** não há Tutorial dedicado para a Semana 6 no repositório. Assim como na Semana 5, isso é coerente com o estágio atual do projeto — a implementação prática é conduzida pela "Atividade de Laboratório" do próprio Plano — e não configura lacuna de documento.

---

## Resumo Geral

A Semana 6 apresenta o conteúdo tecnicamente mais denso do semestre até aqui — todo o Capítulo 8 da Apostila (Dijkstra, heurística, `f = g + h`, admissibilidade, consistência, laço principal, três heurísticas geométricas, A* ponderado e a relação com o NavMesh Agent) condensado em um único encontro teórico de 90 minutos. Ainda assim, Plano e Slides seguem a sequência da Apostila sem saltos nem antecipações indevidas do Capítulo 9 (JPS+), respeitam a filosofia "problema antes de ferramenta" e fecham os dois encontros exatamente em 90 minutos cada, sem excesso de tempo alocado.

Não foram encontradas contradições factuais entre os documentos e a Apostila — diferentemente da Semana 5, nenhum problema desta revisão é de prioridade Alta. O padrão recorrente aqui é outro: três diagramas especificados com riqueza pela Apostila (a função `f = g + h`; o laço principal com listas aberta/fechada; a comparação entre Manhattan, Chebyshev/octile e Euclidiana) foram implementados nos Slides em versões simplificadas que omitem elementos que a própria Apostila trata como obrigatórios para o entendimento do conceito — em especial, o diagrama de `f = g + h` não chega a exibir o próprio `f`. Como esses três pontos correspondem a três dos sete Objetivos de Aprendizagem da semana, vale corrigi-los antes da aplicação, ainda que o conteúdo textual dos slides e do Plano já comunique corretamente os conceitos por escrito.

---

## Pontos Fortes

- **Sequência fiel à Apostila, sem saltos.** O problema do menor caminho em tempo real (8.1) → Dijkstra e busca não-informada (8.2) → heurística e `f = g + h` (8.2.1) → admissibilidade/consistência (8.2.2) → laço principal com listas aberta/fechada (8.3.1) → heurísticas comuns (8.3.2) → A* ponderado → traço de execução (8.4) → vantagens/limitações (8.5) → ferramentas (8.7) é seguida na mesma ordem tanto no Plano quanto nos Slides.
- **Nenhuma antecipação do Capítulo 9.** Tanto o Plano quanto os Slides tratam a redundância de nós simétricos apenas como motivação para o JPS+, sem detalhar a técnica, e o slide de encerramento remete explicitamente a Semana 7 para a solução — coerente com a determinação do próprio Plano de não antecipar o capítulo seguinte.
- **Nenhuma implementação de produção fora de escopo.** O Plano é explícito ao afirmar que a implementação própria de A* tem "função exclusivamente didática", alinhado à seção 8.7 da Apostila (Boa Prática: reimplementar A* só para aprender, para grades sem suporte nativo, ou para controle fino) e ao princípio geral da disciplina de não implementar todos os algoritmos do zero.
- **Uso correto e proporcional do "Erro Comum" de casamento heurística/conectividade.** O slide "Heurísticas comuns" reproduz com fidelidade o alerta da seção 8.3.2 da Apostila sobre usar Manhattan em grade-8 (ou vice-versa), incluindo a tabela de correspondência heurística↔conectividade.
- **Convenção de imagem pendente respeitada.** O slide "Traço de execução" mantém o comentário `FIGURA A PRODUZIR` com descrição detalhada para produção posterior, em vez de inventar uma imagem inexistente — seguindo corretamente a diretriz de produção de materiais do projeto.
- **Fechamento do Micro Game com escopo controlado.** A evolução do Micro Game Navigation (novo destino/obstáculo + explicação verbal de g/h/f + implementação de A* em grade auxiliar como item opcional) preserva o escopo reduzido exigido pela metodologia, sem introduzir mecânicas alheias à IA.
- **Transição para o Capítulo 9 bem ancorada.** O fechamento do Encontro 2 relaciona corretamente a redundância de nós simétricos à motivação do JPS+, preparando o terreno para a Semana 7 sem entregar a solução antecipadamente.

---

## Problemas Encontrados

### Problema 1
- **Documento:** Slides (`assets/mermaid-1.png`)
- **Local:** Slide "A busca informada: f(n) = g(n) + h(n)"
- **Descrição:** A especificação de diagrama da Apostila (seção 8.2.1) exige explicitamente: os três marcos (Origem, nó `n`, Destino); o trecho Origem→n como linha **sólida** rotulada `g(n)` (custo já pago); o trecho n→Destino como linha **tracejada** rotulada `h(n)` (estimativa); uma chave abrangente com `f(n) = g(n) + h(n)`; e a regra "A* expande sempre o nó de MENOR f". O diagrama efetivamente produzido (`mermaid-1.png`) mostra apenas três caixas ligadas por duas setas rotuladas "g: custo pago" e "h: estimativa" — sem qualquer menção a `f`, sem distinção visual entre linha sólida (exato) e tracejada (estimado), e sem a regra do menor `f`. Como o Objetivo de Aprendizagem 2 da semana pede exatamente a definição precisa de `g`, `h` **e** `f`, e este é o único diagrama dedicado a esse conceito em toda a semana, a ausência de `f` no diagrama é uma lacuna relevante — o texto abaixo do diagrama no slide supre parcialmente a falta, mas o elemento visual central da Apostila para fixar o conceito não está presente.
- **Prioridade:** Média

### Problema 2
- **Documento:** Slides (`assets/mermaid-2.png`)
- **Local:** Slide "Listas aberta e fechada"
- **Descrição:** A Apostila (seção 8.3.1) especifica um fluxograma com: teste "lista aberta vazia? → FALHA"; retirada do nó de menor `f`; teste "é o destino? → reconstruir caminho e terminar"; movimentação para a lista fechada; e, para cada vizinho, o teste condicional "`custoTentativa < g(vizinho)`?" antes de atualizar `g`, `f` e predecessor. O diagrama produzido mostra apenas um ciclo linear (Lista Aberta → Expandir menor f → Lista Fechada → Relaxar arestas → volta à Lista Aberta), sem nenhuma condição de parada, sem o caso de falha (destino inalcançável) e sem o teste condicional do relaxamento. Sem a condição de parada, o diagrama comunica um laço que nunca termina — o texto do slide anterior ("Laço principal do A*", com os 5 passos numerados) supre parcialmente essa lacuna, mas o diagrama, isoladamente, não reflete um dos comportamentos mais importantes do algoritmo: saber quando parar.
- **Prioridade:** Média

### Problema 3
- **Documento:** Slides (`slides.md`)
- **Local:** Slide "Heurísticas comuns"
- **Descrição:** A Apostila (seção 8.3.2) especifica um diagrama comparativo com três painéis de uma mesma grade 8×8, mostrando visualmente o caminho e o valor de `h` calculado por Manhattan (h=8, "escada" ortogonal), Chebyshev/octile (h=5 ou 3·1,41+2·1,0, passos diagonais) e Euclidiana (h≈5,83, linha reta), associando cada uma ao seu conjunto de movimentos permitido. Nenhum diagrama equivalente foi produzido — o slide contém apenas uma tabela de texto associando cada heurística à sua conectividade, sem nenhuma representação visual do cálculo ou do caminho geométrico correspondente. Esse é justamente o diagrama que sustenta o Objetivo de Aprendizagem 4 ("selecionar a heurística geométrica adequada"), e sua ausência deixa o conceito apoiado apenas em nomes e fórmulas, sem a intuição visual que a Apostila constrói deliberadamente.
- **Prioridade:** Média

### Problema 4
- **Documento:** Slides (`slides.md`), comparado à Apostila e às Dificuldades Esperadas do Plano de Aula
- **Local:** Slide "Erro comum" (único slide desse tipo na semana) e ausência de slide equivalente para outros pontos
- **Descrição:** A Apostila registra dois blocos de "Erro Comum" no Capítulo 8: (a) na seção 8.2, confundir "a heurística decide o caminho" com seu papel real de apenas ordenar a exploração; (b) na seção 8.3.3 (como "Boa Prática"), confundir o conjunto de nós explorados (aberta+fechada) com o caminho final devolvido. O único slide de erro comum da semana cobre exclusivamente a confusão entre `g` e `h` — que também é a Dificuldade Esperada 1 do Plano. As Dificuldades Esperadas 2 ("achar que a heurística decide o caminho") e 4 ("confundir nós explorados com caminho final") não têm nenhum slide de apoio correspondente, obrigando o professor a criar esse material improvisadamente durante a aula, sem o apoio visual que os demais pontos da semana recebem.
- **Prioridade:** Média

### Problema 5
- **Documento:** Plano de Aula, Encontro 1, etapa 7 ("Heurísticas comuns")
- **Local:** Coluna "Duração" (5 min)
- **Descrição:** A etapa apresenta três heurísticas distintas (Manhattan, Euclidiana, Chebyshev/octile), a regra de casamento com a conectividade da grade e o erro comum de trocá-las — o mesmo conteúdo para o qual a Apostila reserva um diagrama comparativo de três painéis (ver Problema 3). Com apenas 5 minutos e sem o apoio visual correspondente nos Slides, a etapa depende inteiramente da exposição oral do professor para transmitir uma distinção que a própria Apostila trata como sutil o bastante para merecer um diagrama dedicado.
- **Prioridade:** Baixa

### Problema 6
- **Documento:** Slides (`slides.md`)
- **Local:** Slide sem cabeçalho, logo após "Admissibilidade e consistência" (contém apenas a `<div class="tip">` sobre reprocessamento de nós fechados)
- **Descrição:** O slide é composto exclusivamente por uma caixa de dica, sem título ou contexto textual próprio — um formato "solto" que quebra o padrão do restante do material, em que toda caixa de destaque (tip/warning) aparece acompanhada de um título de slide. Isso pode causar estranhamento visual na apresentação, ainda que o conteúdo em si esteja correto.
- **Prioridade:** Baixa

### Problema 7
- **Documento:** Plano de Aula, seção "Micro Game", item 2 de "Funcionalidades esperadas ao final da Semana 6"
- **Local:** Trecho "capacidade do grupo de explicar, **célula a célula**, como uma implementação simplificada de A* chegaria ao mesmo resultado que o NavMesh Agent já produz"
- **Descrição:** A cena de referência do Micro Game Navigation usa NavMesh (representação por polígonos, seção 7.3.3 da Apostila), não uma grade de células (seção 7.3.1). O termo "célula a célula" é impreciso nesse contexto — a Apostila é cuidadosa em distinguir grade, waypoints e NavMesh como representações diferentes, cada uma com seu vocabulário próprio (célula para grade; polígono/nó para NavMesh). Se a frase pretende se referir à implementação auxiliar opcional em grade, isso não fica claro no texto; se pretende se referir à explicação sobre a NavMesh do Micro Game principal, o termo correto seria "nó a nó" ou "polígono a polígono".
- **Prioridade:** Baixa

### Problema 8
- **Documento:** Plano de Aula (Encontro 1, etapa 8), comparado ao Cronograma
- **Local:** Descrição do Encontro 1 no Cronograma ("Fundamentação teórica... **Demonstração** de uma implementação própria simplificada") versus etapa 8 do Encontro 1 no Plano ("**Anuncia** que o Encontro 2 demonstrará uma implementação própria simplificada")
- **Descrição:** O Cronograma descreve a demonstração da implementação própria como parte do Encontro 1, mas o Plano de Aula apenas anuncia essa demonstração no Encontro 1 e a realiza de fato no Encontro 2 (etapa 2, 20 min). Não há inconsistência entre Plano e Slides — ambos concordam entre si sobre quando a demonstração ocorre — mas a redação do Cronograma, se lida isoladamente, pode gerar a expectativa equivocada de que a demonstração acontece já no primeiro encontro.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Refazer `mermaid-1.png` incluindo o valor `f(n)` como chave abrangente sobre os trechos g/h, distinguindo visualmente a linha sólida (g, exato) da tracejada (h, estimado), e adicionando a regra "expande-se sempre o menor f" diretamente no diagrama.
- Refazer `mermaid-2.png` como um fluxograma real (não um ciclo linear), incluindo ao menos o teste "é o destino?" com a saída para reconstrução do caminho e, idealmente, o caso de lista aberta vazia (falha).
- Adicionar um diagrama comparativo (mesmo que simplificado em relação à especificação de 3 painéis da Apostila) mostrando visualmente o cálculo de Manhattan, Chebyshev/octile e Euclidiana sobre uma mesma grade pequena, apoiando o slide "Heurísticas comuns" e a etapa 7 do Encontro 1.
- Acrescentar, no slide "Erro comum" ou em um novo slide, a distinção entre "heurística ordena, não decide o caminho" e "nós explorados ≠ caminho final", cobrindo as Dificuldades Esperadas 2 e 4 do Plano com o mesmo apoio visual já dado à Dificuldade 1.
- Adicionar um título ao slide que hoje contém apenas a caixa de dica sobre consistência (por exemplo, "Por que a consistência importa"), alinhando-o ao padrão visual do restante do material.
- Esclarecer, no item 2 de "Funcionalidades esperadas" do Micro Game, se a explicação célula a célula se refere à implementação auxiliar em grade (opcional) ou à NavMesh principal — trocando o termo por "nó a nó"/"polígono a polígono" neste último caso.
- Ajustar a redação do Cronograma (ou uma nota no Plano) para deixar explícito que a demonstração ao vivo da implementação própria ocorre no Encontro 2, evitando a leitura isolada de que ela acontece já no Encontro 1.

---

## Atualização

As sugestões desta revisão foram aplicadas em `Slides/Semana 6/slides.md`, `Slides/Semana 6/assets/mermaid-1.png`, `Slides/Semana 6/assets/mermaid-2.png`, `Planos de aula/Plano_de_Aula_Semana_06.md` e `Cronograma/Cronograma_IA.md`:

- **Problema 1 (corrigido):** `mermaid-1.png` foi refeito — agora mostra `g(n)` como seta sólida (custo pago, exato), `h(n)` como seta tracejada (estimativa, não pago), a chave abrangente `f(n) = g(n) + h(n)` sobre os dois trechos, e a regra "A* expande sempre o nó de MENOR f" destacada no próprio diagrama.
- **Problema 2 (corrigido):** `mermaid-2.png` foi refeito como um fluxograma real, incluindo o teste "lista aberta vazia?" com o caso de falha, o teste "ATUAL é o destino?" com a saída para reconstrução do caminho, o teste condicional "custoTentativa < g(vizinho)?" antes do relaxamento, e um painel lateral com o estado das listas aberta e fechada.
- **Problema 3 (corrigido):** foi criado `assets/mermaid-3.png` e um novo slide ("Mesma origem e destino, três medidas diferentes") logo após "Heurísticas comuns", com três painéis de uma mesma grade mostrando o caminho e o valor de `h` calculado por Manhattan (h=8), Chebyshev/octile (h=5, ou ≈6,23 na variante ponderada) e Euclidiana (h≈5,83) — reproduzindo o exemplo numérico da Apostila.
- **Problema 4 (corrigido):** foram adicionados dois novos slides "Erro comum", um logo após o slide de admissibilidade/consistência ("a heurística não decide o caminho, apenas ordena a exploração") e outro logo após o diagrama de listas aberta/fechada ("nós explorados não são o caminho final"), cobrindo as Dificuldades Esperadas 2 e 4 do Plano com o mesmo tratamento visual já dado à Dificuldade 1.
- **Problema 5 (mitigado):** o novo diagrama comparativo de heurísticas (Problema 3) dá suporte visual à etapa 7 do Encontro 1, reduzindo o risco de que os 5 minutos previstos dependam inteiramente da exposição oral do professor. O tempo da etapa não foi alterado — se a experiência em sala mostrar que ainda é insuficiente, considerar ampliá-la em 5 minutos, retirando o tempo da etapa 8 (que hoje é apenas um anúncio).
- **Problema 6 (corrigido):** o slide que continha apenas a caixa de dica sobre consistência ganhou o título "Por que a consistência importa".
- **Problema 7 (corrigido):** o item 2 de "Funcionalidades esperadas" do Micro Game, no Plano de Aula, foi reescrito para diferenciar explicitamente "nó a nó (polígono a polígono na NavMesh)" de "célula a célula" (reservado à grade auxiliar opcional).
- **Problema 8 (corrigido):** o Cronograma foi ajustado — a frase "Demonstração de uma implementação própria simplificada..." foi movida do campo Encontro 1 para o campo Encontro 2, onde a demonstração de fato ocorre segundo o Plano de Aula.

O `semana_6_slides.pptx` e o `semana_6_slides.pdf` não foram regenerados manualmente nesta sessão — assim como nas Semanas 4 e 5, esses arquivos são produzidos automaticamente pelo workflow `marp-slides.yml` a partir do `slides.md` atualizado, ao ser enviado ao repositório.

---

## Parecer Final

**Pronta para aplicação.**

Com a reconstrução dos diagramas de `f = g + h` e do laço principal, a adição do diagrama comparativo de heurísticas, a cobertura visual das quatro Dificuldades Esperadas do Plano, o título do slide antes órfão e o ajuste de redação entre Plano e Cronograma, os oito problemas identificados nesta revisão foram resolvidos. A Semana 6 cumpre bem sua função de apresentar o algoritmo mais importante da disciplina até aqui, com fidelidade à Apostila, sem antecipar o Capítulo 9 e com o material visual agora carregando o mesmo peso pedagógico que a Apostila atribui a cada conceito.
