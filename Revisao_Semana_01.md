# Revisão da Semana 1 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_01.md` e `Slides/Semana 1/slides.md` (+ `semana_1_slides.pptx`, 21 slides, contagem consistente com o `.md`)
**Referência de verdade:** Apostila — Parte I, Capítulo 1 ("O que é Inteligência Artificial em Jogos") e Capítulo 2 ("História e Evolução da IA em Jogos")

---

## Resumo Geral

A Semana 1 cumpre bem sua função de abertura: estabelece o vocabulário conceitual do semestre (ilusão de inteligência, ciclo Sentir-Pensar-Agir, tipos de agente, panorama histórico) sem antecipar nenhuma técnica das partes seguintes, e organiza a logística do PBL (grupos, AI Playground, esboço do Micro Game 1) sem exigir implementação. Plano de Aula e Slides são coerentes entre si — mesma sequência, mesmos exemplos (Pac-Man, Half-Life, Halo 2, F.E.A.R.), mesma citação de Heider e Simmel e do canal de fluxo. O tempo fecha certinho em 90 + 90 minutos.

O ponto que efetivamente precisa de ajuste é um só, e é pontual: a Seção 1.4 da Apostila ("Critérios de qualidade de uma IA de jogo" — em especial 1.4.1 Custo computacional/orçamento de quadro e 1.4.2 Controle do designer) está listada nos "Conteúdos" do plano, mas não recebe nenhum bloco de tempo dedicado no Encontro 1, nem aparece nos Slides além da tabela comparativa introdutória. Como o Objetivo 1 da semana promete explicitamente que o aluno saberá diferenciar os dois campos "identificando critérios de sucesso distintos (credibilidade, diversão, **custo computacional e controle do designer**)", há uma lacuna entre o que se promete e o que a sequência de atividades efetivamente cobre em profundidade.

Não há Tutorial para a Semana 1 no repositório — o que é coerente com o fato de não haver implementação nesta semana, mas vale confirmar que essa ausência é intencional e não um arquivo faltante.

---

## Pontos Fortes

- **Sequência didática respeitada à risca.** Nenhuma técnica de Máquinas de Estado ou de qualquer Parte posterior é antecipada; a Semana 1 é genuinamente conceitual e organizacional, como o próprio plano declara.
- **Coerência de exemplos entre Plano e Slides.** Pac-Man, Space Invaders, Half-Life, Halo 2 e F.E.A.R. aparecem nos dois documentos, na mesma ordem e com o mesmo enquadramento histórico do Capítulo 2.
- **Fidelidade conceitual à Apostila.** Ilusão de inteligência, IA forte/fraca, ciclo Sentir-Pensar-Agir, tipos de agente (reativo/deliberativo/híbrido) e o canal de fluxo de Csíkszentmihályi são tratados com a mesma terminologia e profundidade da Seção 1.2–1.3.
- **Encaixe correto da Engenharia Reversa.** O plano evita transformar os exemplos históricos em exercício analítico, reservando isso corretamente para a Semana 4 — decisão explícita e bem justificada no texto.
- **Ferramentas na medida certa.** Nenhuma ferramenta de IA é usada nesta semana; apenas criação de projeto Unity vazio, coerente com "nunca apresentar ferramenta antes do conceito".
- **Timing exato.** Os dois encontros somam exatamente 90 minutos cada, sem sobra nem estouro, e a tabela de dificuldades esperadas é concreta e acionável.
- **Micro Game com escopo realista.** Exigir apenas um esboço textual (sem implementação) evita ambição excessiva na primeira semana e evita o risco, comum em Semana 1 de qualquer disciplina, de tentar entregar conteúdo técnico antes de a turma estar organizada.

---

## Problemas Encontrados

