# Revisão — Semana 14

**Tema:** Fundamentos de Aprendizagem por Reforço
**Módulo:** 6 — Como um agente aprende? (parte 1, abertura da Unidade VI)
**Documentos revisados:** Plano de Aula (Semana 14) e Slides (Semana 14 — `slides.md`, PDF e PPTX) — não existe Tutorial nesta disciplina (nenhuma semana possui esse artefato, confirmado pelo `_sidebar.md` do projeto e já registrado nas Revisões anteriores); o item de coerência com Tutorial é, portanto, não aplicável.
**Referência de verdade:** Cronograma (linha Semana 14); CLAUDE.md — "Micro Games — Exemplos de Implementação" (Módulo 6: Adaptive AI — Coletor de Recompensas); `Incrementos_MicroGames.md` (incremento previsto para S14); Manual do Professor (seção sobre ML-Agents/Sentis, referência à Semana 14).

**Nota metodológica:** como nas Revisões anteriores, a Apostila não está disponível como arquivo neste ambiente de trabalho (é mantida em repositório externo). A verificação de alinhamento à Apostila foi feita por triangulação entre os números de seção citados no Plano de Aula, nos Slides e no Cronograma, e por continuidade com o conteúdo já revisado nas semanas anteriores — não por leitura direta do texto da Apostila. Onde isso limita a confiança de uma constatação, isso é sinalizado explicitamente.

---

## Resumo Geral

A Semana 14 abre o Módulo 6 com uma estrutura conceitualmente sólida: a sequência (problema da RL → vocabulário fundamental → exploração/exploitation e ciclo de aprendizagem → MDP e propriedade de Markov → V(s)/Q(s,a) → ML-Agents apenas como contextualização → planejamento do Micro Game) é idêntica no Plano e nos Slides, os tempos dos dois encontros fecham exatamente em 90 minutos, e a sequência didática da disciplina é respeitada com cuidado — os fundamentos matemáticos e conceituais do Encontro 1 vêm antes de qualquer menção ao ML-Agents, e o próprio ML-Agents é apresentado apenas como ferramenta, sem nenhuma configuração ou treinamento. O ponto mais relevante encontrado é uma lacuna de coerência entre o Plano e os Slides: o Plano trata a escrita do esqueleto do script `Agent` em C# como um resultado essencial da semana (com um quadro de justificativa dedicado, "Por que antecipar o esqueleto do script"), mas esse item não aparece em nenhum slide nem na própria lista de "Funcionalidades esperadas" do Plano, criando risco de que o professor ou os estudantes tratem esse passo como opcional. Há também, como nas semanas anteriores do semestre, ausência do tema fixo do Micro Game ("Coletor de Recompensas") no Plano e nos Slides, e uma pequena inconsistência textual sobre o alcance do conteúdo (seção 12.6) dentro do próprio Plano. São problemas localizados, que não comprometem a estrutura geral da semana, mas merecem correção antes da aplicação em turma.

---

## Pontos Fortes

- **Coerência integral entre Plano de Aula e Slides.** A sequência de seis blocos conceituais (problema da RL, vocabulário, exploração/exploitation e ciclo, MDP, função valor, ML-Agents como contextualização) e o planejamento do Micro Game aparecem nos Slides na mesma ordem e com os mesmos exemplos (CoastRunners, diagrama do laço agente–ambiente, paralelo com Minimax e mapa de influência), sem conceitos ausentes ou contraditórios entre os dois documentos.
- **Sequência didática exemplarmente respeitada.** Todo o Encontro 1 é dedicado a fundamentos (vocabulário, MDP, função valor) sem qualquer menção a ferramentas; o ML-Agents só aparece no Encontro 2, explicitamente rotulado como "contextualização de ferramenta" e sem configuração ou treinamento — coerente com a Filosofia da Disciplina ("nunca apresentar ferramentas antes dos conceitos").
- **Tempos exatos.** Encontro 1: 15+25+20+15+15 = 90 minutos; Encontro 2: 10+15+40+15+10 = 90 minutos.
- **Continuidade sem repetição desnecessária.** O paralelo entre Q(s, a), a função de avaliação do Minimax (Módulo 4) e o mapa de influência (Módulo 3) é retomado tanto no Plano quanto nos Slides para ancorar um conceito novo em conhecimento já consolidado, sem reensinar os módulos anteriores.
- **Tratamento cuidadoso de armadilhas conceituais típicas de RL.** Reward hacking (CoastRunners), a propriedade de Markov como hipótese de projeto (não garantia automática) e o dilema exploração/exploitation aparecem de forma consistente no Plano, nos Slides e na tabela de "Dificuldades Esperadas", com estratégias de intervenção específicas para cada uma.
- **Recomendação de infraestrutura bem amarrada entre documentos.** A orientação de antecipar a instalação do ambiente ML-Agents (Python e pacotes) aparece de forma consistente no Cronograma, no Plano de Aula e no Manual do Professor, que inclusive recomenda testar a instalação completa antes da Semana 14 — mostrando que a recomendação foi pensada de forma operacional, não apenas declarada.

---

## Problemas Encontrados

