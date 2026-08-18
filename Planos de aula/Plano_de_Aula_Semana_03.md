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
| **Tema** | Aprofundamento da FSM — o padrão de projeto State por herança, em C# |
| **Pergunta Norteadora** | Como estruturar o código de uma FSM para que ela cresça sem virar um emaranhado de condicionais? |
| **Tipo de semana** | 🔵 Regular (fundamentação e desenvolvimento do Micro Game) |

---

## Objetivos de Aprendizagem

Ao final da Semana 3, o estudante deverá ser capaz de:

1. **Explicar** o problema que motiva o padrão State — a implementação por `enum`/`switch` concentra toda a lógica de todos os estados em um único método, que cresce e se torna difícil de ler e de testar à medida que estados são adicionados.
2. **Descrever** com precisão a estrutura do padrão de projeto State por **herança**: uma classe base `State`, com métodos **virtuais** (`Enter`, `Update`, `Exit`, `FixedUpdate`) de corpo vazio por padrão; uma subclasse por estado concreto, sobrescrevendo apenas os métodos que precisa; e um contexto (`FSM`) que mantém a referência ao estado ativo (`currentState`) e delega as chamadas a ele.
3. **Justificar** a escolha de herança em vez de interface para este caso: a classe base concentra um campo compartilhado por todo estado (a referência ao contexto `FSM`) e permite que cada subclasse sobrescreva só o que precisa, sem ser obrigada a implementar os quatro métodos como uma interface exigiria.
4. **Mapear** os quatro conceitos elementares da FSM estudados na Semana 2 — estado, transição, evento e ação — para os elementos concretos da classe base `State` e do contexto `FSM`.
5. **Diferenciar** tecnicamente a FSM por `enum`/`switch` da FSM organizada por herança de `State`, reconhecendo o que a refatoração melhora (isolamento de responsabilidade, testabilidade, legibilidade por estado) e o que ela **não** resolve — a explosão de transições identificada na Semana 2 continua, apenas mais organizada.
6. **Refatorar**, em grupo, a FSM implementada na Semana 2 para uma implementação baseada em herança de `State`, preservando o comportamento observável já validado.
7. **Identificar** e corrigir, de forma crítica, um problema de projeto em uma implementação de referência real: a classe base `State`, se não for declarada `abstract`, permite ser instanciada diretamente — algo sem sentido semântico (um "estado genérico" sem comportamento).

---

## Conteúdos

Esta semana **não introduz um capítulo novo da Apostila** — aprofunda a aplicação da **Parte II, Capítulo 3 — Máquinas de Estado Finitas**, já estudado na Semana 2, com foco na materialização por código:

- revisão dos quatro conceitos elementares da FSM — estado, transição, evento, ação (seção 3.2) — agora sob a ótica de organização de código, não apenas de modelagem conceitual;
- revisão do ciclo enter/update/exit (seção 3.3.2), agora como contrato de métodos **virtuais** herdados de uma classe base, sobrescritos apenas onde necessário — e sua extensão natural no ambiente Unity: `FixedUpdate`, para lógica de física, ao lado do `Update` de lógica por quadro;
- aprofundamento da seção 3.7 (materialização da FSM), com foco na alternativa já citada na Semana 2 — o padrão de projeto State em C# — desta vez implementado por **herança** de uma classe base concreta, não por interface;
- estrutura do padrão State por herança: classe base `State` com métodos virtuais, subclasses concretas por estado, classe de contexto `FSM` que mantém o estado ativo e delega as chamadas;
- análise crítica de uma implementação real de referência (`State.cs` e `FSM.cs`), incluindo a discussão de um problema de projeto nela presente (classe base não declarada `abstract`);
- comparação técnica entre `enum`/`switch` e herança de `State`, sem reintroduzir a discussão de hierarquia.

