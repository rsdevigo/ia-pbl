# Revisão — Semana 12

**Tema:** Fundamentos de Algoritmos Genéticos
**Módulo:** 5 — Como encontrar automaticamente boas soluções? (parte 1, abertura do módulo e da Unidade V)
**Documentos revisados:** Plano de Aula (Semana 12) e Slides (Semana 12 — `slides.md`, PDF e PPTX) — não existe Tutorial nesta disciplina (nenhuma semana possui esse artefato, confirmado pelo `_sidebar.md` do projeto); o item de coerência com Tutorial é, portanto, não aplicável, como já registrado nas Revisões anteriores.
**Referência de verdade:** Cronograma (linha Semana 12 e notas da Unidade V); CLAUDE.md — "Micro Games — Exemplos de Implementação" (Módulo 5: Genetic Lab — Criaturas Evoluídas); `Incrementos_MicroGames.md` (incremento previsto para S12 e estado final do Micro Game 5); Plano de Aula e Slides da Semana 13 (para verificar a continuidade do Micro Game); Revisao_Semana_11.md (para verificar se pendências daquela semana afetam esta).

**Nota metodológica:** como nas Revisões anteriores, a Apostila não está disponível como arquivo neste ambiente de trabalho, e o link `https://rsdevigo.github.io/apostila-ia` é uma aplicação renderizada em JavaScript que não pôde ser lida diretamente (a extensão Claude in Chrome não estava conectada nesta sessão). A verificação de alinhamento à Apostila foi feita por triangulação entre os números de seção citados no Plano de Aula, nos Slides, no Cronograma e no `Incrementos_MicroGames.md`, e por continuidade com o conteúdo já revisado nas semanas anteriores — não por leitura direta do texto da Apostila. Onde isso limita a confiança de uma constatação, isso é sinalizado explicitamente.

---

## Resumo Geral

A Semana 12 é o material mais coerente revisado até aqui entre Plano de Aula e Slides: a sequência conceitual (explosão combinatória → otimização heurística → otimizar × aprender a agir → vocabulário evolutivo → ciclo de oito etapas → representação → função de aptidão → operadores genéticos → ferramentas → Micro Game) é idêntica nos dois documentos, os tempos dos dois encontros fecham exatamente em 90 minutos cada, e o uso do problema simplificado "OneMax" (aproximar uma string-alvo) como ponto de partida do Micro Game Genetic Lab — em vez do tema fixo "Criaturas Evoluídas" do CLAUDE.md — está devidamente amparado pelo `Incrementos_MicroGames.md`, que documenta esse mesmo problema simples como incremento da Semana 12 e reserva a evolução de forma/parâmetros de uma criatura para locomoção como estado final do módulo na Semana 13. Não há, portanto, um problema de coerência ali, apenas um andaime pedagógico que se resolve no material da semana seguinte.

O ponto fraco real da semana está em um único artefato visual: o diagrama "Crossover de um ponto" (`assets/mermaid-3.png`, usado tanto no PDF quanto no PPTX) mostra as setas de cruzamento corretamente cruzadas entre os pais, mas rotula o Filho 1 com o cromossomo do Pai 1 sem nenhuma troca de material genético — um erro de conteúdo que contradiz visualmente a própria mecânica que o slide deveria demonstrar. Como este é o único slide de traçado manual de crossover na semana (e o Plano de Aula, na "Preparação do Professor", promete exatamente esse traçado como um dos três exemplos centrais da aula), o problema atinge diretamente um dos poucos suportes visuais da fundamentação teórica. Além disso, um bullet dos Slides mistura inglês e português ("Aprende through tentativa e recompensa"), contrariando a exigência de português brasileiro do CLAUDE.md. São problemas localizados e de correção rápida, que não comprometem a estrutura geral, sólida, do material desta semana.

---

## Pontos Fortes

- **Coerência integral entre Plano de Aula e Slides.** As nove seções de conteúdo do Plano (13.1 a 13.6) aparecem nos Slides na mesma ordem, com os mesmos exemplos (ajuste de parâmetros de uma IA inimiga; "OneMax"; crossover de um ponto; taxa de mutação entre 0,1% e 5%; elitismo entre 1% e 5%) — nenhum conceito presente em um documento está ausente ou contraditório no outro.
- **Andaime pedagógico do Micro Game bem documentado.** O uso do problema "OneMax" nesta semana, em vez do tema fixo "Criaturas Evoluídas" do CLAUDE.md, não é uma inconsistência: o `Incrementos_MicroGames.md` já prevê esse problema simples como o incremento da Semana 12 e registra explicitamente que "Estado final do Micro Game 5: AG evoluindo forma/parâmetros de uma criatura simples para melhor locomoção" — a transição ocorre no Plano da Semana 13, que já fala em abandonar o "OneMax" por um "problema mais expressivo". A escolha é rastreável e coerente com o restante do projeto.
- **Tempos exatos e bem equilibrados.** Encontro 1: 10+10+20+20+15+15 = 90 minutos; Encontro 2: 10+25+40+10+5 = 90 minutos — com boa proporção entre fundamentação (Encontro 1, quase todo teórico) e prática (Encontro 2, com 40 dos 90 minutos dedicados à implementação guiada).
- **Tratamento correto da retomada de conceitos.** O Plano e os Slides recuperam de forma precisa a explosão combinatória do Minimax (Módulo 4) e o sentido de heurística do A* (Módulo 2), mas evitam a armadilha de igualar Algoritmo Genético a Minimax ou a Aprendizagem por Reforço — em ambos os casos há um quadro de "Erro Comum" explícito que separa os conceitos, em vez de deixar a analogia motivacional se transformar em confusão.
- **Fechamento de abertura de módulo bem construído.** Tanto o Plano quanto o slide de resumo e o slide de preparação para a Semana 13 deixam claro que não há entrega nesta semana, que o Módulo 5 só é avaliado na Semana 13, e que as seções 13.7 a 13.11 não devem ser antecipadas — coerente com o Cronograma.
- **Consistência de escopo do Micro Game.** A "Atividade de Laboratório" e o slide "O que implementar hoje" listam exatamente os mesmos quatro entregáveis técnicos (população inicial, função de aptidão, quatro operadores, registro de aptidão ao longo das gerações), sem acréscimo de mecânicas que desviem do foco em IA, conforme a filosofia de Micro Games do CLAUDE.md.