**Problema 1**
- **Documento:** Plano de Aula (Semana 14) e Slides (Semana 14)
- **Local:** Plano — seção "Micro Game" ("Funcionalidades esperadas ao final da Semana 14"); Slides — nenhum slide
- **Descrição:** A "Atividade de Laboratório" do Plano lista, como etapa 6, "Escrever o esqueleto do script de `Agent` em C#" e dedica um quadro de justificativa inteiro a esse passo ("Por que antecipar o esqueleto do script"), afirmando que ele reduz "substancialmente o risco de grupos chegarem à Semana 16 sem modelo próprio". No entanto: (a) esse item não aparece na lista de "Funcionalidades esperadas ao final da Semana 14" da própria seção "Micro Game" do Plano, que menciona apenas cenário montado, definição escrita de estado/ações/recompensa e ausência de treinamento; (b) nenhum slide menciona a escrita do script — nem o slide "O que planejar hoje", nem "Cenário mínimo na Unity", nem o "Resumo da semana" final. Como os Slides são o material que efetivamente acompanha a aula, essa ausência cria risco real de que o passo mais crítico para a viabilidade da Semana 15 (segundo o próprio Plano) seja esquecido ou tratado como opcional.
- **Prioridade:** Alta

**Problema 2**
- **Documento:** Plano de Aula e Slides (Semana 14)
- **Local:** Plano — "Preparação do Professor" (linha "Cena Unity utilizada"), Encontro 2 (etapa 3) e "Atividade de Laboratório" (etapa 1); Slides — slide "Cenário mínimo na Unity"
- **Descrição:** O CLAUDE.md ("Micro Games — Exemplos de Implementação", Módulo 6) e o `Incrementos_MicroGames.md` (linha do incremento de S14) definem o tema fixo do Micro Game 6 como "Coletor de Recompensas": um agente que aprende a coletar itens positivos e evitar itens negativos no ambiente, com a cena descrita como "elementos primitivos... representando itens positivos/negativos". Nem o Plano nem os Slides desta semana mencionam esse tema ou "itens positivos/negativos" em nenhum momento; ambos tratam o problema do Adaptive AI apenas de forma genérica ("alcançar um alvo, desviar de obstáculos, equilibrar-se ou manter-se em uma área"), sempre com "por exemplo". Este é o mesmo padrão de lacuna de especificidade já identificado nas Revisões das Semanas 12 e 13 para os Micro Games 5 e 4 — a redação é aberta o suficiente para comportar o tema correto, mas não ancora explicitamente o professor à decisão já registrada no projeto.
- **Prioridade:** Média

**Problema 3**
- **Documento:** Plano de Aula (Semana 14)
- **Local:** Seção "Conteúdos", primeira frase, versus "Preparação do Professor" (linha "Leitura recomendada") e o restante da própria seção "Conteúdos"
- **Descrição:** A frase de abertura da seção "Conteúdos" afirma que o conteúdo da semana corresponde às "seções 12.1 a 12.6" da Apostila, mas o parágrafo seguinte, na mesma seção, afirma explicitamente que "Não deve ser antecipado o Q-Learning (seção 12.6) em profundidade algorítmica... reservado para a Semana 15", e a "Preparação do Professor" lista a leitura obrigatória como "seções 12.1 a 12.5". Os Slides usam corretamente "12.1 a 12.5, e 12.9 como contextualização" na capa. Trata-se de uma inconsistência textual interna ao próprio Plano — o alcance de conteúdo efetivamente ensinado está correto e é consistente com os Slides, mas a frase de abertura contradiz o restante do documento.
- **Prioridade:** Baixa

**Problema 4**
- **Documento:** Plano de Aula (Semana 14) — Encontro 2, etapa 3, e "Atividade de Laboratório"
- **Local:** Tabela do Encontro 2, etapa "Laboratório — planejamento e esqueleto do Micro Game Adaptive AI" (40 min)
- **Descrição:** Segundo a "Atividade de Laboratório", os 40 minutos dessa etapa devem cobrir: escolha do problema em grupo, definição do estado (com verificação da propriedade de Markov), definição do espaço de ações, definição da função de recompensa (evitando reward hacking), montagem do cenário mínimo na Unity e escrita do esqueleto do script `Agent` em C# com três métodos (observações, ações, recompensa). Mesmo sendo um esqueleto conceitual, sem lógica de treinamento, esse volume de decisões e produção (quatro definições conceituais + montagem de cena + escrita de código) em 40 minutos por grupo é ambicioso, especialmente para estudantes que ainda não manipularam a API do ML-Agents. O Plano não prevê nenhuma válvula de escape caso um grupo não conclua a etapa a tempo da discussão técnica (etapa 4, 15 min).
- **Prioridade:** Média

---

## Sugestões de Melhoria

