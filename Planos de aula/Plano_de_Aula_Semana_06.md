# Plano de Aula — Semana 6

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 6 de 17 |
| **Unidade** | Unidade II — Navegação e Busca de Caminhos (Semanas 5–7) |
| **Módulo** | Módulo 2 — Como um agente encontra seu destino? |
| **Tema** | Busca de Caminhos com A* |
| **Pergunta Norteadora** | Como calcular o melhor caminho entre dois pontos? |
| **Tipo de semana** | 🔵 Semana regular (fundamentação e desenvolvimento do Micro Game) |

---

## Objetivos de Aprendizagem

Ao final da Semana 6, o estudante deverá ser capaz de:

1. **Explicar** por que a busca de Dijkstra é uma busca não-informada e por que essa característica a torna ineficiente para pathfinding em tempo real.
2. **Definir** com precisão os três valores centrais do A* — `g(n)` (custo acumulado, exato), `h(n)` (heurística, estimada) e `f(n) = g(n) + h(n)` — e justificar a regra de expansão pelo menor `f`.
3. **Diferenciar** heurística admissível de heurística consistente, relacionando cada propriedade a uma garantia do algoritmo (otimalidade; dispensa de reprocessamento de nós fechados).
4. **Selecionar** a heurística geométrica adequada (Manhattan, Euclidiana ou Chebyshev/octile) para uma dada conectividade de grade, evitando o erro de superestimar o custo restante.
5. **Descrever** o funcionamento do laço principal do A* — listas aberta e fechada, relaxamento de arestas e reconstrução do caminho por predecessores.
6. **Relacionar** o A* implementado à mão com o serviço equivalente já embutido no NavMesh Agent da Unity, identificando o que a ferramenta resolve internamente.
7. **Evoluir**, em grupo, o Micro Game Navigation, comparando o comportamento de uma implementação própria simplificada de A* com a busca interna já utilizada pelo NavMesh Agent desde a Semana 5.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte III, Capítulo 8 da Apostila — Busca de Caminhos com A***:

- o problema: menor caminho em tempo real, sob a tensão entre otimalidade, velocidade e escalabilidade dentro do orçamento de quadro — seção 8.1;
- busca não-informada: o algoritmo de Dijkstra, sua garantia de otimalidade e sua fraqueza (explorar "cegamente" em todas as direções) — seção 8.2;
- busca informada: a ideia de heurística `h(n)` e a função de avaliação `f(n) = g(n) + h(n)`; os dois casos-limite (`h = 0` → Dijkstra; ignorar `g` → Busca Gulosa) — seção 8.2.1;
- admissibilidade (heurística nunca superestima) e consistência (desigualdade triangular aplicada à heurística), e suas consequências práticas para a otimalidade e para o reprocessamento de nós — seção 8.2.2;
- funcionamento passo a passo: listas aberta (fila de prioridade) e fechada, relaxamento de arestas e reconstrução do caminho via predecessores — seção 8.3.1 e 8.3.3;
- heurísticas comuns — Manhattan (conectividade-4), Euclidiana (movimento livre/NavMesh) e Chebyshev/octile (conectividade-8) — e o recurso do A* ponderado (*weighted A**), que troca otimalidade por velocidade — seção 8.3.2;
- traço de execução do A* contornando um obstáculo, ilustrando exploração eficiente em terreno aberto e mais custosa perto de obstáculos — seção 8.4;
- vantagens (ótimo, completo, geral, eficiente, sintonizável) e limitações (memória por nó, custo com muitos agentes, nós simétricos, recálculo em mundos dinâmicos) — seção 8.5;
- ferramentas: o A* como serviço embutido no NavMesh Agent da Unity, e o A* Pathfinding Project (terceiros) como alternativa para grades e controle direto — seção 8.7.

