# Revisão da Semana 2 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_02.md` e `Slides/Semana 2/slides.md` (+ `semana_2_slides.pptx`, 21 slides, contagem consistente com o `.md`)
**Referência de verdade:** Apostila — Parte II, Capítulo 3 (Máquinas de Estado Finitas — FSM)
**Observação:** não há Tutorial dedicado para a Semana 2 no repositório. Isso é coerente, pois a implementação é conduzida diretamente pela "Atividade de Laboratório" e pelo Encontro 2 do próprio Plano de Aula — não há, portanto, lacuna de material, apenas ausência de um documento separado.

---

## Resumo Geral

A Semana 2 é sólida e cumpre bem sua função de primeira semana técnica do Módulo 1: introduz a FSM seguindo rigorosamente a sequência problema → fundamentos → funcionamento → exemplo → ferramenta, sem antecipar HFSM (Capítulo 4) ou Árvores de Comportamento (Capítulo 6), e sem apresentar ferramentas de terceiros antes da hora — a decisão de reservar NodeCanvas/Behavior Designer para a Semana 4 está corretamente registrada e alinhada à própria Apostila (seção 3.8), que também adia esse aprofundamento ao Capítulo 6. Plano de Aula e Slides seguem a mesma terminologia e, em sua maior parte, a mesma sequência da Apostila, e o Micro Game (primeira versão da FSM do NPC Decision, três a cinco estados) tem escopo bem calibrado, evitando antecipar a explosão de transições na prática.

Os dois pontos que pedem atenção são de natureza semelhante e já apareceram na revisão da Semana 1: um objetivo de aprendizagem promete profundidade que o material não entrega por completo, e a tabela de tempo do Encontro 1 não cobre explicitamente todo o conteúdo que aparece nos Slides. Nenhum dos dois compromete a aplicação da semana, mas ambos merecem ajuste antes ou durante a aula.

---

## Pontos Fortes

- **Sequência didática respeitada.** Problema (3.1) → fundamentos (3.2) → funcionamento (3.3) → exemplo (3.4) → ferramenta (3.7) é seguida tanto no Plano quanto nos Slides, sem antecipar HFSM ou Árvores de Comportamento — a explosão de transições é corretamente apresentada como "problema em aberto", exatamente como o Plano determina.
- **Coerência terminológica entre Plano e Slides.** Estado, transição, evento/guarda e ação; polling versus eventos; enter/update/exit; o exemplo do guarda de cinco estados (Patrulhar, Investigar, Perseguir, Atacar, Fugir) — tudo aparece com o mesmo vocabulário nos dois documentos e na Apostila.
- **Adiamento correto de ferramentas de terceiros.** O Plano declara explicitamente que NodeCanvas e Behavior Designer ficam para a Semana 4, o que está alinhado à própria Apostila (seção 3.8), que também remete essas ferramentas ao Capítulo 6.
- **Micro Game com escopo bem calibrado.** Exigir de três a cinco estados evita que os grupos experimentem a explosão de transições na própria implementação antes da discussão teórica — o problema é vivido de forma controlada, guiada, e não por acidente.
- **Timing exato.** Encontro 1 (10+15+20+15+20+10) e Encontro 2 (10+15+40+10+10+5) somam exatamente 90 minutos cada.
- **Fechamento com gancho para a Semana 3.** Tanto o Plano ("Preparação para a Próxima Semana") quanto os Slides (último slide) preparam a transição para HFSM a partir do mesmo problema — a explosão de transições vivida na prática.
- **Dificuldades esperadas concretas e acionáveis**, com estratégias de intervenção específicas (ex.: distinguir update de enter/exit, definir prioridade entre guardas).

---

## Problemas Encontrados

### Problema 1
- **Documento:** Plano de Aula (Objetivo 3 e Encontro 1, etapa "Fundamentos") / Slides (slide "A resposta: Máquina de Estados Finita")
- **Local:** Objetivo de aprendizagem nº 3 do Plano; etapa 3 do Encontro 1 (20 min); slide de abertura dos fundamentos
- **Descrição:** O Objetivo 3 promete que o estudante será capaz de "relacionar a FSM à sua raiz teórica nos autômatos finitos, **justificando por que seu caráter finito e determinístico produz previsibilidade e depurabilidade**" — uma formulação que reproduz fielmente a seção 3.2.1 da Apostila. No entanto, nem o Plano nem os Slides desenvolvem essa justificativa: a etapa 3 do Encontro 1 apenas "introduz a raiz nos autômatos finitos", sem detalhar o argumento; e o slide correspondente reduz o ponto a uma única linha ("Base teórica: autômatos finitos"), sem conectar explicitamente "finito e determinístico" a "previsível e depurável". O conceito está corretamente citado, mas o *raciocínio* que o Objetivo 3 promete ensinar não está, de fato, redigido em nenhum dos dois materiais — depende inteiramente da improvisação oral do professor.
- **Prioridade:** Média

