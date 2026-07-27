# Revisão — Semana 11

**Tema:** Heurísticas e Poda Alfa-Beta
**Módulo:** 4 — Como derrotar um adversário inteligente? (parte 2, encerramento do módulo)
**Documentos revisados:** Plano de Aula (Semana 11) e Slides (Semana 11) — não existe Tutorial nesta disciplina (nenhuma semana possui esse artefato); item de coerência com Tutorial é, portanto, não aplicável.
**Referência de verdade:** Apostila — Parte V, Cap. 11 (seções 11.3.4, 11.4, 11.4.1), citações à seção 11.3 (revisão), 11.7, 11.8 e 11.9; Parte VI, Cap. 13 (seção 13.1); Parte VII, Cap. 14 (seção 14.3); CLAUDE.md — "Micro Games — Exemplos de Implementação" (Módulo 4: Conecta 4 Reduzido); Cronograma (Semana 10–12); Revisao_Semana_10.md (para continuidade e para verificar se os ajustes ali registrados se propagaram); Plano de Ensino, Rubrica de Avaliação e Critérios de Notas (para a matriz de pesos do Módulo 4).

**Nota metodológica:** a Apostila em si não está disponível como arquivo neste ambiente de trabalho (não há `.md`/`.docx`/`.pdf` de apostila na pasta do projeto, nem histórico de commit que a inclua). A verificação de alinhamento à Apostila foi feita por triangulação entre os números de seção citados no Plano de Aula, nos Slides, no Cronograma e no Manual do Professor, e por continuidade com o conteúdo já verificado na Revisão da Semana 10 — não por leitura direta do texto da Apostila. Onde isso limita a confiança de uma constatação, isso é sinalizado explicitamente.

---

## Resumo Geral

A Semana 11 encerra o Módulo 4 com um Plano de Aula tecnicamente sólido e bem sequenciado: a progressão heurística de avaliação → motivação da poda → formalização de α/β → traçado guiado → corretude/complexidade/ordenação reproduz corretamente a estrutura das seções 11.3.4 e 11.4 (com 11.4.1), os dois encontros fecham exatamente em 90 minutos, e o Plano já incorpora — de forma visível — o ajuste feito na Revisão da Semana 10 quanto ao Micro Game: agora se compromete explicitamente com o Conecta 4 Reduzido em vez de tratá-lo como uma entre várias opções equivalentes. Os Slides seguem a mesma sequência conceitual do Plano com boa fidelidade. No entanto, essa correção não se propagou de forma completa: os Slides desta mesma semana ainda apresentam "damas simplificada ou Connect Four em grade reduzida" como alternativas equivalentes, reabrindo exatamente a ambiguidade que a Semana 10 já havia corrigido no Plano. Some a isso um problema de conteúdo visual — o diagrama do exemplo A/B/C usado nos Slides é uma árvore genérica sem qualquer anotação de α/β ou indicação de poda, apesar de a legenda do próprio slide e a especificação do Plano de Aula prometerem exatamente essas anotações — e uma citação de seção da Apostila (11.7) que não aparece em nenhum outro lugar do projeto, nem mesmo nos materiais da Semana 10 a que ela se refere. São problemas localizados e corrigíveis sem reestruturação, mas que afetam diretamente o critério de Coerência entre documentos e a qualidade do material de apoio visual desta semana.

---

## Pontos Fortes