Não deve ser antecipado o conteúdo do Capítulo 9 (JPS+ e otimizações): a redundância de nós simétricos explorados pelo A* em grades abertas é apenas mencionada como motivação, sem detalhamento das técnicas que a resolvem — essas ficam para a Semana 7. Também não é objetivo desta semana implementar um A* de produção: a implementação própria tem função exclusivamente didática, para tornar visível o que a NavMesh já resolve internamente.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte III, Capítulo 8, completo (seções 8.1 a 8.7) |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com a NavMesh e o NavMesh Agent da Semana 5 já funcionais |
| **Cena Unity utilizada** | A mesma cena do Micro Game Navigation criada na Semana 5 (salas, corredor e obstáculos), reaproveitada para comparar a implementação própria de A* com o NavMesh Agent já configurado |
| **Assets** | Nenhum asset adicional além dos já utilizados na Semana 5; um script de A* simplificado (grade lógica sobreposta à cena, sem geometria adicional) preparado previamente pelo professor como base de demonstração |
| **Exemplos** | Diagrama da função de avaliação `f = g + h` (seção 8.2.1); fluxograma do laço principal do A* com listas aberta e fechada (seção 8.3.1); diagrama comparativo de Manhattan, Euclidiana e Chebyshev/octile (seção 8.3.2); diagrama do traço de execução contornando uma parede (seção 8.4) |
| **Vídeos** | Recomenda-se, opcionalmente, uma visualização animada de A* em grade (por exemplo, um demonstrador de pathfinding em grade) para reforçar visualmente as listas aberta e fechada em movimento |
| **Jogos para Engenharia Reversa** | Não aplicável nesta semana — a Semana 6 não prevê momento de Engenharia Reversa, conforme o Cronograma |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação do algoritmo A* (função heurística, lista aberta/fechada). Demonstração de uma implementação própria simplificada, para tornar visível o que a NavMesh resolve internamente.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 5 min | Conectar a NavMesh da Semana 5 ao problema desta semana | Recapitula que a Semana 5 resolveu a *representação* do espaço (grafo, NavMesh); anuncia que hoje se resolve a *busca* sobre essa representação | Relembram, em voz alta, a correspondência polígono = nó / borda compartilhada = aresta construída na semana anterior |
| 2. O problema: menor caminho em tempo real | 10 min | Apresentar a tensão entre otimalidade, velocidade e escala | Apresenta a seção 8.1: por que a busca ingênua (testar todos os caminhos) é inviável; a tensão entre um caminho ótimo e um caminho rápido o bastante para o orçamento de quadro | Discutem, em duplas, por que um NPC com um desvio absurdo "quebra" a ilusão de inteligência mesmo com IA correta |
| 3. Dijkstra: busca não-informada | 15 min | Explicar a busca de Dijkstra e sua limitação | Apresenta a seção 8.2: a expansão "em mancha" de Dijkstra, sua garantia de otimalidade e o desperdício de explorar em todas as direções sem saber onde fica o destino | Descrevem, com suas palavras, por que Dijkstra é "cego" em relação ao destino |
| 4. Heurística e a função f = g + h | 20 min | Definir g, h e f, e a regra do menor f | Apresenta a seção 8.2.1 com o diagrama de `f = g + h`; explicita os dois casos-limite (`h = 0` → Dijkstra; ignorar `g` → Busca Gulosa) | Calculam, para um exemplo simples de grade fornecido pelo professor, os valores de g, h e f de alguns nós vizinhos à origem |
| 5. Admissibilidade e consistência | 15 min | Explicar as propriedades que garantem a otimalidade | Apresenta a seção 8.2.2: heurística admissível (nunca superestima) e consistente (desigualdade triangular); relaciona a consistência à dispensa de reprocessamento de nós fechados | Identificam se a distância em linha reta, ignorando obstáculos, é admissível, justificando a resposta |
| 6. Listas aberta e fechada, e reconstrução do caminho | 15 min | Explicar o laço principal do algoritmo | Apresenta o fluxograma da seção 8.3.1 (retirar o menor f, expandir vizinhos, relaxar arestas, mover para a fechada) e a reconstrução via predecessores (seção 8.3.3) | Acompanham o fluxograma e apontam, em um traço de execução simples, qual nó seria expandido a cada passo |
| 7. Heurísticas comuns | 5 min | Apresentar Manhattan, Euclidiana e Chebyshev/octile | Apresenta a seção 8.3.2, com a regra prática de casar cada heurística à conectividade da grade (4 direções, 8 direções, movimento livre) | Identificam qual heurística seria adequada à NavMesh do Micro Game Navigation (movimento livre → Euclidiana) |
| 8. Demonstração de implementação própria simplificada | 5 min | Anunciar a demonstração prática do próximo encontro | Anuncia que o Encontro 2 demonstrará uma implementação própria simplificada de A* sobre uma grade lógica, para tornar visível o que a NavMesh resolve internamente, seguida da comparação técnica | Registram dúvidas conceituais para retomada no início do Encontro 2 |

