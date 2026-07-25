# Revisão da Semana 5 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_05.md` e `Slides/Semana 5/slides.md` (+ `semana_5_slides.pptx`/`.pdf` e `assets/mermaid-1.png`, `assets/mermaid-2.png`)
**Referência de verdade:** Apostila — Parte III, Capítulo 7 (Grafos e Representação do Espaço), seções 7.1 a 7.5
**Observação:** não há Tutorial dedicado para a Semana 5 no repositório. Isso é coerente com o restante do projeto nesta fase — a implementação é conduzida pela "Atividade de Laboratório" do próprio Plano — e não configura lacuna de documento.

---

## Resumo Geral

A Semana 5 abre a Unidade II com um material tecnicamente sólido e bem estruturado. Plano e Slides seguem, com fidelidade, a sequência da Apostila (7.1 → 7.2.1 → 7.2.2 → 7.3.1/7.3.2/7.3.3 → 7.4 → 7.5), respeitam a filosofia "problema antes de ferramenta" (não antecipam o Capítulo 8/A\*, tratam grades, waypoints e A\* Pathfinding Project/Recast & Detour apenas como panorama comparativo) e distribuem o tempo dos dois encontros exatamente em 90 minutos cada, sem excesso nem falta de conteúdo evidente na maior parte das etapas.

Dois problemas merecem atenção antes da aplicação. O primeiro, de prioridade alta, é uma inversão factual entre o slide "Comparativo das três representações" e a Apostila: o slide classifica a atualização dinâmica da Grade como "Custosa" e da NavMesh como "Suportada", quando a Apostila afirma exatamente o oposto — atualização trivial na grade e mais cara na NavMesh. O segundo, de prioridade média, é uma omissão de conteúdo: o *corner cutting*, citado explicitamente no Plano como parte do conteúdo da seção 7.3.1, não aparece em nenhum slide, nem em texto nem no diagrama correspondente (`mermaid-2.png`), que também não representa uma grade nem exibe os valores de custo (1,0 / 1,41) mencionados na legenda do próprio slide. Nenhum dos dois problemas impede a aplicação da semana, mas ambos devem ser corrigidos — o primeiro por ser uma contradição direta com a fonte da verdade do projeto.

---

## Pontos Fortes

- **Sequência didática fiel à Apostila.** O problema (7.1: pathfinding vs. steering) → fundamentos de grafo (7.2.1: vértice/aresta/peso/direção) → custo/conectividade/memória (7.2.2) → as três representações espaciais (7.3.1/7.3.2/7.3.3) → ferramentas oficiais (7.4) → panorama de terceiros (7.5) é seguida sem saltos tanto no Plano quanto nos Slides, na mesma ordem e com a mesma terminologia da Apostila.
- **Nenhuma antecipação indevida.** Tanto o Plano quanto os Slides deixam explícito que o algoritmo A\* (Capítulo 8) não deve ser antecipado e que o A\* Pathfinding Project e o Recast & Detour aparecem "apenas como panorama comparativo, sem uso prático nesta semana" — coerente com a seção 7.5 da Apostila e com a tabela de Ferramentas do Cronograma.
- **Transição de unidade bem marcada.** A abertura do Encontro 1 (Plano, etapa 1) e o slide de pergunta norteadora ("Como um agente encontra seu destino?") comunicam com clareza que a Unidade II trata de um problema novo — navegação —, não uma continuação da decisão do Módulo 1, retomando corretamente o ciclo Sentir → Pensar → Agir.
- **Micro Game com escopo bem calibrado.** O objetivo da semana (configurar uma NavMesh funcional, com um agente indo a um destino fixo, usando a busca interna como caixa-preta) evita qualquer complexidade de algoritmo prematura e é plenamente compatível com o estágio "apenas representação, ainda sem busca" da Apostila.
- **Diagrama do grafo ponderado/direcionado bem-resolvido.** `mermaid-1.png` (Sala A – Corredor – Sala B – Queda) ilustra corretamente arestas não direcionadas com peso e uma aresta direcionada de mão única ("queda: só descida"), cobrindo os quatro elementos da seção 7.2.1 (vértice, aresta, peso, direção) num único diagrama compacto, tal como pedido pela Apostila.
- **"Dificuldades Esperadas" bem calibradas.** As cinco dificuldades listadas no Plano (confundir pathfinding/steering, custo diagonal igual ao ortogonal, confundir o papel do nó entre representações, parâmetros de agente incompatíveis com a geometria, esquecer de checar conectividade) espelham exatamente os blocos "❌ Erro Comum" e "⚠️ Atenção" da Apostila no Capítulo 7, sem inventar problemas alheios ao conteúdo da semana.
- **Ausência corretamente justificada de Engenharia Reversa.** O Plano é explícito ao dizer que não há momento de Engenharia Reversa nesta semana e que o próximo ocorre na Semana 7 — coerente com o Cronograma, que reserva os momentos formais às semanas de encerramento de módulo.

