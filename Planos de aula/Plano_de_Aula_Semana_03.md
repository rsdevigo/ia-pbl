# Plano de Aula — Semana 3

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 3 de 17 |
| **Unidade** | Unidade I — Fundamentos e Decisão de NPCs (Semanas 1–4) |
| **Módulo** | Módulo 1 — Como um NPC decide o que fazer? |
| **Tema** | Aprofundamento da FSM — o padrão de projeto State em C# |
| **Pergunta Norteadora** | Como estruturar o código de uma FSM para que ela cresça sem virar um emaranhado de condicionais? |
| **Tipo de semana** | 🔵 Regular (fundamentação e desenvolvimento do Micro Game) |

---

## Objetivos de Aprendizagem

Ao final da Semana 3, o estudante deverá ser capaz de:

1. **Explicar** o problema que motiva o padrão State — a implementação por `enum`/`switch` concentra toda a lógica de todos os estados em um único método, que cresce e se torna difícil de ler e de testar à medida que estados são adicionados.
2. **Descrever** com precisão a estrutura do padrão de projeto State (GoF): uma interface ou classe base comum a todos os estados, uma classe própria para cada estado concreto, e um contexto (a FSM) que delega a ela as chamadas de Enter/Update/Exit e mantém a referência ao estado ativo.
3. **Mapear** os quatro conceitos elementares da FSM estudados na Semana 2 — estado, transição, evento e ação — para os elementos concretos do padrão State em C#: cada estado passa a ser uma classe, cada transição uma chamada explícita de troca de estado, e o ciclo enter/update/exit passa a ser um contrato de interface implementado por cada classe.
4. **Diferenciar** tecnicamente a FSM por `enum`/`switch` da FSM organizada pelo padrão State, reconhecendo o que o padrão melhora (isolamento de responsabilidade, testabilidade, legibilidade por estado) e o que ele **não** resolve — a explosão de transições identificada na Semana 2 continua, apenas mais organizada.
5. **Refatorar**, em grupo, a FSM implementada na Semana 2 para uma implementação baseada no padrão State em C#, preservando o comportamento observável já validado.
6. **Justificar** tecnicamente a escolha entre manter a implementação por `enum`/`switch` ou migrar para o padrão State, considerando o tamanho e a trajetória prevista do Micro Game.

---

## Conteúdos

Esta semana **não introduz um capítulo novo da Apostila** — aprofunda a aplicação da **Parte II, Capítulo 3 — Máquinas de Estado Finitas**, já estudado na Semana 2, com foco na materialização por código:

- revisão dos quatro conceitos elementares da FSM — estado, transição, evento, ação (seção 3.2) — agora sob a ótica de organização de código, não apenas de modelagem conceitual;
- revisão do ciclo enter/update/exit (seção 3.3.2), agora como contrato de interface a ser implementado por cada classe de estado;
- aprofundamento da seção 3.7 (materialização da FSM), com foco na alternativa já citada na Semana 2 — o padrão de projeto State em C# — como estrutura de código para uma FSM que cresce além de poucos estados;
- estrutura do padrão State (GoF): interface/classe base de estado comum, classes concretas por estado, contexto que delega chamadas e mantém a referência ao estado ativo;
- comparação técnica entre `enum`/`switch` e padrão State, sem reintroduzir a discussão de hierarquia.

**Observação sobre o Cronograma desta oferta da disciplina:** a Máquina de Estados Hierárquica (Parte II, Capítulo 4 da Apostila) não é trabalhada nesta semana, nem em nenhuma outra desta oferta — é uma exclusão deliberada, análoga à do GOAP no Capítulo 6 (ver Manual do Professor), motivada pelo ritmo da turma. O capítulo permanece disponível na Apostila como leitura de aprofundamento voluntário, mas o Micro Game NPC Decision segue diretamente da FSM (Semanas 2–3) para a Árvore de Comportamento (Semana 4), sem passar por uma etapa hierárquica intermediária. O professor deve comunicar essa mudança à turma, explicitamente, na abertura do Encontro 1: a pergunta desta semana não é "como organizar hierarquicamente", é "como organizar o *código*" da FSM que já existe.

