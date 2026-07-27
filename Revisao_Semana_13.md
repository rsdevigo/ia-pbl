# Revisão — Semana 13

**Tema:** Aplicação de Algoritmos Genéticos
**Módulo:** 5 — Como encontrar automaticamente boas soluções? (parte 2, encerramento do módulo e da Unidade V)
**Documentos revisados:** Plano de Aula (Semana 13) e Slides (Semana 13 — `slides.md`, PDF de 30 páginas e PPTX) — não existe Tutorial nesta disciplina (nenhuma semana possui esse artefato, confirmado pelo `_sidebar.md` do projeto e já registrado nas Revisões anteriores); o item de coerência com Tutorial é, portanto, não aplicável.
**Referência de verdade:** Cronograma (linha Semana 13); CLAUDE.md — "Micro Games — Exemplos de Implementação" (Módulo 5: Genetic Lab — Criaturas Evoluídas); `Incrementos_MicroGames.md` (incremento previsto para S13 e estado final do Micro Game 5); Revisao_Semana_12.md (para verificar continuidade das pendências daquela semana).

**Nota metodológica:** como nas Revisões anteriores, a Apostila não está disponível como arquivo neste ambiente de trabalho. A verificação de alinhamento à Apostila foi feita por triangulação entre os números de seção citados no Plano de Aula, nos Slides, no Cronograma e no `Incrementos_MicroGames.md`, e por continuidade com o conteúdo já revisado nas semanas anteriores — não por leitura direta do texto da Apostila. Onde isso limita a confiança de uma constatação, isso é sinalizado explicitamente.

---

## Resumo Geral

A Semana 13 é um material bem estruturado e consistente entre Plano de Aula e Slides: a sequência conceitual (retomada da Semana 12 → problema mais expressivo → convergência e diversidade → aplicações em jogos → ferramentas → vantagens/limitações e comparação com RL → estudos de caso → Micro Game → Desafio de Escolha Tecnológica → Engenharia Reversa → encerramento) é idêntica nos dois documentos, os tempos dos dois encontros fecham exatamente em 90 minutos cada, e o encerramento do Módulo 5 e da Unidade V está corretamente amarrado ao Cronograma (quatro entregas, mesmos pesos). O ponto mais relevante encontrado é uma lacuna de especificidade no próprio Micro Game: tanto o Plano quanto os Slides tratam o "problema mais expressivo" apenas de forma genérica ("ajustar um pequeno conjunto de parâmetros de uma IA de jogo"), sem nunca mencionar o tema fixo "Criaturas Evoluídas" (CLAUDE.md) nem o cenário de locomoção que o próprio `Incrementos_MicroGames.md` já define como o incremento e o estado final oficiais do Micro Game 5 desta semana. Além disso, a figura de apoio à diversidade populacional prevista no Plano ("Materiais... eventual gráfico") nunca foi produzida, permanecendo como nota de produção pendente no `slides.md`, e o slide de estudos de caso não rotula explicitamente cada item como fato documentado ou inferência, ao contrário do slide de Engenharia Reversa que faz exatamente isso. São problemas localizados, que não comprometem a estrutura sólida da semana, mas merecem correção antes da aplicação em turma.

---

## Pontos Fortes

- **Coerência integral entre Plano de Aula e Slides.** As cinco seções de conteúdo do Plano (13.7 a 13.11) aparecem nos Slides na mesma ordem e com os mesmos exemplos (saltos/platôs, cinco famílias de aplicação, três ferramentas, vantagens/limitações, comparação otimizar × aprender a agir, estudos de caso fato/inferência) — nenhum conceito presente em um documento está ausente ou contraditório no outro.
- **Tempos exatos e coerentes com a proposta da semana.** Encontro 1: 10+25+20+20+15 = 90 minutos; Encontro 2: 10+35+10+20+15 = 90 minutos — com peso adequado à natureza da semana (mais prática e de consolidação no Encontro 2, mais teórica no Encontro 1).
- **Encerramento de módulo bem amarrado ao Cronograma.** As quatro entregas (Micro Game 5, AI Design Log, Desafio de Escolha Tecnológica M5, 5º momento de Engenharia Reversa) e seus pesos (50/25/15/10%) aparecem de forma idêntica no Plano e no Cronograma, e a Verificação da Aprendizagem remete corretamente à Rubrica de Avaliação.
- **Tratamento metodológico cuidadoso da Engenharia Reversa.** O Plano reconhece explicitamente que a Apostila não traz estudo de caso de Algoritmos Genéticos no Capítulo 15, orientando o professor a tratar a análise como inferência plausível — e os Slides reforçam isso com o rótulo `[Documentado]`/`[Inferência]` no slide de perguntas de observação, coerente com a seção 13.10.
- **Retomada sem repetição desnecessária.** Tanto o Plano quanto os Slides deixam claro que o vocabulário evolutivo, o ciclo de oito etapas e os operadores genéticos da Semana 12 (seções 13.1 a 13.6) não devem ser reensinados, apenas retomados brevemente — evitando a repetição que o CLAUDE.md pede para evitar.
- **Uso correto dos Exercícios de fixação da Apostila.** O Plano orienta explicitamente o professor a usar Exercícios de fixação, Questões de Revisão e Exercícios de Integração já prontos na Apostila antes de criar questões próprias, coerente com a Filosofia da Disciplina.