- **Sequência fiel à Apostila e à continuidade da Semana 10.** O Plano cobre exatamente as seções 11.3.4 (heurística, trade-off, ponte com aprendizado) e 11.4/11.4.1 (motivação, funcionamento, corte alfa/beta, traçado, corretude, complexidade, ordenação), retomando o mesmo exemplo numérico (A→3,5; B→6,2; C→1,8) já usado na Semana 10 — dando continuidade pedagógica real em vez de reiniciar o exemplo do zero.
- **Ajuste da Semana 10 incorporado ao Plano.** Diferente do estado registrado na Revisão da Semana 10 (onde o Plano da Semana 11 tratava "damas simplificada" e "Connect Four" como alternativas equivalentes), a versão atual do Plano de Aula da Semana 11 compromete-se de forma consistente com o **Conecta 4 Reduzido** em todas as seções relevantes (Cena Unity, Objetivo 9, Micro Game, Atividade de Laboratório).
- **Tempos exatos.** Encontro 1: 10+25+15+20+15+5 = 90 minutos; Encontro 2: 10+35+10+15+15 = 90 minutos (mais 5 min de encerramento do módulo, cabendo dentro do bloco). Nenhuma etapa sobra ou falta tempo no papel.
- **Matriz de avaliação idêntica à fonte oficial.** Os pesos e critérios do Micro Game (50%), AI Design Log (25%), Desafio de Escolha Tecnológica (15%) e Engenharia Reversa (10%) descritos no Plano reproduzem exatamente a matriz do item 4 dos Critérios de Notas, e o peso do módulo (11,67%) confere com a distribuição das Semanas 4, 7, 9, 11, 13 e 16.
- **PDF exportado limpo.** A nota de produção de imagem embutida como comentário HTML no `slides.md` ("FIGURA A PRODUZIR") não vaza para o PDF exportado (28 páginas, verificadas integralmente) nem para o PPTX (28 slides) — o problema já corrigido na Semana 8 não se repete aqui.
- **Fechamento de módulo bem construído.** Tanto o Plano quanto o slide final articulam corretamente o encerramento do Módulo 4/Unidade IV, a transição de pergunta norteadora para a Semana 12 ("como encontrar automaticamente boas soluções?") e o alerta de que o Capítulo 13 será retomado do zero, não continuado a partir da seção 13.1 já vista.

---

## Problemas Encontrados

**Problema 1**
- **Documento:** Slides (Semana 11)
- **Local:** Slide "O que implementar hoje" (dentro da seção "Micro Game Board Game AI — consolidação") e slide de capa/meta
- **Descrição:** O Plano de Aula da Semana 11 já foi ajustado (por decisão registrada na Revisão da Semana 10) para se comprometer explicitamente com o **Conecta 4 Reduzido** como destino do Micro Game do Módulo 4, conforme fixado pelo CLAUDE.md. Os Slides desta mesma semana, porém, não acompanharam esse ajuste: o slide "O que implementar hoje" ainda lista "teste em tabuleiro maior (ex.: damas simplificada ou Connect Four em grade reduzida)" como alternativas equivalentes, e nem esse slide nem o de capa mencionam Conecta 4 Reduzido como o jogo definido. Isso reabre, dentro dos próprios materiais desta semana, a ambiguidade que a correção na Semana 10 pretendia fechar — falha direta no critério de Coerência (Plano de Aula e Slides devem ensinar exatamente o mesmo conteúdo).
- **Prioridade:** Alta

**Problema 2**
- **Documento:** Slides (Semana 11), slide "Retraçando o exemplo A/B/C com poda"
- **Local:** Imagem `assets/mermaid-1.png` e a legenda "Mesma árvore da Semana 10 — agora com α e β anotados a cada passo"
- **Descrição:** A imagem efetivamente usada é uma árvore MAX/MIN simples com os valores das folhas (3, 5, 6, 2, 1, 8), mas **sem qualquer anotação de α ou β e sem indicação visual de poda** (ramos eliminados, esmaecidos ou tracejados). Isso contradiz tanto a legenda do próprio slide quanto a especificação do Plano de Aula ("traçado do exemplo numérico A/B/C com valores de α e β anotados nos pontos de corte"; "diagrama comparativo Minimax completo × árvore podada por alfa-beta"). O comentário de produção deixado no `slides.md` (nota do apresentador, não visível no PDF/PPTX) já descrevia corretamente o que deveria ser produzido — duas árvores lado a lado, uma completa e outra com os ramos podados, com α/β anotados —, mas a imagem final não corresponde a essa especificação. Como este é o slide central da mecânica de poda (o ponto alto conceitual da semana), a lacuna visual enfraquece exatamente o momento em que os estudantes deveriam visualizar o que é eliminado e por quê.
- **Prioridade:** Alta

