# Revisão — Semana 17

**Tema:** Engenharia Reversa integrada e apresentação final do AI Playground
**Unidade:** VII — Projeto Final e Encerramento (semana única, encerramento do semestre)
**Documentos revisados:** Plano de Aula (Semana 17) e Slides (Semana 17 — `slides.md`, PDF e PPTX). Não existe Tutorial nesta disciplina em nenhuma semana (confirmado nas Revisões 01–16); o item de coerência com Tutorial é, portanto, não aplicável.
**Referência de verdade:** Apostila, Parte VII — Capítulo 15 (Estudos de Caso Comentados) e Encerramento da Parte VII, lidos diretamente do repositório-fonte (`rsdevigo.github.io/apostila-ia`, via `raw.githubusercontent.com`); Cronograma (linha Semana 17); CLAUDE.md; Manual do Professor (§ 5.4, § 5.4 "Projeto Integrador Final da Apostila", § 6.5 GOAP); Critérios de Notas (itens 4 e 5); Formulários de Avaliação (Ficha 6).

**Nota metodológica:** ao contrário das Revisões anteriores (01–16), desta vez foi possível ler o texto integral do Capítulo 15 e do Encerramento da Parte VII diretamente do repositório-fonte da Apostila, e não apenas triangular por números de seção. A verificação de alinhamento à Apostila nesta Revisão tem, portanto, confiança mais alta que nas anteriores.

---

## Resumo Geral

A Semana 17 é o encerramento mais bem resolvido do semestre nos dois documentos revisados. Plano de Aula e Slides descrevem exatamente a mesma sequência didática, os mesmos nove estudos de caso do Capítulo 15, o mesmo formato de feira em estações e os mesmos critérios de avaliação (Ficha 6, 20% da nota final). A escolha de *F.E.A.R.* como "caso de contraste" é tecnicamente correta e está ancorada numa decisão pedagógica deliberada e documentada no Manual do Professor (§ 6.5) — não é uma lacuna, é um fechamento proposital do arco GOAP aberto na Semana 1. O dimensionamento de turma (10 a 14 grupos, 4–5 minutos de arguição por grupo) é detalhado e vem com plano de contingência explícito. Os dois problemas encontrados são pontuais: um defeito de formatação na tabela do Encontro 2 do Plano de Aula (prioridade baixa, apenas cosmético) e uma pequena divergência entre os seis objetivos de aprendizagem do Plano e os quatro objetivos listados nos Slides (prioridade baixa). Não foram encontradas inconsistências de conteúdo entre Plano, Slides e Apostila.

---

## Pontos Fortes

- **Fidelidade total ao Capítulo 15 da Apostila.** Os nove estudos de caso (Pac-Man, F.E.A.R., Halo, The Sims, Left 4 Dead, Alien: Isolation, Age of Empires/Civilization, Black & White, The Last of Us) e a tabela-síntese de técnicas por módulo, presentes nos Slides, correspondem exatamente à estrutura e ao conteúdo do capítulo, incluindo a distinção entre técnicas simples com ilusão forte e técnicas complexas com ilusão frágil, tema central da seção 15.10 da Apostila.
- **Uso correto e bem justificado de *F.E.A.R.* como caso de contraste.** O Plano de Aula descreve com precisão o motivo pelo qual GOAP nunca foi ensinado (é conteúdo de aprofundamento, seção 6.6) e por que isso torna *F.E.A.R.* o fechamento metodológico ideal — exatamente a leitura prescrita no Manual do Professor (§ 6.5) e coerente com a Apostila, cuja seção 15.2 também identifica GOAP como "técnica que a turma não estudou" nesse sentido pedagógico.
- **Formato de feira em estações bem dimensionado.** A justificativa para abandonar apresentações seriadas (menos de 5 minutos por grupo para 6 Micro Games e 8 critérios) é clara, e o cálculo de tempo (14 grupos × 4–5 min ≈ 65 dos 70 minutos do Encontro 2) é consistente entre "Preparação do Professor", a etapa 2 do Encontro 2 e o Cronograma.
- **Divergência entre Apostila e disciplina tratada corretamente.** A Apostila propõe, no Encerramento da Parte VII, um "Projeto Integrador Final" próprio (engenharia reversa individual de um jogo novo, com rubrica de seis etapas). A Semana 17 do curso **não** adota esse projeto — decisão explicitamente registrada e justificada no Manual do Professor (§ 5.4: "a disciplina não o adota como instrumento avaliativo próprio, porque o seu Projeto Integrador é o AI Playground"). Como há orientação explícita do professor documentada, isso está de acordo com a regra de Fonte da Verdade do CLAUDE.md, e não configura conflito não resolvido.
- **Consistência numérica de ponta a ponta.** O peso de 20% citado no Plano confere com os Critérios de Notas (itens 4 e 5); a composição da nota (feira + AI Design Log consolidado + acompanhamento contínuo) confere com a Ficha 6 dos Formulários de Avaliação, que já lista os seis Micro Games e os oito critérios integrados.
- **Diagramas dos Slides existem e estão no lugar certo.** `assets/mermaid-1.png` (percurso dos seis módulos) e `assets/mermaid-2.png` (os seis momentos de Engenharia Reversa) estão presentes na pasta de assets da Semana 17, evitando a falha — comum em outras semanas revisadas — de referência a imagem inexistente.
- **Dificuldades esperadas bem calibradas.** A tabela de dificuldades cobre tanto riscos técnicos (integração dos seis Micro Games num único projeto Unity) quanto riscos de avaliação (AI Design Log consolidado como simples justaposição, grupo que só ensaiou um Micro Game), com estratégias de intervenção específicas e não genéricas.