---

## Problemas Encontrados

**Problema 1**
- **Documento:** Slides (Semana 12)
- **Local:** Slide "Crossover de um ponto" — imagem `assets/mermaid-3.png` (usada tanto no PDF quanto no PPTX)
- **Descrição:** O diagrama mostra Pai 1 = "A B C / D E" e Pai 2 = "F G H / I J", com um ponto de corte após a terceira posição. As setas do diagrama cruzam corretamente entre os pais (sugerindo a troca de segmentos), mas o rótulo do Filho 1 aparece como "A B C D E" — ou seja, o próprio cromossomo do Pai 1, sem nenhuma troca de material genético com o Pai 2. O correto, para um crossover de um ponto nesse corte, seria Filho 1 = "A B C I J" (segmento inicial do Pai 1 + segmento final do Pai 2); o Filho 2 = "F G H D E" está correto. Como este é o único slide de traçado manual de crossover da semana, e a "Preparação do Professor" do Plano de Aula promete esse traçado como um dos três exemplos centrais da aula, o erro atinge diretamente a demonstração central do conceito de crossover, arriscando ensinar a mecânica errada.
- **Prioridade:** Alta

**Problema 2**
- **Documento:** Slides (Semana 12)
- **Local:** Slide "Otimizar × aprender a agir", linha "Avalia soluções prontas / Aprende through tentativa e recompensa"
- **Descrição:** A palavra em inglês "through" aparece no meio de uma frase em português, contrariando a exigência de português brasileiro em toda a produção de materiais (CLAUDE.md, "Produção dos Materiais"). O texto correto seria algo como "Aprende por tentativa e recompensa" ou "Aprende por tentativa e erro".
- **Prioridade:** Baixa

**Problema 3**
- **Documento:** Slides (Semana 12) — arquivo-fonte `slides.md`
- **Local:** Comentário HTML (nota do apresentador) no slide "Anatomia de uma população"
- **Descrição:** O comentário deixado no `slides.md` ainda trata o diagrama como "FIGURA A PRODUZIR", sugerindo um arquivo `assets/anatomia-populacao-genetica.webp` que nunca foi criado — mas o slide já referencia e exibe uma imagem finalizada e correta (`assets/mermaid-1.png`), com o diagrama hierárquico população → indivíduos → cromossomo → genes/aptidão plenamente produzido. A nota é apenas um resquício de uma etapa de produção já concluída; não aparece no PDF nem no PPTX finais e não afeta o material entregue ao estudante, mas pode confundir quem futuramente editar o `slides.md` supondo que a figura ainda esteja pendente.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Corrigir `assets/mermaid-3.png` (ou regenerar o diagrama de origem) para que o Filho 1 exiba "A B C I J", mantendo o Filho 2 como "F G H D E" — alinhando o rótulo às setas cruzadas já corretas na imagem.
- Corrigir a linha "Aprende through tentativa e recompensa" no slide "Otimizar × aprender a agir" para português ("Aprende por tentativa e recompensa").
- Remover ou atualizar o comentário "FIGURA A PRODUZIR" remanescente no `slides.md`, já que a imagem correspondente foi produzida sob outro nome de arquivo.

---

## Parecer Final

**Pronta com pequenos ajustes.**

Justificativa: a estrutura pedagógica da semana (sequência, tempos, coerência entre Plano de Aula e Slides, escopo do Micro Game e alinhamento ao Cronograma e ao `Incrementos_MicroGames.md`) está sólida e não exige reestruturação. O único problema de prioridade alta é um erro de conteúdo isolado em uma única imagem (o rótulo do Filho 1 no diagrama de crossover), com correção pontual e rápida; os demais problemas são cosméticos (uma palavra em inglês) ou internos ao arquivo-fonte (nota de produção desatualizada, sem efeito no material entregue). Corrigido o diagrama de crossover, a semana está pronta para aplicação em sala.