---

## Problemas Encontrados

### Problema 1
- **Documento:** Slides (`slides.md`)
- **Local:** Slide "Comparativo das três representações", linha "Atualização dinâmica"
- **Descrição:** O slide classifica a atualização dinâmica da **Grade** como "Custosa" e da **NavMesh** como "Suportada (NavMesh Obstacle)". A Apostila (seção 7.3.1) afirma o contrário para a grade: *"atualizações dinâmicas são triviais (bloquear ou liberar uma célula é mudar um único valor, útil quando o jogador constrói ou destrói estruturas em tempo real)"*. E para a NavMesh (seção 7.3.3), afirma que as atualizações dinâmicas *"são mais caras do que numa grade, exigindo técnicas específicas (recozimento local, carving de obstáculos)"*. Ou seja, a relação correta é: grade com atualização barata/trivial e NavMesh com atualização mais cara — exatamente o inverso do que o slide comunica. O rótulo "Suportada (NavMesh Obstacle)" não é falso em si (o componente existe e resolve um subconjunto de casos), mas, colocado como está na tabela comparativa, o slide ensina aos estudantes uma hierarquia de custo de atualização dinâmica que contradiz a fonte da verdade do projeto.
- **Prioridade:** Alta

### Problema 2
- **Documento:** Slides (`slides.md` e `assets/mermaid-2.png`) — comparado ao Plano de Aula e à Apostila
- **Local:** Slide "Grades: conectividade-4 e conectividade-8" e o diagrama `assets/mermaid-2.png`
- **Descrição:** O conteúdo previsto no Plano de Aula para a semana lista explicitamente "grades (conectividade-4 e conectividade-8, custo diagonal, *corner cutting*) — seção 7.3.1", e a Apostila trata o *corner cutting* (cortar a quina entre dois obstáculos diagonais) como uma das "duas sutilezas" centrais da conectividade-8, com um diagrama dedicado a marcá-lo com um "X" de proibição. Nem o texto do slide nem `mermaid-2.png` mencionam ou ilustram esse conceito. Além disso, o próprio diagrama está desalinhado com sua legenda: o slide afirma "Movimento diagonal custa √2 ≈ 1,41, não 1,0", mas `mermaid-2.png` mostra apenas dois grafos abstratos de nós conectados (sem grade, sem células bloqueadas e sem nenhum valor numérico de custo visível), muito aquém da especificação de diagrama da Apostila (grade 6×6 com células bloqueadas, oito setas rotuladas com os custos 1,0/1,41 e uma marcação de corner cutting proibido).
- **Prioridade:** Média