### Problema 1
- **Documento:** Plano de Aula (Encontro 1) e Slides
- **Local:** Tabela do Encontro 1 (etapas 1–6) / slide "Dois critérios de sucesso distintos"
- **Descrição:** A Seção 1.4 da Apostila (Critérios de Qualidade — credibilidade, diversão, custo computacional/orçamento de quadro, controle do designer, previsibilidade, robustez, depurabilidade, escalabilidade) está listada nos "Conteúdos" do plano, mas nenhuma etapa do Encontro 1 é dedicada a ela além da tabela introdutória de 1.1.2. Os números concretos que a Apostila usa para tornar o conceito memorável (orçamento de quadro de ~16,7 ms a 60 FPS) e os exemplos de ferramentas de controle de autoria (Unity Behavior, Animator, Visual Scripting, citados na Apostila como "Na Indústria") não aparecem nem no plano nem nos slides.
- **Prioridade:** Média

### Problema 2
- **Documento:** Plano de Aula (Encontro 1, etapa "Panorama histórico") / Slides ("Hardware e técnica caminham juntos")
- **Descrição:** Os 15 minutos reservados a essa etapa precisam cobrir, no limite, seis subseções do Capítulo 2 (2.1 a 2.6), incluindo a distinção entre achievement documentado e análise provável — um ponto que a própria Apostila trata com um box de "Atenção" por ser fonte comum de erro. Nos slides, a "era dos dados" (aprendizado de máquina, PCG, *Black & White*, *AlphaGo*) some, reduzida a uma linha genérica ("dados, ferramentas visuais e aprendizado de máquina"). Não é um erro de conteúdo — é compressão aceitável para uma introdução —, mas o tempo alocado é apertado para o volume do Capítulo 2 se o professor quiser preservar a ressalva "documentado x inferido", que é justamente a disciplina metodológica que a Engenharia Reversa (Semana 4 em diante) vai exigir da turma.
- **Prioridade:** Baixa

### Problema 3
- **Documento:** Ausência de material (Tutorial)
- **Local:** Pasta da disciplina — não há tutorial para a Semana 1
- **Descrição:** Os critérios de revisão da disciplina prevêem verificação de Tutorial, mas nenhum arquivo de tutorial existe para esta semana. Isso é coerente com a ausência de implementação prática na Semana 1 (apenas esboço textual + setup vazio do Unity), mas não há, no Plano de Aula, uma frase explícita confirmando que a ausência de tutorial é intencional — um leitor futuro (outro professor assumindo a disciplina) pode interpretar isso como arquivo faltante em vez de decisão de design.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

Incluir, na etapa "IA de jogos x IA acadêmica" do Encontro 1 (ou no fechamento da etapa "Ciclo Sentir-Pensar-Agir"), uma menção explícita e breve ao orçamento de quadro (os ~16,7 ms a 60 FPS da Seção 1.4.1) e ao controle do designer como conteúdo autoral (Seção 1.4.2), já que o Objetivo 1 do plano promete essa diferenciação nominalmente. Não é necessário expandir o tempo do encontro — um slide adicional ou um parágrafo a mais na etapa já prevista resolve, sem comprometer o equilíbrio de 90 minutos.

Adicionar, no Plano de Aula, uma linha explícita em "Conteúdos" ou em "Ferramentas" esclarecendo que não há Tutorial nesta semana por não haver implementação prática — mantém o documento autoexplicativo para qualquer professor que o utilize no futuro.

Se o tempo da etapa "Panorama histórico" permanecer em 15 minutos, considerar reduzir ainda mais a ambição da "era dos dados" no discurso do professor (uma frase, não um bloco), e reforçar a ressalva "documentado x análise provável" apenas verbalmente, sem tentar cobrir todos os exemplos do Capítulo 2 — o Cronograma já lista essa etapa entre os "encontros com folga relativa comportáveis", então nenhuma mudança estrutural é necessária.

---

## Parecer Final

**Pronta com pequenos ajustes.**

O Plano de Aula e os Slides da Semana 1 são coerentes entre si, fiéis à Apostila e adequados ao tempo disponível. O único ajuste que vale a pena fazer antes da aplicação é dar um espaço explícito — mesmo que breve — aos critérios de custo computacional e controle do designer (Seção 1.4), já que o próprio plano promete essa diferenciação como objetivo de aprendizagem. Os demais pontos (compressão do panorama histórico, ausência não documentada de tutorial) são observações de baixa prioridade que não impedem a aplicação da semana como está.