- Adicionar, em pelo menos um slide (por exemplo, um novo slide após "Cenário mínimo na Unity" ou uma expansão de "O que planejar hoje"), a menção explícita à escrita do esqueleto do script `Agent` em C#, e incluir esse item na lista de "Funcionalidades esperadas ao final da Semana 14" do Plano — tornando visível para professor e estudantes o mesmo passo que o próprio Plano já trata como crítico para a Semana 15.
- Incluir, no Plano de Aula (linha "Cena Unity utilizada" e "Atividade de Laboratório", etapa 1) e no slide "Cenário mínimo na Unity", uma referência explícita ao tema fixo "Coletor de Recompensas" (itens positivos/negativos), mantendo os demais exemplos (alvo, obstáculos, equilíbrio) como variações secundárias, seguindo o mesmo ajuste já sugerido nas Revisões das Semanas 12 e 13 para os respectivos Micro Games.
- Corrigir a frase de abertura da seção "Conteúdos" do Plano, trocando "seções 12.1 a 12.6" por "seções 12.1 a 12.5", para eliminar a contradição com o restante do próprio parágrafo, com a "Preparação do Professor" e com os Slides.
- Revisar a distribuição de tempo da etapa de Laboratório do Encontro 2: considerar reduzir em alguns minutos a etapa 2 ("Apresentação do ML-Agents", 15 min, que é majoritariamente expositiva) em favor da etapa 3, ou orientar explicitamente no Plano que grupos que não concluam o esqueleto do script a tempo podem finalizá-lo como tarefa antes da Semana 15, sem prejuízo à apresentação na discussão técnica.

---

## Status dos Ajustes

Os quatro problemas foram corrigidos diretamente nos documentos-fonte:

- **Problema 1 (esqueleto do script ausente dos Slides e da lista de entregáveis):** o Plano ("Funcionalidades esperadas", "Foco" do Encontro 2 e etapa 3 da tabela) agora lista explicitamente o esqueleto do script `Agent` como entregável da semana; os Slides ganharam um novo slide dedicado ("Esqueleto do script `Agent` em C#") e o "Resumo da semana" passou a mencioná-lo.
- **Problema 2 (tema fixo "Coletor de Recompensas" ausente):** o Plano ("Cena Unity utilizada", "Atividade de Laboratório" etapa 1, etapa 3 da tabela do Encontro 2) e os Slides (capa, slide "Cenário mínimo na Unity") agora referenciam explicitamente o tema fixo — um agente que aprende a coletar itens positivos e evitar itens negativos —, mantendo os demais exemplos (alvo, obstáculos, equilíbrio) apenas como ilustração secundária.
- **Problema 3 (contradição sobre o alcance da seção 12.6):** a frase de abertura da seção "Conteúdos" do Plano foi corrigida de "seções 12.1 a 12.6" para "seções 12.1 a 12.5", alinhando com o restante do documento e com os Slides.
- **Problema 4 (risco de tempo na etapa de Laboratório):** a etapa 3 do Encontro 2 foi ampliada de 40 para 45 minutos (compensada pela redução da etapa 2, de 15 para 10 minutos, que era majoritariamente expositiva), e foi adicionada uma nota no Plano orientando que grupos mais lentos podem concluir o esqueleto do script fora da aula, desde que o planejamento conceitual já esteja validado na discussão técnica.

**Pendência de build:** o `slides.md` foi atualizado, mas a regeneração de `semana_14_slides.pdf` e `semana_14_slides.pptx` a partir da nova fonte não pôde ser concluída neste ambiente — o download do Chromium necessário para o Marp CLI renderizar os arquivos está bloqueado pela política de rede do sandbox (mesma limitação já registrada na Revisão da Semana 13). Para atualizar os arquivos finais, execute localmente (com Marp CLI e Chrome/Chromium instalados):

```
marp --theme-set "Slides/themes/academic-course.css" "Slides/Semana 14/slides.md" --pdf --allow-local-files -o "Slides/Semana 14/semana_14_slides.pdf"
marp --theme-set "Slides/themes/academic-course.css" "Slides/Semana 14/slides.md" --pptx --allow-local-files -o "Slides/Semana 14/semana_14_slides.pptx"
```

---

## Parecer Final

**Classificação: Pronta com pequenos ajustes.**

**Justificativa:** a arquitetura da semana é sólida — coerência conceitual completa entre Plano e Slides, tempos exatos, e um cuidado didático notável em manter os fundamentos matemáticos e o vocabulário de RL inteiramente separados de qualquer configuração de ferramenta, o que está diretamente alinhado à Filosofia da Disciplina. Os quatro problemas encontrados são localizados: a ausência do esqueleto do script nos Slides e na lista de entregáveis do Plano (Problema 1, prioridade Alta) é a mais relevante, pois afeta o que efetivamente chega aos estudantes em aula, mas sua correção é uma adição pontual de conteúdo — um slide e um item de lista —, não uma reestruturação da semana. A falta de âncora ao tema fixo "Coletor de Recompensas" (Problema 2) repete um padrão já mapeado e corrigido em semanas anteriores, a inconsistência sobre o alcance da seção 12.6 (Problema 3) é um erro de redação sem impacto no conteúdo efetivamente ensinado, e o risco de tempo na etapa de Laboratório (Problema 4) é mitigável com um ajuste fino na distribuição dos 90 minutos do Encontro 2. Nenhum dos quatro exige alterar a sequência didática, os objetivos de aprendizagem ou a arquitetura geral da semana.