---

## Problemas Encontrados

**Problema 1**
- **Documento:** Plano de Aula e Slides (Semana 13)
- **Local:** Plano — "Preparação do Professor" (linha "Cena Unity utilizada") e Encontro 1, etapa 1; Slides — slides "Um problema mais expressivo" e "O que consolidar hoje"
- **Descrição:** O `Incrementos_MicroGames.md` já define, como incremento oficial da S13 e como "Estado final do Micro Game 5", a evolução de forma/parâmetros de uma criatura simples para melhorar sua locomoção — o mesmo tema fixo "Criaturas Evoluídas" registrado no CLAUDE.md ("Micro Games — Exemplos de Implementação", Módulo 5). Nem o Plano de Aula nem os Slides desta semana mencionam "criatura" ou "locomoção" em nenhum momento; ambos tratam o "problema mais expressivo" apenas de forma genérica ("ajustar um pequeno conjunto de parâmetros de uma IA de jogo, ou uma sequência/layout simples", sempre com "por exemplo"). Isso não é uma contradição direta — a redação é aberta o suficiente para comportar o cenário de locomoção — mas deixa o professor sem uma âncora explícita ao tema fixo já decidido pelo projeto, criando risco de que diferentes turmas ou diferentes leituras do Plano implementem Micro Games 5 com temas distintos entre si, o que contraria a busca por consistência entre os artefatos da disciplina.
- **Prioridade:** Média

**Problema 2**
- **Documento:** Slides (Semana 13) — arquivo-fonte `slides.md`
- **Local:** Comentário HTML (nota do apresentador) após o slide "Diagnosticando convergência prematura"
- **Descrição:** O comentário no `slides.md` ainda descreve uma "FIGURA A PRODUZIR" (`assets/convergencia-prematura-vs-diversidade.webp`), contrastando visualmente uma população diversa (exploração) e uma população convergida prematuramente (baixa diversidade). Diferente do resíduo já observado na Semana 12 (onde a imagem final já existia sob outro nome), aqui a imagem realmente não foi produzida: a pasta `assets/` desta semana contém apenas `mermaid-1.png` (a curva de evolução), e nem o PDF nem o PPTX finais trazem o diagrama de diversidade populacional. Como a distinção entre "platô com baixa diversidade" (convergência prematura) e "platô normal" é justamente um dos objetivos de aprendizagem explícitos da semana (objetivo 2 do Plano), a ausência desse apoio visual é uma lacuna de conteúdo, não apenas um resíduo de produção.
- **Prioridade:** Média