Não devem ser antecipados, portanto, conteúdos de árvores de comportamento e Blackboard (Capítulo 6), nem qualquer noção de hierarquia de estados: a explosão de transições identificada na Semana 2 permanece, propositalmente, um problema em aberto — será resolvida diretamente pela Árvore de Comportamento na Semana 4, sem passagem intermediária pela HFSM.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte II, Capítulo 3, seções 3.2, 3.3.2 e 3.7 (revisão aprofundada); referência externa sobre o padrão de projeto State (Gang of Four), caso o professor deseje material complementar de apoio |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com a FSM da Semana 2 já implementada |
| **Cena Unity utilizada** | A mesma cena de demonstração da Semana 2 (NPC provisório e ponto de referência do jogador), reaproveitada para a refatoração de código |
| **Assets** | Nenhum asset de arte adicional; segue-se com o modelo provisório do NPC já utilizado |
| **Exemplos** | Exemplo do inimigo guarda de cinco estados (Patrulhar, Investigar, Perseguir, Atacar, Fugir — seção 3.4 da Apostila), agora reescrito como classes `PatrulharState`, `InvestigarState` etc., cada uma implementando uma interface comum `IState` |
| **Vídeos** | Não previsto especificamente |
| **Jogos para Engenharia Reversa** | Não previsto nesta semana (ver seção "Engenharia Reversa" abaixo) |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação do padrão de projeto State como alternativa de implementação à FSM por `enum`/`switch`. Mapeamento dos conceitos da Semana 2 para a estrutura do padrão.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 10 min | Reconectar com a Semana 2 e anunciar a mudança de rota desta oferta da disciplina | Retoma a FSM implementada na Semana 2 e comunica explicitamente à turma que esta semana não trata de hierarquia (HFSM), mas de organização de código; apresenta a pergunta norteadora "como estruturar o código da FSM para que ela cresça sem virar um emaranhado de condicionais?" | Relembram a implementação da FSM da Semana 2 e a estimativa de crescimento de transições feita ao final daquele encontro |
| 2. O problema: um método que cresce demais | 15 min | Mostrar concretamente o limite da implementação por `enum`/`switch` | Apresenta um `switch` de FSM crescido artificialmente para o exemplo do guarda de cinco estados, destacando como toda a lógica de todos os estados convive no mesmo método, difícil de ler e de testar isoladamente | Identificam, no exemplo, blocos de código que pertencem a estados diferentes, mas estão misturados no mesmo `switch` |
| 3. Fundamentos: a estrutura do padrão State | 20 min | Definir com precisão a estrutura do padrão de projeto State (GoF) | Apresenta a interface/classe base comum (`IState`, com `Enter`, `Update`, `Exit`), uma classe concreta por estado, e o contexto (a FSM) que mantém a referência ao estado ativo e delega as chamadas | Identificam, para o exemplo do guarda, quais classes seriam necessárias e o que cada uma conteria |
| 4. Mapeamento: da Semana 2 ao padrão State | 20 min | Traduzir estado, transição, evento e ação para elementos concretos do padrão | Conduz o mapeamento explícito: estado → classe; ciclo enter/update/exit → métodos da interface; transição → chamada explícita de troca de estado no contexto; evento/guarda → condição avaliada dentro do `Update` do estado ativo | Reescrevem, em duplas, um trecho do `switch` do exemplo do guarda como uma classe de estado isolada |
| 5. Comparação técnica: `switch` versus padrão State | 15 min | Diferenciar as duas abordagens e reconhecer o que muda e o que não muda | Conduz a comparação: o padrão State melhora isolamento, legibilidade e testabilidade por estado; **não resolve** a explosão de transições — o número de regras permanece o mesmo, apenas distribuído em mais arquivos | Discutem em grupo se a refatoração resolveria, por si só, o problema de transições repetidas identificado na Semana 2 |
| 6. Demonstração no Unity/C# | 10 min | Mostrar a refatoração ao vivo | Demonstra ao vivo a conversão de dois ou três `case` do `switch` do exemplo do guarda em classes de estado, com o contexto trocando entre elas | Observam a demonstração e relacionam cada `case` convertido aos elementos da interface `IState` |

---

## Encontro 2 (1h30)