---

## Problemas Encontrados

**Problema 1**
- **Documento:** Plano de Aula (Semana 17)
- **Local:** Seção "Encontro 2 (1h30)", entre a linha de abertura da tabela e a primeira linha de dados
- **Descrição:** O cabeçalho da tabela (`| Etapa | Duração | Objetivo | ... |`) é declarado, mas antes de qualquer linha de dados é interrompido por um bloco de citação (a nota sobre o formato de feira em estações) e, em seguida, o mesmo cabeçalho é repetido uma segunda vez, agora seguido das três linhas reais. Em renderizadores Markdown mais estritos isso produz uma tabela vazia solta antes da nota, seguida da tabela correta — um artefato visual confuso, embora o conteúdo em si esteja correto e completo.
- **Prioridade:** Baixa (defeito cosmético de formatação, não de conteúdo)

**Problema 2**
- **Documento:** Slides (Semana 17), slide "Objetivos da aula"
- **Local:** Comparação com a seção "Objetivos de Aprendizagem" do Plano de Aula
- **Descrição:** O Plano de Aula lista seis objetivos de aprendizagem, incluindo explicitamente "reunir os seis Micro Games... em um único AI Playground funcional" e "consolidar o AI Design Log do semestre". Os Slides resumem os objetivos em apenas quatro marcadores, e nenhum deles menciona diretamente a integração técnica dos Micro Games no projeto Unity nem a consolidação do AI Design Log como objetivo de aprendizagem — embora ambos os temas apareçam mais adiante, no slide "Checklist do AI Playground". Não é uma contradição, mas os Slides não espelham todos os objetivos formais do Plano na abertura da aula.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

Corrigir a formatação da tabela do Encontro 2 no Plano de Aula, movendo o bloco de citação sobre o formato de feira para antes ou depois da tabela única (com um só cabeçalho), eliminaria o artefato de renderização sem alterar nenhum conteúdo. No slide "Objetivos da aula", adicionar um quinto marcador cobrindo a integração dos seis Micro Games e a consolidação do AI Design Log aproximaria os Slides dos seis objetivos completos do Plano, sem tornar o slide de abertura mais denso do que os demais.

---

## Parecer Final

**Pronta para aplicação.**

Os dois documentos revisados desta semana de encerramento estão coerentes entre si, tecnicamente corretos em relação ao Capítulo 15 e ao Encerramento da Parte VII da Apostila, e alinhados aos instrumentos de avaliação (Ficha 6, Critérios de Notas). A divergência mais delicada — o Projeto Integrador Final descrito pela própria Apostila e não adotado pela disciplina — está resolvida por decisão explícita e documentada do professor, conforme previsto na regra de Fonte da Verdade do projeto. Os dois problemas identificados são de baixa prioridade (um defeito cosmético de tabela e uma pequena assimetria entre a lista de objetivos do Plano e a dos Slides) e não comprometem a aplicação da semana em sala.