### Problema 2
- **Documento:** Plano de Aula (tabela do Encontro 1) / Slides
- **Local:** Etapas 5–6 do Encontro 1 / slides "Exemplo canônico: o guarda de 5 estados" e "Aplicações em jogos comerciais"
- **Descrição:** Os Slides trazem dois blocos de conteúdo — o exemplo canônico do guarda de cinco estados (Apostila 3.4) e as aplicações em jogos comerciais, Pac-Man e Half-Life (Apostila 3.6) — posicionados, na sequência do deck, entre o ciclo enter/update/exit e o encerramento do Encontro 1 (o segundo inclusive depois do slide de demonstração do Animator). Nenhum desses dois blocos, porém, tem uma etapa correspondente na tabela do Encontro 1: a etapa 5 (20 min) cobre apenas "funcionamento: polling, eventos e enter/update/exit", e a etapa 6 (10 min) é dedicada exclusivamente à "demonstração no Unity (Animator)". Não fica explícito em que momento dos 90 minutos o professor deve apresentar o exemplo do guarda e os exemplos de mercado — o risco é que esse conteúdo seja espremido informalmente dentro de etapas já com tempo justo (a etapa 6, por exemplo, já reserva seus 10 minutos inteiros para a demonstração ao vivo do Animator).
- **Prioridade:** Média

### Problema 3
- **Documento:** Plano de Aula ("Conteúdos" e "Ferramentas") / Slides
- **Local:** Bullet de "Conteúdos" referente à seção 3.7 da Apostila; tabela "Ferramentas"
- **Descrição:** O bullet de "Conteúdos" menciona explicitamente "materialização da FSM no Animator Controller **e no Visual Scripting** da Unity (3.7)", mas o Visual Scripting não aparece em nenhum outro lugar: não há etapa dedicada a ele no Encontro 1, não há slide correspondente, e a tabela "Ferramentas" do Plano lista apenas Animator Controller e Scripting C#. É uma inconsistência interna pequena — o próprio documento promete um conteúdo que não desenvolve em nenhuma outra seção sua.
- **Prioridade:** Baixa

### Problema 4
- **Documento:** Slides
- **Local:** Ausência de slide dedicado às "vantagens" gerais da FSM (Apostila, seção 3.5, parte inicial — simplicidade, baixo custo, previsibilidade, depurabilidade, visualização)
- **Descrição:** Os Slides tratam bem a limitação central (explosão de transições, 3.5.1), mas não reúnem, em nenhum slide, a lista de vantagens da FSM de forma explícita — elas aparecem apenas de forma esparsa (previsibilidade citada de passagem junto aos autômatos; depurabilidade nunca é nomeada como tal). O "Resumo da semana" cobre pontos equivalentes, mas de forma implícita, misturados a outros tópicos. Isso é uma omissão menor: o conteúdo é logicamente coberto no material oral, mas nenhum slide oferece ao aluno o quadro comparativo "vantagens x limitações" que a Apostila apresenta como bloco único.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

Acrescentar, na etapa 3 do Encontro 1 ou no slide correspondente, uma frase explícita ligando "finito e determinístico" a "previsível e depurável" — por exemplo, retomando a ideia de que o professor "pode enumerar todos os estados e revisar todas as transições, tendo certeza de que não há comportamento escondido". Não é necessário expandir o tempo da etapa; um parágrafo a mais no roteiro do professor ou uma linha adicional no slide resolve a lacuna entre o Objetivo 3 e o material.

Adicionar, na tabela do Encontro 1, uma referência explícita a onde o exemplo do guarda de cinco estados e os exemplos de mercado (Pac-Man, Half-Life) devem ser apresentados — por exemplo, incorporando-os textualmente à etapa 5 ("funcionamento... e ilustração com o exemplo do guarda") ou reservando um ou dois minutos adicionais dentro da etapa 6, reduzindo proporcionalmente a etapa 3 ou 4 caso necessário. O objetivo é apenas que a tabela reflita fielmente tudo o que os Slides efetivamente apresentam em aula.

Remover a menção ao Visual Scripting do bullet de "Conteúdos" (Problema 3) caso a decisão seja realmente não abordá-lo nesta semana, ou, alternativamente, adicionar uma frase breve nos Slides ou na tabela de Ferramentas reconhecendo sua existência como alternativa visual ao Animator — qualquer uma das duas opções resolve a inconsistência com uma única linha.

Se houver espaço no roteiro oral do professor, considerar unir "previsibilidade e depurabilidade" (Problema 1) e um resumo rápido de vantagens (Problema 4) em um único slide ou fala de transição, evitando adicionar mais um slide isolado ao deck.

---

## Parecer Final

**Pronta com pequenos ajustes.**

O Plano de Aula e os Slides da Semana 2 são coerentes entre si, fiéis à sequência e à terminologia da Apostila, e adequados ao tempo disponível — os 90 minutos de cada encontro fecham exatamente, e o Micro Game tem escopo realista. Os ajustes recomendados (detalhar a justificativa de previsibilidade/depurabilidade a partir do caráter finito e determinístico da FSM, e mapear explicitamente na tabela do Encontro 1 onde o exemplo do guarda e as aplicações de mercado são apresentados) são pontuais e de baixo custo de correção. Nenhum deles envolve conteúdo incorreto, antecipação de técnicas futuras ou desalinhamento estrutural com a Apostila — apenas lacunas de detalhamento que não impedem a aplicação da semana como está.