**Problema 3**
- **Documento:** Plano de Aula (Semana 11), Encontro 2, Etapa 4 ("Desafio de Escolha Tecnológica do Módulo 4")
- **Local:** Trecho "considerando alternativas e limitações discutidas na Semana 10 (seção 11.7)"
- **Descrição:** A seção 11.7 não aparece em nenhum outro documento do projeto — nem no próprio Plano de Aula da Semana 10 (que cobre 11.1, 11.2, 11.3, 11.3.1–11.3.3, 11.6, 11.8 e 11.9, mas nunca 11.7), nem no Cronograma, nem no Manual do Professor. Como não há acesso direto ao texto da Apostila neste ambiente, não é possível confirmar se 11.7 existe e trata de fato de "alternativas e limitações" do Minimax, ou se é uma citação equivocada (possivelmente destinada a outra seção, ou a um conteúdo que deveria ter sido incluído no Plano da Semana 10 mas não foi). Em qualquer um dos dois casos, o Plano da Semana 11 pede que o professor "retome" uma discussão que os materiais revisados da Semana 10 não registram sob esse número — um risco real de o professor procurar um conteúdo que não está onde o Plano indica.
- **Prioridade:** Média

**Problema 4**
- **Documento:** Cronograma (verificado por referência cruzada; a tabela pertence ao Cronograma, não aos dois documentos revisados desta semana)
- **Local:** Linha "Semana 11" na tabela do Cronograma, campo "Apostila"
- **Descrição:** O Cronograma indica, para a Semana 11, "Apostila: Parte VI, Cap. 13 — Heurísticas e Algoritmos Genéticos (parte de heurísticas de avaliação)" como se este fosse o capítulo principal da semana. Tanto o Plano de Aula quanto os Slides da própria Semana 11 deixam claro que o conteúdo central é a **Parte V, Capítulo 11** (seções 11.3.4 e 11.4/11.4.1), e que o Capítulo 13 (seção 13.1) entra apenas como reforço terminológico secundário — o próprio Plano de Aula chega a dizer explicitamente que o Capítulo 13 "não é concluído nesta semana". Este é o mesmo problema já registrado (Prioridade Baixa) na Revisão da Semana 10, ainda não corrigido; como agora é a própria linha da Semana 11 que está imprecisa (não apenas uma referência cruzada a partir da Semana 10), o risco de um professor consultar só essa tabela e preparar a leitura errada é mais direto.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Ajustar o slide "O que implementar hoje" (e, se possível, a capa) para citar **Conecta 4 Reduzido** como o jogo definido do Micro Game, removendo "damas simplificada" como alternativa equivalente — mantendo qualquer menção a outros jogos apenas como observação para o professor, fora do slide do estudante, como já ocorre no Plano de Aula.
- Substituir a imagem `assets/mermaid-1.png` da Semana 11 por uma versão que efetivamente mostre os valores de α e β anotados nos nós e os ramos podados (esmaecidos ou tracejados), conforme a nota de produção já deixada no próprio `slides.md` — a especificação já existe, falta apenas a produção do artefato correspondente.
- Revisar a citação da seção 11.7 no Plano de Aula da Semana 11: confirmar o número correto junto à Apostila e, caso o conteúdo de "alternativas e limitações do Minimax" não tenha de fato sido coberto na Semana 10, ajustar a referência ou reforçar esse ponto brevemente na retomada da Etapa 1 do Encontro 1 desta semana antes do Desafio.
- Corrigir o campo "Apostila" da linha "Semana 11" no Cronograma para refletir a Parte V, Capítulo 11 como conteúdo principal, citando o Capítulo 13 (seção 13.1) apenas como complemento — mesma correção já sugerida para a Semana 10 e ainda pendente.

---

## Parecer Final

**Pronta com pequenos ajustes.**

**Justificativa:** os fundamentos conceituais e a estrutura pedagógica da Semana 11 estão sólidos — sequência fiel às seções 11.3.4 e 11.4, tempos exatos nos dois encontros, matriz de avaliação idêntica à fonte oficial, e continuidade real com o exemplo numérico e com o ajuste de Micro Game já aplicado ao Plano da Semana 10. Os quatro problemas identificados são localizados e não exigem reestruturação: dois de prioridade Alta (Slides desatualizados quanto ao jogo definido do Micro Game; diagrama sem as anotações de α/β que o próprio material promete), um de prioridade Média (citação de seção da Apostila não verificável nos materiais existentes) e um de prioridade Baixa herdado do Cronograma. Nenhum deles compromete a lógica pedagógica da semana — todos são correções pontuais de conteúdo e de um ativo visual.