**Por que herança, e não interface, para este caso?** A classe base `State` guarda um campo compartilhado por todo estado — a referência ao contexto (`protected FSM _fsm`) — que uma interface não poderia carregar; cada estado concreto herda esse campo pronto, em vez de reimplementá-lo. Além disso, os métodos do ciclo de vida (`Enter`, `Exit`, `Update`, `FixedUpdate`) são declarados `virtual` com corpo vazio: uma subclasse sobrescreve só o que precisa, enquanto uma interface obrigaria a implementação dos quatro métodos em toda classe concreta, mesmo quando vazios. Essa é uma escolha de projeto, não a única correta — o professor deve deixar claro que ambas as abordagens (interface e herança) são variantes válidas do padrão State, e que a decisão depende do que se quer compartilhar entre os estados.

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
| **Exemplos** | Implementação de referência real: `State.cs` e `FSM.cs` — classe base `State` com campo protegido `_fsm`, métodos virtuais `Enter`/`Exit`/`Update`/`FixedUpdate`, e classe `FSM` com `currentState`, `Add(key, state)`, `SetCurrentState`, `GetState`, `Update` e `FixedUpdate`. Exemplo do inimigo guarda de cinco estados (Patrulhar, Investigar, Perseguir, Atacar, Fugir — seção 3.4 da Apostila), reescrito como subclasses `PatrulharState`, `InvestigarState` etc. |
| **Vídeos** | Não previsto especificamente |
| **Jogos para Engenharia Reversa** | Não previsto nesta semana (ver seção "Engenharia Reversa" abaixo) |

---

## Encontro 1 (1h30)