**Foco:** Refatoração guiada do Micro Game NPC Decision, migrando a implementação da Semana 2 para o padrão State em C#. Discussão técnica comparando as duas abordagens.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando a estrutura do padrão State e o mapeamento estado→classe | Respondem perguntas de verificação oral |
| 2. Análise da FSM de cada grupo | 15 min | Avaliar se a implementação atual do grupo já usa o padrão State ou ainda é por `switch` | Orienta cada grupo a identificar como sua FSM da Semana 2 foi implementada (Animator, `switch`, ou já padrão State) e a planejar a refatoração conforme o ponto de partida | Classificam sua própria implementação e listam os estados a converter |
| 3. Projeto das classes de estado | 15 min | Planejar a interface comum e as classes concretas antes de codificar | Acompanha cada grupo na definição da interface `IState` (ou equivalente) e na lista de classes concretas necessárias, uma por estado já existente | Projetam, em papel ou diagrama, a interface comum e as classes de estado do próprio NPC |
| 4. Implementação guiada | 35 min | Refatorar a implementação existente para o padrão State | Acompanha os grupos na refatoração, reforçando que o comportamento observável deve permanecer idêntico ao da Semana 2, e que apenas a organização do código muda | Reescrevem sua FSM como um conjunto de classes de estado, testando cada transição migrada |
| 5. Testes e ajustes | 10 min | Verificar se o comportamento refatorado corresponde ao esperado | Circula entre os grupos, testando se a FSM refatorada se comporta exatamente como antes da refatoração | Testam a FSM refatorada e corrigem transições ou ciclos enter/update/exit mal migrados |
| 6. Discussão técnica: o que mudou e o que não mudou | 5 min | Fechar comparando as duas abordagens a partir da prática | Conduz uma discussão rápida: o que ficou mais fácil de ler e testar? O número de transições escritas mudou? | Comparam a organização do código antes e depois, reconhecendo que a explosão de transições continua sem solução |

---

## Micro Game

**Micro Game em desenvolvimento:** NPC Decision (Módulo 1).

**Objetivo pedagógico:** demonstrar como um NPC decide o que fazer, evoluindo de uma implementação simples por `enum`/`switch` (Semana 2) para uma FSM organizada pelo padrão de projeto State (Semana 3), antes de migrar diretamente para uma Árvore de Comportamento com Blackboard na Semana 4.

**Estado ao final da Semana 3:** FSM da Semana 2 refatorada para o padrão State, contendo:

- uma interface ou classe base comum a todos os estados (`IState` ou equivalente), com os métodos Enter, Update e Exit;
- uma classe concreta para cada estado já definido na Semana 2 (três a cinco estados);
- um contexto (a FSM) que mantém a referência ao estado ativo e delega as chamadas do ciclo enter/update/exit;
- transições implementadas como chamadas explícitas de troca de estado, preservando as guardas e prioridades já definidas;
- comportamento observável idêntico ao validado na Semana 2 — o ganho é de organização de código, não de novo comportamento.

**Relação com módulos anteriores:** dá continuidade direta à FSM implementada na Semana 2, refatorando sua estrutura de código sem introduzir hierarquia. Servirá de base direta para a migração prevista na Semana 4, quando os próprios estados (não superestados — esta oferta da disciplina não passa pela HFSM) serão agrupados em subárvores de uma Árvore de Comportamento.

---

## Engenharia Reversa

Não há atividade formal de Engenharia Reversa prevista para a Semana 3, conforme o Cronograma — o primeiro momento formal ocorre na Semana 4, junto à apresentação da metodologia de Engenharia Reversa (Capítulo 14 da Apostila).

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C# (padrão de projeto State)** | Refatoração da FSM do NPC Decision, migrando de `enum`/`switch` (ou consolidando a implementação já feita via padrão State na Semana 2) para uma estrutura de classes de estado |

Nenhuma ferramenta de terceiros é apresentada nesta semana. Sub-state machines do Animator não são utilizadas, pois não fazem parte do escopo desta oferta da disciplina (a HFSM, Capítulo 4, não é trabalhada).

---

## Atividade de Laboratório

**Objetivo:** refatorar a FSM do Micro Game NPC Decision, implementada na Semana 2, para uma estrutura baseada no padrão de projeto State em C#.

**Etapas:**

1. Cada grupo revisa como sua FSM da Semana 2 foi implementada e identifica os estados a converter.
2. Definição de uma interface ou classe base comum (`IState`), com os métodos Enter, Update e Exit.
3. Criação de uma classe concreta para cada estado já existente, migrando a lógica correspondente do `switch` (quando aplicável) para a classe.
4. Implementação do contexto (a FSM), que mantém a referência ao estado ativo e realiza as trocas de estado.
5. Teste do comportamento resultante, verificando se ele é idêntico ao da FSM da Semana 2.
6. Reflexão em grupo comparando a legibilidade e a testabilidade do código antes e depois da refatoração.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma FSM funcional no Micro Game NPC Decision organizada pelo padrão State, com uma classe por estado e comportamento observável idêntico ao validado na Semana 2.