---

## Encontro 2 (1h30)

**Foco:** Evolução do Micro Game Navigation com A*. Discussão técnica comparando a implementação própria com a solução interna da NavMesh.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 5 min | Retomar g, h, f e admissibilidade antes da prática | Conduz uma discussão breve recuperando a função `f = g + h` e a regra do menor f | Respondem perguntas de verificação oral, relacionando cada termo ao que será visto na demonstração |
| 2. Demonstração de A* simplificado | 20 min | Mostrar o algoritmo funcionando, célula a célula | Demonstra, ao vivo, uma implementação própria simplificada de A* sobre uma grade lógica sobreposta à cena de teste, destacando as listas aberta e fechada e o comportamento ao contornar um obstáculo (seção 8.4) | Observam a demonstração e identificam visualmente os nós na lista aberta (fronteira) e na lista fechada (resolvidos) a cada passo |
| 3. Comparação com o NavMesh Agent | 10 min | Relacionar a implementação própria ao serviço interno da Unity | Apresenta a seção 8.7: o A* como serviço embutido no NavMesh Agent, os custos por área como pesos de aresta e os off-mesh links como arestas adicionais; cita o A* Pathfinding Project como alternativa de terceiros para grades | Relacionam cada elemento da implementação própria (nó, aresta, custo) ao componente correspondente já configurado no NavMesh Agent desde a Semana 5 |
| 4. Implementação guiada: evolução do Micro Game Navigation | 30 min | Aplicar o conceito ao Micro Game de cada grupo | Acompanha os grupos na adição de um segundo destino (ou obstáculo móvel) à cena, verificando se o NavMesh Agent recalcula corretamente a rota; orienta os grupos que desejarem a experimentar uma versão mínima de A* próprio sobre uma grade auxiliar simples, para fins comparativos | Testam o NavMesh Agent com um novo obstáculo ou destino, observando o recálculo da rota; grupos que optarem por implementar uma versão mínima de A* comparam seu comportamento ao do NavMesh Agent |
| 5. Discussão técnica | 10 min | Consolidar a comparação entre as duas abordagens | Conduz a discussão: em que cenários vale a pena controlar o A* diretamente (grades, atualização dinâmica intensa) versus confiar na NavMesh; retoma a Boa Prática da seção 8.7 sobre quando reimplementar A* compensa | Argumentam, com base nos critérios apresentados, se o Micro Game Navigation se beneficiaria de controle direto do A* ou se o NavMesh Agent já é suficiente |
| 6. Testes e ajustes | 10 min | Verificar a robustez da navegação evoluída | Circula entre os grupos, verificando se o agente contorna corretamente o novo obstáculo e se a rota recalculada permanece plausível | Ajustam parâmetros ou geometria caso a rota apresente comportamento inesperado (por exemplo, hesitação excessiva ou colisão com o obstáculo) |
| 7. Fechamento e transição | 5 min | Preparar a ponte para a Semana 7 | Recapitula a relação entre a implementação própria e o NavMesh Agent, e anuncia que a Semana 7 apresentará o JPS+ como otimização do A* em grandes escalas, encerrando o Módulo 2 | Registram dúvidas e organizam-se para a leitura prévia do Capítulo 9 |

