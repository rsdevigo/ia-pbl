# Revisão da Semana 3 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_03.md` e `Slides/Semana 3/slides.md` (+ `semana_3_slides.pptx`)
**Referência de verdade:** Apostila — Parte II, Capítulo 4 (Máquinas de Estado Hierárquicas — HFSM)
**Observação:** não há Tutorial dedicado para a Semana 3 no repositório, assim como na Semana 2 — coerente, pois a implementação é conduzida pela "Atividade de Laboratório" e pelo Encontro 2 do próprio Plano. Não há, portanto, lacuna de documento, apenas ausência de um arquivo separado.

---

## Resumo Geral

A Semana 3 é bem construída como continuação direta da Semana 2: retoma explicitamente a explosão de transições, introduz superestado/subestado/configuração ativa/histórico com a mesma terminologia da Apostila (seção 4.2), trata corretamente a avaliação em cascata e a herança de transições (4.3), a ordem de enter/exit entre níveis (4.3.1) e o estado de histórico (4.3.2), e fecha com a reestruturação guiada da FSM da Semana 2 em HFSM — um Micro Game de escopo bem calibrado, que reaproveita a implementação existente em vez de recomeçar do zero. Plano e Slides estão em sequência e terminologia consistentes entre si, e nenhum conteúdo de Árvores de Decisão (Cap. 5) ou Árvores de Comportamento/Blackboard (Cap. 6) é antecipado.

O ponto que mais pede atenção é estrutural: a seção "Conteúdos" do Plano lista dois itens da Apostila — aplicações em jogos (4.6) e ferramentas de terceiros/State Tree como panorama (4.8) — que não recebem etapa própria em nenhum dos dois Encontros nem slide correspondente, e que colidem parcialmente com o que o Cronograma já reserva, de forma explícita, para a Semana 4. Um segundo ponto, menor, é um selo visual ("Na indústria") usado nos Slides para um conteúdo que não é, de fato, um comentário de indústria. Nenhum dos dois compromete a aplicação da semana, mas ambos merecem ajuste.

---

## Pontos Fortes

- **Continuidade real com a Semana 2.** A abertura retoma explicitamente o crescimento quadrático de transições estimado na semana anterior, e o Micro Game reestrutura a FSM já implementada sem alterar seu comportamento observável — o ganho é de organização, exatamente como a Apostila (4.1) enquadra o problema.
- **Coerência terminológica entre Plano e Slides.** Superestado, subestado, configuração ativa, estado inicial de cada nível, avaliação em cascata, herança de transições, histórico raso versus profundo — todos os termos aparecem com o mesmo vocabulário nos dois documentos e na Apostila, sem termos alternativos ou ambíguos.
- **Erros comuns da Apostila corretamente transpostos.** O erro de omitir enter/exit de níveis intermediários (4.3.1) e a ressalva sobre uso indiscriminado de histórico (4.3.2) aparecem tanto no Plano ("Dificuldades Esperadas") quanto nos Slides (blocos de aviso), com o mesmo exemplo do guarda em "Recarregando".
- **Sequência didática respeitada.** Problema (4.1) → fundamentos (4.2) → funcionamento/herança (4.3, 4.3.1) → histórico (4.3.2) → ferramenta Unity (4.7) é seguida tanto no Plano quanto nos Slides, sem antecipar Árvores de Decisão ou Árvores de Comportamento — a limitação de comportamento sequenciado/reordenável é corretamente apresentada como "problema em aberto para a Semana 4".
- **Micro Game com escopo e continuidade bem calibrados.** Exigir a reestruturação (não recriação) de uma FSM já validada, com pelo menos dois superestados e uma transição herdada, evita que o grupo enfrente decisões de design do zero justamente na semana em que o foco é a hierarquia, não a modelagem inicial.
- **Timing exato.** Encontro 1 (10+15+20+20+15+10) e Encontro 2 (10+15+15+35+5+5+5) somam exatamente 90 minutos cada.
- **Ferramentas corretamente restritas ao escopo do Cronograma.** O Plano e a tabela "Ferramentas" declaram explicitamente que a comparação com NodeCanvas/Behavior Designer/State Tree é "apenas panorama teórico, sem uso prático nesta semana" — alinhado ao Cronograma, que reserva ferramentas de terceiros com uso comparativo para a Semana 4.
- **Fechamento com gancho correto para a Semana 4.** Tanto o Plano ("Preparação para a Próxima Semana") quanto os Slides (último slide) anunciam Árvores de Comportamento e Blackboard a partir da mesma limitação discutida na "Discussão técnica: FSM plana versus HFSM".

---

## Problemas Encontrados