**Problema 3**
- **Documento:** Slides (Semana 13)
- **Local:** Slide "O que se sabe e o que se infere" (estudos de caso)
- **Descrição:** O slide lista quatro itens (PCG baseada em busca, competições de IA por evolução/NEAT, balanceamento e ajuste de parâmetros na indústria, neuroevolução em jogos experimentais) sem rotular explicitamente cada um como `[Documentado]` ou `[Inferência]`, embora o próprio título do slide e a seção 13.10 da Apostila peçam essa distinção. O aviso abaixo ("Erro comum: afirmar que um jogo comercial específico 'usa Algoritmos Genéticos'...") ajuda, mas não substitui a classificação item a item. Isso contrasta com o slide de Engenharia Reversa (mais adiante), que já usa corretamente os rótulos `[Documentado]`/`[Inferência]`, mostrando que o padrão existe no material mas não foi aplicado de forma consistente neste slide específico.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Incluir, no Plano de Aula (Encontro 1, etapa 1, e "Cena Unity utilizada") e no slide "Um problema mais expressivo", uma referência explícita ao tema fixo "Criaturas Evoluídas" (evolução de forma/parâmetros para locomoção), mantendo o exemplo de "parâmetros de IA de jogo" apenas como variação secundária ou analogia, para alinhar o material da semana ao que já está decidido no CLAUDE.md e no `Incrementos_MicroGames.md`.
- Produzir o diagrama pendente de diversidade populacional (`assets/convergencia-prematura-vs-diversidade.webp`) descrito no comentário do `slides.md`, ou remover a nota caso o professor opte por não incluir esse apoio visual — mas, dado que o conceito é objetivo de aprendizagem explícito, recomenda-se produzir a figura.
- Adicionar os rótulos `[Documentado]` / `[Inferência]` a cada item do slide "O que se sabe e o que se infere", replicando o padrão já usado no slide de Engenharia Reversa da mesma semana.

---

## Status dos Ajustes

Os três problemas foram corrigidos diretamente nos documentos-fonte:

- **Problema 1 (tema fixo do Micro Game):** o Plano de Aula ("Cena Unity utilizada", Encontro 1 etapa 1, e "Objetivo pedagógico"/"Funcionalidades esperadas" da seção Micro Game) e os Slides (slide "Um problema mais expressivo") agora referenciam explicitamente o tema fixo "Criaturas Evoluídas" — evoluir forma/parâmetros de uma criatura para locomoção —, mantendo o exemplo de parâmetros de IA de jogo apenas como ilustração secundária.
- **Problema 2 (figura de diversidade populacional):** a figura foi produzida (`assets/mermaid-2.png`, painel duplo comparando população diversa/curva com saltos e população convergida/curva em platô longo) e inserida em um novo slide logo após "Diagnosticando convergência prematura", substituindo a nota de produção pendente.
- **Problema 3 (rótulos fato/inferência):** o slide "O que se sabe e o que se infere" agora rotula cada item com `[Documentado]` ou `[Inferência]`, no mesmo padrão já usado no slide de Engenharia Reversa.

**Pendência de build:** o `slides.md` foi atualizado, mas a regeneração de `semana_13_slides.pdf` e `semana_13_slides.pptx` a partir da nova fonte não pôde ser concluída neste ambiente — o download do Chromium necessário para o Marp CLI renderizar os arquivos está bloqueado pela política de rede do sandbox (`storage.googleapis.com` retorna 403). Para atualizar os arquivos finais, execute localmente (com Marp CLI e Chrome/Chromium instalados):

```
marp --theme-set "Slides/themes/academic-course.css" "Slides/Semana 13/slides.md" --pdf --allow-local-files -o "Slides/Semana 13/semana_13_slides.pdf"
marp --theme-set "Slides/themes/academic-course.css" "Slides/Semana 13/slides.md" --pptx --allow-local-files -o "Slides/Semana 13/semana_13_slides.pptx"
```

---

## Parecer Final

**Classificação: Pronta com pequenos ajustes.**

**Justificativa:** a arquitetura da semana é sólida — coerência total entre Plano e Slides, tempos exatos, encerramento de módulo corretamente amarrado ao Cronograma e à Rubrica, e tratamento metodológico cuidadoso da distinção fato/inferência na Engenharia Reversa. Os três problemas encontrados são localizados e não afetam a estrutura geral: a falta de âncora explícita ao tema fixo "Criaturas Evoluídas" é uma lacuna de especificidade que não chega a contradizer o material (a redação genérica ainda comporta o tema correto), a figura pendente de diversidade populacional é uma lacuna de conteúdo de correção relativamente rápida (produção de uma imagem), e a ausência de rótulos no slide de estudos de caso é uma inconsistência menor de padronização visual. Nenhum dos três exige reescrita de conteúdo ou realocação de tempo — todos podem ser corrigidos com ajustes pontuais no Plano e no `slides.md`, sem alterar a sequência didática, os objetivos ou os tempos já bem calibrados da semana.