---

## Micro Game

**Micro Game em desenvolvimento:** Navigation (Módulo 2) — **evolução**.

**Objetivo pedagógico:** tornar visível, por meio de uma implementação própria simplificada, o algoritmo que já roda internamente no NavMesh Agent desde a Semana 5, consolidando a compreensão de como o A* calcula o melhor caminho entre dois pontos.

**Funcionalidades esperadas ao final da Semana 6:**

- a cena do Micro Game Navigation evoluída com um novo destino ou obstáculo, exigindo recálculo de rota pelo NavMesh Agent;
- capacidade do grupo de explicar, célula a célula, como uma implementação simplificada de A* chegaria ao mesmo resultado que o NavMesh Agent já produz;
- (opcional) uma versão mínima de A* implementada sobre uma grade lógica auxiliar, para comparação direta com a NavMesh;
- capacidade do grupo de justificar, com critérios técnicos, quando controlar o A* diretamente compensaria em relação a usar o NavMesh Agent.

**Relação com módulos anteriores:** dá continuidade direta ao Micro Game Navigation iniciado na Semana 5, abrindo a "caixa-preta" da busca interna do NavMesh Agent. Reaproveita a cena, a NavMesh e o agente já configurados, sem introduzir novas mecânicas — o foco permanece exclusivamente na compreensão do algoritmo de busca.

---

## Engenharia Reversa

Não há momento de Engenharia Reversa previsto para a Semana 6, conforme o Cronograma — o segundo momento formal da disciplina está previsto para a Semana 7, ao final do Módulo 2.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **AI Navigation / NavMesh Agent** (oficial) | Reutilizado da Semana 5; agora compreendido como executor de uma busca da família A* sobre o grafo de polígonos da NavMesh |
| **Implementação própria de A*** | Script simplificado, demonstrado pelo professor e opcionalmente experimentado pelos grupos, sobre uma grade lógica auxiliar, com finalidade exclusivamente didática |
| **A\* Pathfinding Project** (terceiros) | Citado apenas como alternativa para cenários baseados em grade ou que exigem controle direto do algoritmo, sem uso prático nesta semana |

---

## Atividade de Laboratório

**Objetivo:** evoluir o Micro Game Navigation adicionando um novo destino ou obstáculo, verificando o recálculo de rota pelo NavMesh Agent, e relacionar esse comportamento ao funcionamento do A* estudado na teoria.

**Etapas:**

1. Na cena do Micro Game Navigation (Semana 5), adicionar um novo destino ou um obstáculo dinâmico próximo à rota original.
2. Testar o deslocamento do NavMesh Agent, observando se a rota é recalculada corretamente ao redor do novo obstáculo.
3. Em grupo, descrever verbalmente como um A* rodando sobre o grafo de polígonos chegaria à mesma rota, identificando o papel de g, h e f em pelo menos dois nós do caminho.
4. (Opcional, para grupos com tempo disponível) implementar uma versão mínima de A* sobre uma grade lógica auxiliar simples, comparando seu resultado ao do NavMesh Agent.
5. Registrar, por escrito, em que situação o grupo optaria por controlar o A* diretamente em vez de usar o NavMesh Agent.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter o Micro Game Navigation evoluído com um novo obstáculo ou destino, com o NavMesh Agent recalculando a rota corretamente, e deve ser capaz de explicar essa rota em termos de g, h e f.

---

## Verificação da Aprendizagem