---

## Verificação da Aprendizagem

O Módulo 1 se encerra formalmente apenas na Semana 4, quando ocorrem o Desafio de Escolha Tecnológica, o AI Design Log e a Engenharia Reversa do módulo. A verificação nesta semana é, portanto, **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes descrevem corretamente a estrutura do padrão State e mapeiam estado/transição/evento/ação para seus elementos (critério **Compreensão Conceitual** da Rubrica);
- observação da refatoração guiada no Encontro 2, verificando se a FSM resultante preserva o comportamento da versão anterior e se a interface de estado foi corretamente implementada (indício de **Aplicação Prática**, formalmente avaliado na consolidação do Micro Game na Semana 4);
- discussão técnica de comparação entre `switch` e padrão State, avaliando se os grupos conseguem articular o que a refatoração melhora e o que ela ainda não resolve — a explosão de transições (indício de **Tomada de Decisão**);
- observação da organização do código (uma classe por estado, interface comum) durante a implementação guiada (indício de **Uso da Unity e do Ecossistema**).

Nenhuma nota é atribuída nesta semana, conforme os Critérios de Notas da disciplina, que vinculam a composição da nota aos módulos encerrados nas Semanas 4, 7, 9, 11, 13 e 16, ao checkpoint da Semana 8 e à apresentação final da Semana 17.

---

## Entregas

Não há entrega formal prevista para a Semana 3, conforme o Cronograma.

A FSM refatorada do Micro Game NPC Decision permanece com os grupos, para migração direta para Árvore de Comportamento com Blackboard na Semana 4 e consolidação nessa mesma semana, quando passa a compor o Micro Game entregável, o AI Design Log e o Desafio de Escolha Tecnológica do Módulo 1.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir a interface de estado com a própria FSM, implementando toda a lógica de transição dentro de cada classe de estado, sem um contexto central | Reforçar que o contexto (a FSM) é quem mantém a referência ao estado ativo e realiza a troca — o estado apenas decide *quando* pedir a troca, não *como* ela ocorre |
| Achar que a refatoração para o padrão State resolve, por si só, a explosão de transições | Retomar explicitamente a comparação técnica do Encontro 2: o número de regras é o mesmo, apenas mais organizado; o problema de fato só será resolvido na Semana 4 |
| Alterar o comportamento observável do NPC durante a refatoração, em vez de apenas reorganizar o código | Insistir, antes da implementação, que o teste de aceitação é comparar o comportamento novo com o antigo lado a lado — qualquer diferença é um bug de refatoração, não uma melhoria |
| Grupos com FSM implementada via Animator na Semana 2 terem dificuldade de mapear a refatoração para código | Orientar esses grupos a reescrever a lógica em C# como parte desta semana, já que o padrão State pressupõe implementação por script; alternativa: manter o Animator e discutir apenas conceitualmente o mapeamento para o padrão State |

---

## Preparação para a Próxima Semana

Para a Semana 4 (Árvores de Comportamento, Blackboard e Engenharia Reversa), o professor deve:

- solicitar a leitura prévia do Capítulo 6 da Apostila (Árvores de Comportamento) e do Capítulo 14 (Metodologia de Engenharia Reversa de IA); o Capítulo 5 (Árvores de Decisão) **não** precisa ser revisado como ponte, pois a Semana 4 desta oferta migra diretamente da FSM (padrão State) para a Árvore de Comportamento;
- garantir que todos os grupos tenham, de fato, uma FSM funcional organizada pelo padrão State no Micro Game NPC Decision ao final da Semana 3;
- revisar rapidamente a FSM de cada grupo antes do próximo encontro, agrupando mentalmente os estados existentes por afinidade comportamental (por exemplo, estados de combate versus estados pacíficos), para usar como base concreta no mapeamento de estados para subárvores na Semana 4 — este agrupamento substitui, nesta oferta, o papel que os superestados da HFSM cumpririam;
- providenciar acesso ao pacote **Unity Behavior** nos projetos de cada grupo, já que a Semana 4 realiza a primeira demonstração prática dessa ferramenta;
- selecionar previamente o jogo comercial a ser utilizado no primeiro momento de Engenharia Reversa, garantindo que sua IA de decisão seja suficientemente visível para sustentar a discussão.