**Foco:** Fundamentação do padrão de projeto State por herança como alternativa de implementação à FSM por `enum`/`switch`. Mapeamento dos conceitos da Semana 2 para a estrutura da classe base `State` e do contexto `FSM`.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 10 min | Reconectar com a Semana 2 e anunciar a mudança de rota desta oferta da disciplina | Retoma a FSM implementada na Semana 2 e comunica explicitamente à turma que esta semana não trata de hierarquia (HFSM), mas de organização de código; apresenta a pergunta norteadora "como estruturar o código da FSM para que ela cresça sem virar um emaranhado de condicionais?" | Relembram a implementação da FSM da Semana 2 e a estimativa de crescimento de transições feita ao final daquele encontro |
| 2. O problema: um método que cresce demais | 15 min | Mostrar concretamente o limite da implementação por `enum`/`switch` | Apresenta um `switch` de FSM crescido artificialmente para o exemplo do guarda de cinco estados, destacando como toda a lógica de todos os estados convive no mesmo método, difícil de ler e de testar isoladamente | Identificam, no exemplo, blocos de código que pertencem a estados diferentes, mas estão misturados no mesmo `switch` |
| 3. Fundamentos: a classe base `State` e o contexto `FSM` | 20 min | Definir com precisão a estrutura do padrão State por herança, a partir de uma implementação real | Apresenta o código real de `State.cs` e `FSM.cs`: a classe base `State` com campo `protected FSM _fsm` e métodos `virtual` de corpo vazio (`Enter`, `Exit`, `Update`, `FixedUpdate`); a classe `FSM`, que guarda `currentState`, adiciona estados a um dicionário e troca de estado via `SetCurrentState` (chamando `Exit` do antigo e `Enter` do novo) | Identificam, no código real, qual campo é compartilhado por todo estado e por que ele está na classe base, não em cada subclasse |
| 4. Por que herança, e não interface? | 15 min | Justificar tecnicamente a escolha de projeto | Conduz a comparação: herança permite compartilhar o campo `_fsm` e sobrescrever só os métodos necessários (métodos virtuais com corpo vazio); uma interface obrigaria implementar os quatro métodos em toda classe, mesmo vazios | Discutem em duplas: se cada estado precisasse herdar de outra classe (por exemplo, um `MonoBehaviour`), a herança de `State` ainda seria possível? (Não — C# não tem herança múltipla de classes; é uma limitação real da escolha) |
| 5. Mapeamento: da Semana 2 à classe `State` | 15 min | Traduzir estado, transição, evento e ação para elementos concretos | Conduz o mapeamento explícito: estado → subclasse de `State`; ciclo enter/update/exit → métodos virtuais sobrescritos; transição → chamada a `fsm.SetCurrentState(novoEstado)`; evento/guarda → condição avaliada dentro do `Update`/`FixedUpdate` do estado ativo | Reescrevem, em duplas, um trecho do `switch` do exemplo do guarda como uma subclasse de `State` |
| 6. Erro de projeto na implementação de referência | 10 min | Exercitar leitura crítica de código real, não apenas reprodução | Pergunta à turma: "o que impede `new State(fsm)` de ser chamado diretamente, no código real?" — nada impede, porque a classe não é `abstract`; discute por que isso é um problema semântico (um estado sem comportamento não deveria poder existir) e como corrigir (`public abstract class State`) | Identificam o problema no código real e propõem a correção antes de replicá-lo no próprio Micro Game |

---

## Encontro 2 (1h30)

**Foco:** Refatoração guiada do Micro Game NPC Decision, migrando a implementação da Semana 2 para herança de `State` em C#. Discussão técnica comparando as duas abordagens.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 10 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando a estrutura da classe base `State`, o contexto `FSM` e o mapeamento estado→subclasse | Respondem perguntas de verificação oral |
| 2. Análise da FSM de cada grupo | 15 min | Avaliar se a implementação atual do grupo já usa herança de estado ou ainda é por `switch` | Orienta cada grupo a identificar como sua FSM da Semana 2 foi implementada (Animator, `switch`, ou já orientada a objetos) e a planejar a refatoração conforme o ponto de partida | Classificam sua própria implementação e listam os estados a converter |
| 3. Projeto da classe base e do contexto | 15 min | Planejar `State` (abstrata) e `FSM` antes de codificar | Acompanha cada grupo na definição da classe base `State` (já como `abstract`, corrigindo o problema discutido no Encontro 1), do campo `_fsm` e da lista de subclasses concretas necessárias, uma por estado já existente | Projetam, em papel ou diagrama, a classe base, o contexto `FSM` e as subclasses de estado do próprio NPC |
| 4. Implementação guiada | 35 min | Refatorar a implementação existente para herança de `State` | Acompanha os grupos na refatoração, reforçando que o comportamento observável deve permanecer idêntico ao da Semana 2, e que apenas a organização do código muda | Reescrevem sua FSM como uma classe base `State` (abstrata) e subclasses concretas, testando cada transição migrada |
| 5. Testes e ajustes | 10 min | Verificar se o comportamento refatorado corresponde ao esperado | Circula entre os grupos, testando se a FSM refatorada se comporta exatamente como antes da refatoração | Testam a FSM refatorada e corrigem transições ou ciclos enter/update/exit mal migrados |
| 6. Discussão técnica: o que mudou e o que não mudou | 5 min | Fechar comparando as duas abordagens a partir da prática | Conduz uma discussão rápida: o que ficou mais fácil de ler e testar? O número de transições escritas mudou? | Comparam a organização do código antes e depois, reconhecendo que a explosão de transições continua sem solução |

---

## Micro Game

**Micro Game em desenvolvimento:** NPC Decision (Módulo 1).

**Objetivo pedagógico:** demonstrar como um NPC decide o que fazer, evoluindo de uma implementação simples por `enum`/`switch` (Semana 2) para uma FSM organizada por herança de uma classe base `State` (Semana 3), antes de migrar diretamente para uma Árvore de Comportamento com Blackboard na Semana 4.

**Estado ao final da Semana 3:** FSM da Semana 2 refatorada para herança de `State`, contendo:

- uma classe base `State` (declarada `abstract`), com o campo protegido `_fsm` (referência ao contexto) e métodos virtuais `Enter`, `Update`, `Exit` (e `FixedUpdate`, quando aplicável);
- uma subclasse concreta para cada estado já definido na Semana 2 (três a cinco estados), sobrescrevendo apenas os métodos necessários;
- um contexto `FSM`, que mantém a referência ao estado ativo (`currentState`) e realiza a troca de estado disparando `Exit` do antigo e `Enter` do novo;
- transições implementadas como chamadas a `fsm.SetCurrentState(novoEstado)`, preservando as guardas e prioridades já definidas;
- comportamento observável idêntico ao validado na Semana 2 — o ganho é de organização de código, não de novo comportamento.

**Relação com módulos anteriores:** dá continuidade direta à FSM implementada na Semana 2, refatorando sua estrutura de código sem introduzir hierarquia. Servirá de base direta para a migração prevista na Semana 4, quando os próprios estados (não superestados — esta oferta da disciplina não passa pela HFSM) serão agrupados em subárvores de uma Árvore de Comportamento.

---

## Engenharia Reversa

Não há atividade formal de Engenharia Reversa prevista para a Semana 3, conforme o Cronograma — o primeiro momento formal ocorre na Semana 4, junto à apresentação da metodologia de Engenharia Reversa (Capítulo 14 da Apostila).

A leitura crítica do código real de `State.cs`/`FSM.cs` (Encontro 1, etapa 6) não é Engenharia Reversa de IA de jogo comercial — é revisão de código-fonte disponível abertamente, um exercício de leitura crítica diferente, que não deve ser confundido com a metodologia formal do Capítulo 14.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C# (padrão de projeto State por herança)** | Refatoração da FSM do NPC Decision, migrando de `enum`/`switch` para uma classe base `State` (abstrata) e subclasses concretas por estado, seguindo a estrutura de `State.cs`/`FSM.cs` como referência |

Nenhuma ferramenta de terceiros é apresentada nesta semana. Sub-state machines do Animator não são utilizadas, pois não fazem parte do escopo desta oferta da disciplina (a HFSM, Capítulo 4, não é trabalhada).

---

## Atividade de Laboratório

**Objetivo:** refatorar a FSM do Micro Game NPC Decision, implementada na Semana 2, para uma estrutura baseada no padrão de projeto State por herança, em C#.

**Etapas:**

1. Cada grupo revisa como sua FSM da Semana 2 foi implementada e identifica os estados a converter.
2. Definição de uma classe base `State` (abstrata), com o campo `_fsm` e os métodos virtuais Enter, Update e Exit (e FixedUpdate, se necessário).
3. Criação de uma subclasse concreta para cada estado já existente, migrando a lógica correspondente do `switch` (quando aplicável) para a subclasse, sobrescrevendo apenas os métodos necessários.
4. Implementação do contexto `FSM`, que mantém a referência ao estado ativo e realiza as trocas de estado via `SetCurrentState`.
5. Teste do comportamento resultante, verificando se ele é idêntico ao da FSM da Semana 2.
6. Reflexão em grupo comparando a legibilidade e a testabilidade do código antes e depois da refatoração.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter uma FSM funcional no Micro Game NPC Decision organizada por herança de `State`, com uma subclasse por estado, classe base abstrata e comportamento observável idêntico ao validado na Semana 2.

---

## Verificação da Aprendizagem

O Módulo 1 se encerra formalmente apenas na Semana 4, quando ocorrem o Desafio de Escolha Tecnológica, o AI Design Log e a Engenharia Reversa do módulo. A verificação nesta semana é, portanto, **formativa e informal**, servindo de base para o acompanhamento contínuo previsto na Rubrica de Avaliação.

O professor pode verificar os objetivos da semana por meio de:

- perguntas orais durante o Encontro 1, observando se os estudantes descrevem corretamente a estrutura da classe base `State` e do contexto `FSM`, e se justificam a escolha de herança em vez de interface (critério **Compreensão Conceitual** da Rubrica);
- observação da refatoração guiada no Encontro 2, verificando se a FSM resultante preserva o comportamento da versão anterior e se a classe base foi corretamente declarada `abstract` (indício de **Aplicação Prática**, formalmente avaliado na consolidação do Micro Game na Semana 4);
- discussão técnica de comparação entre `switch` e herança de `State`, avaliando se os grupos conseguem articular o que a refatoração melhora e o que ela ainda não resolve — a explosão de transições (indício de **Tomada de Decisão**);
- observação da organização do código (uma subclasse por estado, classe base abstrata) durante a implementação guiada (indício de **Uso da Unity e do Ecossistema**).

Nenhuma nota é atribuída nesta semana, conforme os Critérios de Notas da disciplina, que vinculam a composição da nota aos módulos encerrados nas Semanas 4, 7, 9, 11, 13 e 16, ao checkpoint da Semana 8 e à apresentação final da Semana 17.

---

## Entregas

Não há entrega formal prevista para a Semana 3, conforme o Cronograma.

A FSM refatorada do Micro Game NPC Decision permanece com os grupos, para migração direta para Árvore de Comportamento com Blackboard na Semana 4 e consolidação nessa mesma semana, quando passa a compor o Micro Game entregável, o AI Design Log e o Desafio de Escolha Tecnológica do Módulo 1.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir a classe base `State` com a própria FSM, implementando toda a lógica de transição dentro de cada subclasse de estado, sem consultar o contexto | Reforçar que o contexto (a `FSM`) é quem mantém a referência ao estado ativo e realiza a troca — o estado apenas decide *quando* pedir a troca (chamando `fsm.SetCurrentState`), não *como* ela ocorre |
| Deixar a classe base `State` não abstrata, permitindo instanciá-la diretamente | Retomar o erro de projeto discutido no Encontro 1 (etapa 6) a partir do código real de referência; exigir `public abstract class State` na implementação do grupo |
| Achar que a refatoração para herança de `State` resolve, por si só, a explosão de transições | Retomar explicitamente a comparação técnica do Encontro 2: o número de regras é o mesmo, apenas mais organizado; o problema de fato só será resolvido na Semana 4 |
| Alterar o comportamento observável do NPC durante a refatoração, em vez de apenas reorganizar o código | Insistir, antes da implementação, que o teste de aceitação é comparar o comportamento novo com o antigo lado a lado — qualquer diferença é um bug de refatoração, não uma melhoria |
| Grupos com FSM implementada via Animator na Semana 2 terem dificuldade de mapear a refatoração para código | Orientar esses grupos a reescrever a lógica em C# como parte desta semana, já que o padrão State por herança pressupõe implementação por script; alternativa: manter o Animator e discutir apenas conceitualmente o mapeamento para a classe `State` |

---

## Preparação para a Próxima Semana

Para a Semana 4 (Árvores de Comportamento, Blackboard e Engenharia Reversa), o professor deve:

- solicitar a leitura prévia do Capítulo 6 da Apostila (Árvores de Comportamento) e do Capítulo 14 (Metodologia de Engenharia Reversa de IA); o Capítulo 5 (Árvores de Decisão) **não** precisa ser revisado como ponte, pois a Semana 4 desta oferta migra diretamente da FSM (herança de `State`) para a Árvore de Comportamento;
- garantir que todos os grupos tenham, de fato, uma FSM funcional organizada por herança de `State` no Micro Game NPC Decision ao final da Semana 3;
- revisar rapidamente a FSM de cada grupo antes do próximo encontro, agrupando mentalmente os estados existentes por afinidade comportamental (por exemplo, estados de combate versus estados pacíficos), para usar como base concreta no mapeamento de estados para subárvores na Semana 4 — este agrupamento substitui, nesta oferta, o papel que os superestados da HFSM cumpririam;
- providenciar acesso ao pacote **Unity Behavior** nos projetos de cada grupo, já que a Semana 4 realiza a primeira demonstração prática dessa ferramenta;
- selecionar previamente o jogo comercial a ser utilizado no primeiro momento de Engenharia Reversa, garantindo que sua IA de decisão seja suficientemente visível para sustentar a discussão.