O Módulo 2 se encerra formalmente apenas na Semana 7, quando ocorrem o Desafio de Escolha Tecnológica, o AI Design Log e a Engenharia Reversa do módulo. A verificação nesta semana é, portanto, **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes definem corretamente g, h, f e distinguem admissibilidade de consistência (critério **Compreensão Conceitual** da Rubrica);
- observação da demonstração e da discussão do Encontro 2, verificando se os grupos relacionam corretamente a implementação própria ao NavMesh Agent (indício inicial do critério **Uso da Unity e do Ecossistema**);
- observação da implementação guiada, verificando se o recálculo de rota ocorre corretamente após a adição do novo obstáculo (indício adicional do critério **Aplicação Prática**, formalmente avaliado na consolidação do Micro Game na Semana 7);
- qualidade do argumento apresentado na discussão técnica sobre quando controlar o A* diretamente compensaria (indício inicial do critério **Tomada de Decisão**, central no Desafio de Escolha Tecnológica da Semana 7).

Nenhuma nota é atribuída nesta semana, conforme os Critérios de Notas da disciplina, que vinculam a composição da nota aos módulos encerrados nas Semanas 4, 7, 9, 11, 13 e 16, ao checkpoint da Semana 8 e à apresentação final da Semana 17.

---

## Entregas

Não há entrega formal prevista para a Semana 6, conforme o Cronograma.

A evolução do Micro Game Navigation implementada nesta semana permanece com os grupos para consolidação na Semana 7, quando o Micro Game passa a compor as entregas do Módulo 2 (Desafio de Escolha Tecnológica, AI Design Log e Engenharia Reversa), já incorporando também as otimizações de JPS+ apresentadas naquela semana.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir `g(n)` (exato, já pago) com `h(n)` (estimado, ainda não pago), tratando ambos como "custos conhecidos" | Retomar o diagrama da seção 8.2.1 e pedir que o grupo classifique, para um exemplo concreto, qual valor já foi "pago" e qual é apenas um palpite |
| Achar que a heurística "decide o caminho" em vez de apenas ordenar a exploração | Retomar o Erro Comum da seção 8.2, reforçando que uma heurística imperfeita (mas admissível) ainda leva ao caminho ótimo — apenas explora mais ou menos nós |
| Usar a heurística de Manhattan em uma grade de conectividade-8 (ou Euclidiana quando Chebyshev/octile seria mais adequada), sem perceber o efeito sobre admissibilidade ou eficiência | Retomar o Erro Comum da seção 8.3.2 e pedir que o grupo calcule manualmente `h` com duas heurísticas diferentes para o mesmo par de nós, comparando os resultados |
| Confundir "nós explorados" (aberta + fechada) com "caminho final", achando que tudo o que o A* toca faz parte da rota devolvida | Retomar a Boa Prática da seção 8.3.3, separando explicitamente os três produtos de uma busca: nós explorados, predecessores e caminho final reconstruído |
| Não perceber que o NavMesh Agent já executa um A* internamente, tratando-o como uma "caixa mágica" sem relação com a teoria estudada | Retomar a seção 8.7, relacionando explicitamente cada componente já configurado na Semana 5 (NavMesh Areas, off-mesh links) aos elementos de g, h e f estudados nesta semana |

---

## Preparação para a Próxima Semana

Para a Semana 7 (JPS+ e Otimizações, encerramento do Módulo 2), o professor deve:

- solicitar a leitura prévia do Capítulo 9 da Apostila (JPS+ e Otimizações);
- garantir que todos os grupos possuam, ao final da Semana 6, o Micro Game Navigation evoluído, com o NavMesh Agent recalculando rotas corretamente diante de obstáculos ou destinos adicionais;
- preparar previamente uma comparação de desempenho entre A* e JPS+ em uma grade ampla, a ser demonstrada na Semana 7, e revisar os critérios do Desafio de Escolha Tecnológica do Módulo 2, já que a Semana 7 encerra o módulo com Desafio, AI Design Log e Engenharia Reversa;
- não é necessária nenhuma instalação ou configuração adicional de ferramentas: a Semana 7 dá continuidade ao uso do pacote AI Navigation já consolidado, complementado pela discussão comparativa com o A* Pathfinding Project (seção 7.5/8.7).