### Problema 1
- **Documento:** Plano de Aula (seção "Conteúdos") / Slides / Cronograma
- **Local:** Bullet "aplicações em jogos, com destaque para sub-state machines e camadas de animação do Animator como materialização documentada (seção 4.6, 4.7)" e bullet "ferramentas de terceiros (NodeCanvas, Behavior Designer) e comparação com o State Tree da Unreal, apenas como panorama (seção 4.8)"
- **Descrição:** O Plano lista as seções 4.6 e 4.8 da Apostila como conteúdo previsto para a semana, mas nenhuma etapa do Encontro 1 ou 2 é dedicada a elas, e nenhum slide as cobre. Os Slides tratam apenas a materialização documentada no Animator (4.7, seção "HFSM no Unity: sub-state machines"), mas não trazem exemplos de jogos comerciais ou gêneros (4.6, o que a Semana 2 fez explicitamente com "Aplicações em jogos comerciais" para FSM) nem qualquer menção ao panorama de NodeCanvas/Behavior Designer/State Tree (4.8) — nem mesmo em nível de citação rápida, como o próprio Plano sugere fazer na seção "Engenharia Reversa" para 4.6 (mas ali como observação opcional, sem tempo reservado). Além disso, o item 4.8 no Plano de Aula da Semana 3 conflita parcialmente com o Cronograma: este atribui explicitamente a "comparação pontual a soluções de terceiros (NodeCanvas, Behavior Designer)" ao Encontro 1 da Semana 4, e a tabela "Ferramentas" do Cronograma para a Semana 3 lista apenas "Scripting C# (HFSM)", sem qualquer menção a 4.8. Ou seja: o conteúdo é citado como pertencente à Semana 3 no Plano, mas não é entregue em nenhum dos dois Encontros nem nos Slides, e sua entrega real e planejada (com comparação prática) já está reservada — corretamente — para a Semana 4.
- **Prioridade:** Média

### Problema 2
- **Documento:** Slides
- **Local:** Slide "O que a HFSM não resolve" (linha ~172–181)
- **Descrição:** O conteúdo do slide ("a hierarquia organiza a complexidade, mas o acoplamento entre estados e a rigidez estrutural da família FSM permanecem") é envolvido pela classe visual `industry`, que nos temas do curso é reservada para o selo "🏭 Na indústria" — usado consistentemente nas Semanas 1 e 2 para observações sobre uso em produção/mercado (ex.: "a FSM continua presente mesmo em jogos modernos..."). O conteúdo deste slide, porém, é uma afirmação conceitual sobre limitações teóricas da HFSM (Apostila, seção 4.5, inclusive already destacada lá como "❌ Erro Comum": "acreditar que a HFSM resolve de vez os problemas da FSM"), não um comentário de indústria. O selo visual está tecnicamente incorreto e pode confundir o leitor sobre a natureza da afirmação — o bloco correto seria `warning` (⚠️ Atenção) ou `error` (🚫 Erro comum), classes já usadas nos Slides desta mesma semana para conteúdo equivalente.
- **Prioridade:** Baixa

### Problema 3
- **Documento:** Plano de Aula (Objetivo 4)
- **Local:** Objetivo de aprendizagem nº 4
- **Descrição:** O Objetivo 4 pede que o estudante "justifique em que situações o estado de histórico é indispensável [...] e em que situações reiniciar pelo subestado inicial é a escolha correta" — uma exigência de justificativa em duas direções, espelhando fielmente o "Atenção" da seção 4.3.2 da Apostila. Os Slides, no entanto, tratam o ponto em um único slide curto ("Quando usar histórico?") com um exemplo de cada lado (guarda recarregando / comportamento "grudento"), sem espaço para os estudantes elaborarem a justificativa por conta própria. Isso não é um erro — o Encontro 1, etapa 5, reserva 15 minutos e inclui discussão em grupo sobre um caso de cada tipo —, mas o material de apoio (Slides) é mais raso do que o objetivo declarado exige; o risco é o mesmo já observado na Semana 2 (Problema 1 daquela revisão): a profundidade da justificativa depende quase inteiramente da condução oral do professor durante a discussão em grupo, sem apoio visual equivalente.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Adicionar, seja como um slide curto de 4.6 (aplicações em jogos, à semelhança do que a Semana 2 fez para FSM) seja apenas removendo a referência a 4.6/4.8 do bullet "Conteúdos" do Plano, para que a lista de conteúdos previstos corresponda exatamente ao que é de fato entregue no Encontro 1 ou 2. Caso a intenção seja mesmo tratar 4.8 apenas como "panorama sem uso prático", isso pode ser resolvido com uma frase única no fechamento do Encontro 1 (por exemplo, ao lado da demonstração do Animator), sem necessidade de tempo dedicado — mas então o Plano deveria dizer isso explicitamente, e não apenas listar 4.8 em "Conteúdos" sem etapa correspondente.
- Trocar a classe `industry` por `warning` (ou `error`) no slide "O que a HFSM não resolve", alinhando-o ao mesmo padrão visual usado nas Semanas 1 e 2 para esse tipo de conteúdo.
- Considerar adicionar um pequeno apoio visual (por exemplo, uma tabela de duas colunas "quando usar histórico" / "quando reiniciar") ao slide "Quando usar histórico?", dando ao Objetivo 4 um suporte visual equivalente ao que já existe para os demais objetivos da semana.

---

## Parecer Final

**Pronta com pequenos ajustes.**

A Semana 3 cumpre com solidez sua função central: apresentar a HFSM como resposta direta e bem fundamentada ao problema deixado em aberto pela Semana 2, com terminologia, sequência e exemplos consistentes entre Plano e Slides, sem antecipar conteúdo dos capítulos seguintes. Os problemas identificados são de baixo a médio impacto — uma lacuna de conteúdo declarado mas não entregue (4.6/4.8), um selo visual tecnicamente incorreto e uma profundidade de apoio visual aquém do que um objetivo específico promete — e nenhum deles compromete a aplicabilidade da semana em sala. Recomenda-se resolver o Problema 1 antes da aplicação (ajustando a lista de "Conteúdos" do Plano para refletir o que é realmente entregue), enquanto os Problemas 2 e 3 podem ser corrigidos em qualquer revisão de rotina dos Slides.
