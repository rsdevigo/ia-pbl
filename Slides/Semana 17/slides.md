---
marp: true
paginate: true
theme: academic-course
size: 16:9
header: "Tecnologia em Jogos Digitais • Inteligência Artificial e Ilusão de Inteligência"
footer: "IFMS • Semana 17"
---

<!-- _class: cover -->

![logo](https://dummyimage.com/280x90/ffffff/3b2f68&text=IFMS)

# Inteligência Artificial e Ilusão de Inteligência

## Semana 17 — Engenharia Reversa integrada e apresentação final do AI Playground

<div class="meta">

**Unidade VII:** Projeto Final e Encerramento
**Apostila:** Parte VII, Cap. 15 — Estudos de Caso Comentados
**Micro Game:** integração final dos seis Micro Games (sem desenvolvimento novo)

</div>

---

## Objetivos da aula

Ao final de hoje você será capaz de:

- relacionar os estudos de caso comentados da Apostila às técnicas estudadas no semestre;
- revisar, de forma integrada, os seis momentos de Engenharia Reversa realizados;
- apresentar o AI Playground completo, justificando as decisões de cada Micro Game;
- distinguir, com exemplos do próprio semestre, aprendizagem real de ilusão de inteligência.

---

## Retomada da Semana 16

**Semana 16:** treinar (ML-Agents) × executar (Sentis); consolidação do Adaptive AI; encerramento do ciclo dos seis módulos de conteúdo.

<div class="tip">

Hoje não há conteúdo novo. O objetivo é olhar para trás e amarrar os seis módulos em uma única síntese.

</div>

---

<!-- _class: question -->

# O que aprendemos sobre IA e ilusão de inteligência?

A pergunta que atravessou todo o semestre.

---

## O percurso dos seis módulos

![diagram](assets/mermaid-1.png)

Cada módulo respondeu a uma pergunta de design com uma família de técnicas — não o contrário.

---

## Um mapa das técnicas estudadas

| Módulo | Pergunta | Técnicas | Micro Game |
|---|---|---|---|
| 1 | Decidir o que fazer | FSM, HFSM, Behavior Trees | NPC Decision |
| 2 | Encontrar o destino | NavMesh, A*, JPS+ | Navigation |
| 3 | Escolher a melhor ação | Decision Trees, Influence Maps, Utility AI | Tactical AI |
| 4 | Derrotar um adversário | Minimax, heurísticas | Board Game AI |
| 5 | Encontrar boas soluções | Algoritmos Genéticos | Genetic Lab |
| 6 | Aprender com a experiência | Reinforcement Learning, ML-Agents, Sentis | Adaptive AI |

---

<!-- _class: section -->

# Estudos de Caso Comentados

Apostila, Parte VII, Capítulo 15.

---

## Da teoria ao jogo comercial

O Capítulo 15 reúne casos comerciais que ilustram, um a um, os seis módulos do semestre.

<div class="tip">

Cada estudo de caso responde à mesma pergunta que orientou um módulo — só que agora aplicada a um jogo publicado, e não a um Micro Game experimental.

</div>

---

## Como usar o capítulo hoje

1. Ler cada estudo de caso relacionando-o à família de técnicas correspondente;
2. identificar o que, no comportamento descrito, sugere a técnica hipotetizada;
3. observar onde técnicas simples produzem ilusão convincente, e onde técnicas mais complexas seriam necessárias.

---

<!-- _class: section -->

# Revisão integrada da Engenharia Reversa

Os seis momentos do semestre, revisitados.

---

## Os seis momentos

![diagram](assets/mermaid-2.png)

Cada momento levantou uma hipótese de arquitetura para um jogo comercial, com o conhecimento disponível até aquela semana.

---

## A pergunta de hoje

<div class="warning">

As hipóteses levantadas em cada momento anterior ainda parecem corretas à luz do que foi visto depois?

</div>

Revisitem suas anotações: alguma hipótese de FSM se revela, agora, mais próxima de uma Behavior Tree? Alguma decisão "tática" seria hoje melhor explicada por Utility AI?

---

> [!FIGURA]
>
> **Objetivo didático**
>
> Apoiar a revisão integrada, situando lado a lado os seis jogos comerciais analisados ao longo do semestre e a técnica hipotetizada em cada momento.
>
> **Arquivo sugerido**
>
> ```
> assets/linha-do-tempo-engenharia-reversa.webp
> ```
>
> **Descrição**
>
> Linha do tempo horizontal com seis marcadores (um por módulo), cada um contendo o nome do jogo analisado naquele momento e a técnica hipotetizada, sem capturas de tela dos jogos em si.
>
> **Como produzir**
>
> Diagrama simples montado em Krita a partir dos registros de Engenharia Reversa de cada módulo, sem uso de imagens dos jogos originais.

---

<!-- _class: section -->

# Aprendizagem real × ilusão de inteligência

A síntese conceitual da disciplina.

---

## Duas pontas do mesmo espectro

<div class="tip">

**Técnicas simples, ilusão forte:** uma FSM de três estados, bem ajustada, pode parecer mais "inteligente" do que é.

</div>

<div class="warning">

**Técnicas complexas, ilusão frágil:** um agente treinado por RL pode se comportar de forma incompreensível se mal recompensado.

</div>

---

<div class="industry">

Na indústria, a escolha raramente é "a técnica mais avançada". É a técnica que produz a ilusão de inteligência necessária, com o menor custo de produção e depuração possível.

</div>

---

<!-- _class: section -->

# Preparação para a apresentação final

O que cada grupo leva para o Encontro 2.

---

## Checklist do AI Playground

1. Os seis Micro Games reunidos e executáveis no mesmo projeto Unity;
2. navegação simples entre eles, sem mecânicas que desviem o foco da IA;
3. AI Design Log consolidado, com síntese — não apenas cópia — dos seis módulos.

---

<div class="error">

**Erro comum:** consolidar o AI Design Log como uma simples justaposição dos seis documentos anteriores, sem evidenciar a evolução do grupo ao longo do semestre.

</div>

---

<div class="error">

**Erro comum:** priorizar, na apresentação, o Micro Game mais recente em detrimento dos demais. Todos os seis integram a nota final.

</div>

---

## Como será avaliado

A apresentação final e o AI Design Log consolidado são avaliados pelos oito critérios da Rubrica, de forma integrada — não módulo a módulo.

<div class="tip">

Preparem, para cada Micro Game, uma explicação objetiva: qual problema, qual solução, por quê.

</div>

---

<!-- _class: summary -->

## Resumo da semana

- Estudos de Caso Comentados (Apostila, Cap. 15) relacionados aos seis módulos
- Revisão integrada dos seis momentos de Engenharia Reversa
- Síntese entre aprendizagem real e ilusão de inteligência
- Checklist de integração do AI Playground completo
- Preparação para a apresentação final e entrega do AI Design Log consolidado

---

## Encerramento do semestre

Não há Semana 18. Esta é a última aula da disciplina.

<div class="tip">

O AI Playground reunido hoje é a evidência de um semestre inteiro de decisões técnicas justificadas — não apenas de código funcionando.

</div>