### Problema 3
- **Documento:** Plano de Aula, seção "Encontro 1", etapa 5 ("Grades e grafos de células")
- **Local:** Coluna "Duração" (15 min) e coluna "Atividade dos Estudantes"
- **Descrição:** A etapa acumula, em 15 minutos, três entregas: (a) apresentação da conectividade-4/8 e *corner cutting* pelo professor, (b) o cálculo, pelos estudantes, do custo total de dois caminhos alternativos em uma grade (um ortogonal, outro com diagonais) e (c) a discussão do resultado. A soma dos tempos do Encontro 1 fecha exatamente em 90 minutos (5+10+15+10+15+10+15+10), sem qualquer folga — o que é reconhecido pelo próprio Cronograma, que lista "Semana 5, Encontro 1" entre os poucos encontros com "folga relativa" e sugere comprimir justamente a apresentação das três representações espaciais em caso de atraso. Como a etapa 5 já é uma das mais densas (exposição + cálculo em grupo + discussão) e não tem tempo de reserva embutido, um pequeno atraso nas etapas anteriores (2 a 4) tende a comprimir justamente a etapa onde os estudantes praticam um cálculo, e não apenas escutam.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Corrigir a linha "Atualização dinâmica" da tabela comparativa do slide, invertendo os rótulos de Grade e NavMesh (ou reformulando-os) para refletir a Apostila: grade com atualização barata/trivial, NavMesh com atualização mais cara e dependente de técnicas específicas (o "NavMesh Obstacle" pode permanecer citado, mas como uma mitigação pontual, não como sinônimo de atualização barata).
- Adicionar ao slide "Grades: conectividade-4 e conectividade-8" uma menção textual ao *corner cutting* (mesmo que sintética) e substituir ou complementar `mermaid-2.png` por um diagrama que efetivamente mostre uma grade com células bloqueadas, os valores de custo 1,0/1,41 nas setas, e a marcação de uma diagonal proibida por corte de quina — aproximando o material da especificação de diagrama já descrita na Apostila.
- Caso a experiência em sala confirme que a etapa 5 do Encontro 1 estoura os 15 minutos previstos, considerar reduzir o cálculo manual a um único caminho (em vez de dois caminhos alternativos), preservando a comparação ortogonal/diagonal com menos tempo de aritmética em grupo.

---

## Atualização

As três sugestões desta revisão foram aplicadas em `Slides/Semana 5/slides.md`, `Slides/Semana 5/assets/mermaid-2.png` e `Planos de aula/Plano_de_Aula_Semana_05.md`:

- **Problema 1 (corrigido):** a linha "Atualização dinâmica" da tabela comparativa foi invertida para refletir a Apostila — Grade agora consta como "Trivial (mudar 1 célula)" e NavMesh como "Custosa (rebake; mitigada por NavMesh Obstacle)".
- **Problema 2 (corrigido):** o slide "Grades: conectividade-4 e conectividade-8" ganhou uma linha de texto explícita sobre *corner cutting*, e o diagrama `mermaid-2.png` foi refeito mostrando uma grade real com duas células bloqueadas, os custos 1,0/1,41 rotulados nas setas e a diagonal de corte de quina marcada com um X vermelho e o rótulo "corner cutting proibido".
- **Problema 3 (corrigido):** a etapa 5 do Encontro 1 do Plano de Aula foi ajustada — em vez de calcular dois caminhos alternativos completos, os estudantes calculam um caminho com diagonais e comparam oralmente com o custo que teriam ao tratar todos os passos como ortogonais, reduzindo o risco de estouro dos 15 minutos previstos.

O `semana_5_slides.pptx` e o `semana_5_slides.pdf` não foram regenerados manualmente nesta sessão — assim como na Semana 4, esses arquivos são produzidos automaticamente pelo workflow `marp-slides.yml` a partir do `slides.md` atualizado, ao ser enviado ao repositório.

---

## Parecer Final

**Pronta para aplicação.**

Com a correção da inversão factual na tabela comparativa (Grade × NavMesh), a inclusão do *corner cutting* no slide e no diagrama de grades, e o ajuste de escopo da etapa 5 do Encontro 1, os três problemas identificados foram resolvidos. A Semana 5 cumpre bem sua função de abrir a Unidade II com uma fundamentação sólida de grafos e representação espacial, sem antecipar o algoritmo de busca do Capítulo 8, com boa correspondência entre Plano, Slides e Apostila, e sem contradições factuais remanescentes.
