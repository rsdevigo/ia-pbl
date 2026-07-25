---
marp: true
paginate: true
theme: academic-course
size: 16:9
header: "Tecnologia em Jogos Digitais • Inteligência Artificial e Ilusão de Inteligência"
footer: "IFMS • Semana 08"
---

<!-- _class: cover -->

![logo](https://dummyimage.com/280x90/ffffff/3b2f68&text=IFMS)

# Inteligência Artificial e Ilusão de Inteligência

## Semana 8 — Árvores de Decisão e introdução aos Mapas de Influência

<div class="meta">

**Módulo 3:** Como um NPC escolhe sua melhor ação?
**Apostila:** Parte II, Cap. 5; Parte IV, Cap. 10 (introdução)
**Micro Game:** Tactical AI (início)

</div>

---

## Objetivos da aula

Ao final de hoje você será capaz de:

- diferenciar o problema da árvore de decisão do problema da FSM/HFSM;
- descrever nó, ramo e folha, e a avaliação da raiz até a ação;
- distinguir árvore de decisão de árvore de comportamento;
- justificar a ordenação de testes por custo e poder decisório;
- reconhecer o mapa de influência como resposta a "onde ir?".

---

## Retomada dos Módulos 1 e 2

**Módulo 1:** como um NPC decide o que fazer — FSM, HFSM, Behavior Trees, Blackboard.

**Módulo 2:** como um agente encontra seu destino — NavMesh, A*, JPS+.

Hoje: um novo problema. Nenhum dos dois módulos anteriores resolve *qual ação escolher agora*.

---

<!-- _class: question -->

# Como um NPC escolhe sua melhor ação?

A partir de várias condições observadas ao mesmo tempo — sem memória de estado.

---

## O problema da árvore de decisão

FSM pergunta: **"em que modo estou?"**

Árvore de decisão pergunta: **"qual ação, agora, dado este conjunto de condições?"**

<div class="tip">

Não há necessidade intrínseca de memória de estado — cada avaliação parte do zero.

</div>

---

<!-- _class: diagram -->

## Nós, ramos e folhas

```mermaid
flowchart TD
    A[Vê o jogador?] -->|sim| B[Distância curta?]
    A -->|não| C[Patrulhar]
    B -->|sim| D[Atacar corpo a corpo]
    B -->|não| E[Atirar]
```

A avaliação percorre a raiz até uma folha — sempre a mesma ação para o mesmo conjunto de condições.

---

## Árvore de decisão × árvore de comportamento

| Aspecto | Árvore de decisão | Árvore de comportamento |
|---|---|---|
| **Propósito** | Escolher uma ação | Orquestrar uma sequência |
| **Estados de retorno** | Ausentes | Sucesso, falha, em execução |
| **Noção de tempo** | Nenhuma | Central |
| **Reutilização/composição** | Limitada | Alta |

---

<div class="warning">

**Erro comum:** tratar a árvore de decisão como sinônimo da árvore de comportamento por compartilharem a forma de árvore. A árvore de decisão escolhe; não orquestra sequência.

</div>

---

## Ordenação de testes

Testes mais **baratos e decisivos** devem ficar perto da raiz.

A ordenação afeta o **custo de avaliação** — nunca o resultado final.

<div class="tip">

Profundidade maior custa mais para avaliar e reduz a legibilidade da árvore.

</div>

---

## Vantagens e limitações

| Vantagens | Limitações |
|---|---|
| Simplicidade | Ausência de tempo |
| Baixo custo | Sem sequenciamento |
| Transparência | Baixa reutilização e composição |

Essas limitações motivaram a adoção das árvores de comportamento pela indústria (Módulo 1).

---

## Ferramentas

| Situação | Solução |
|---|---|
| Árvore de decisão nativa | **Não existe ferramenta dedicada na Unity** |
| Implementação | C# ou Visual Scripting |
| Reaparição dentro do Behavior Tree | Nós de condição do Unity Behavior |

---

<!-- _class: question -->

# Do "como chegar?" ao "onde ir?"

O pathfinding (Módulo 2) não resolve tudo.

---

## Três situações que o pathfinding não resolve

- onde se posicionar para ter **cobertura**;
- por onde um **exército** deve avançar;
- para onde **fugir** de uma ameaça.

<div class="tip">

O mapa de influência responde "vale a pena ir?" — uma pergunta avaliativa, não topológica.

</div>

---

## Campo escalar: fonte, propagação, decaimento

Introdução apenas — aprofundamento na Semana 9.

- **Fonte:** ponto de origem de um valor de influência;
- **Propagação:** espalhamento desse valor pelo mapa;
- **Decaimento:** redução do valor com a distância da fonte.

---

<div class="warning">

**Atenção:** não confundir o mapa de influência com a grade de navegação do Módulo 2. A grade responde "posso ir?" (topológico); o mapa de influência responde "vale a pena ir?" (avaliativo).

</div>

---

<!-- _class: exercise -->

# Erro comum

Expressar, na árvore de decisão, uma sequência de ações com dependência de sucesso ("faça A, depois B").

<div class="objectives">

A árvore de decisão escolhe uma ação. Sequenciar é território das árvores de comportamento, já disponíveis do Módulo 1.

</div>

---

<!-- _class: section -->

# Micro Game Tactical AI — início

Primeira árvore de decisão funcional do NPC tático.

---

## O que implementar hoje

- duas ou três condições observáveis (visão do jogador, distância, vida);
- árvore de decisão em C# ou Visual Scripting, com nós, ramos e folhas identificáveis;
- teste de ao menos dois caminhos de avaliação distintos;
- justificativa da ordenação dos testes escolhida.

> [!FIGURA]
>
> **Objetivo didático**
>
> Apoiar a implementação guiada, mostrando a árvore de decisão do NPC tático já desenhada antes da codificação.
>
> **Arquivo sugerido**
>
> ```
> assets/arvore-decisao-npc-tatico.webp
> ```
>
> **Descrição**
>
> Diagrama de árvore com raiz "Vê o jogador?", ramificando em "Distância curta?" e folhas de ação (Patrulhar, Atacar corpo a corpo, Atirar), com anotações indicando qual teste é mais barato.
>
> **Como produzir**
>
> Diagrama vetorial produzido no Krita a partir do esboço em papel elaborado pelos grupos durante a atividade de laboratório.

---

<!-- _class: section -->

# Apresentação Técnica Intermediária

Checkpoint do AI Playground — Módulos 1 e 2.

---

## Critérios do checkpoint

| Critério | O que observar |
|---|---|
| **Comunicação Técnica** | Clareza ao explicar problema, solução e decisões dos Micro Games NPC Decision e Navigation |
| **Evolução ao Longo do Semestre** | Incorporação consistente do feedback recebido nos Módulos 1 e 2 |

<div class="industry">

O checkpoint corresponde a 10% da nota final do semestre.

</div>

---

<!-- _class: summary -->

## Resumo da semana

- Árvore de decisão escolhe uma ação a partir de condições, sem memória de estado
- Nó, ramo, folha — avaliação da raiz até a ação
- Diferente da árvore de comportamento: sem tempo, sem sequenciamento
- Ordenação de testes afeta custo, não resultado
- Mapa de influência: nova pergunta ("onde ir?"), introdução apenas
- Micro Game Tactical AI iniciado; checkpoint do AI Playground realizado

---

## Preparação para a Semana 9

**Tema:** Mapas de Influência (aprofundamento) e Utility AI — encerramento do Módulo 3 e da Unidade III

- Confirmar árvore de decisão funcional em todos os grupos
- Revisar o conceito de campo escalar apresentado hoje

<div class="tip">

Três entregas na Semana 9: Desafio de Escolha Tecnológica, AI Design Log e terceiro momento de Engenharia Reversa.

</div>
