---
marp: true
paginate: true
theme: academic-course
size: 16:9
header: "Tecnologia em Jogos Digitais • Inteligência Artificial e Ilusão de Inteligência"
footer: "IFMS • Semana 03"
---

<!-- _class: cover -->

![logo](../themes/logo-ifms.svg)

# Inteligência Artificial e Ilusão de Inteligência

## Semana 3 — Aprofundamento da FSM: o padrão State em C#

<div class="meta">

**Módulo 1:** Como um NPC decide o que fazer?
**Apostila:** Parte II, Cap. 3 (aprofundamento)
**Micro Game:** NPC Decision

</div>

---

## Objetivos da aula

Ao final de hoje você será capaz de:

- explicar o problema de um `switch` de FSM que cresce demais;
- descrever a estrutura do padrão de projeto State (GoF);
- mapear estado, transição, evento e ação para o padrão State;
- refatorar a FSM da Semana 2 para o padrão State em C#;
- reconhecer o que essa refatoração resolve e o que ela não resolve.

---

## Antes de começar: mudança de rota

<div class="warning">

Esta turma **não vai estudar Máquinas de Estado Hierárquicas** (Capítulo 4) neste semestre. O Micro Game segue direto de FSM para Árvore de Comportamento, na Semana 4.

</div>

Hoje o assunto não é "como organizar hierarquicamente" — é "como organizar o **código**" da FSM que você já tem.

---

## Retomada da Semana 2

Você já tem uma FSM funcional: estados, transições, eventos e ações, implementados por `enum`/`switch` (ou já pelo padrão State, para quem escolheu esse caminho).

O que acontece com esse código quando o número de estados cresce?

---

<!-- _class: question -->

# Como estruturar o código da FSM para que ela cresça sem virar um emaranhado de condicionais?

O guarda tem cinco estados. Cada um com sua própria lógica de update. E tudo mora no mesmo `switch`.

---

## O problema: um método que cresce demais

Não é a quantidade de estados — é que **toda a lógica de todos os estados convive no mesmo lugar**.

<div class="warning">

Um `switch` com cinco `case`, cada um com dezenas de linhas, é difícil de ler, difícil de testar isoladamente e fácil de quebrar ao editar um caso vizinho.

</div>

---

## A resposta: o padrão de projeto State

Cada estado vira uma **classe própria**, que implementa uma interface comum.

- Uma interface `IState` com `Enter`, `Update`, `Exit`
- Uma classe concreta por estado (`PatrulharState`, `AtacarState`...)
- Um **contexto** — a FSM — que mantém o estado ativo e delega as chamadas

---

<!-- _class: diagram -->

## Estrutura do padrão State

<!--
FIGURA A PRODUZIR (nota do apresentador — não aparece no slide)

Objetivo didático:
Mostrar a estrutura do padrão State: interface IState, classes concretas de estado e o contexto (FSM) que mantém a referência ao estado ativo.
Arquivo sugerido:
assets/mermaid-1.png (substituir o diagrama atual, que ilustra os superestados da antiga Semana 3 — não usado mais nesta oferta)
Descrição:
Diagrama com uma interface IState no topo, três classes concretas apontando para ela (PatrulharState, AtacarState, FugirState) e uma classe FsmContext com uma seta para o estado ativo, indicando a delegação de Enter/Update/Exit.
Como produzir:
Gerar via Mermaid (classDiagram) e exportar como PNG, seguindo o padrão dos demais diagramas do curso.
-->

---

## Mapeando a Semana 2 para o padrão State

| Conceito (Semana 2) | Elemento no padrão State |
|---|---|
| **Estado** | Classe que implementa `IState` |
| **Ciclo enter/update/exit** | Métodos da interface `IState` |
| **Transição** | Chamada explícita de troca de estado no contexto |
| **Evento/guarda** | Condição avaliada dentro do `Update` do estado ativo |

---

## Exemplo: do `switch` à classe

```csharp
// Antes: um case dentro de um switch gigante
case EstadoGuarda.Atacar:
    if (vida < 0.2f) TrocarPara(EstadoGuarda.Fugir);
    AtacarJogador();
    break;
```

```csharp
// Depois: uma classe isolada
public class AtacarState : IState
{
    public void Enter(Guarda g) { }
    public void Update(Guarda g)
    {
        if (g.Vida < 0.2f) g.TrocarPara(new FugirState());
        g.AtacarJogador();
    }
    public void Exit(Guarda g) { }
}
```

---

## O que o padrão State melhora

- **Isolamento:** a lógica de "Atacar" só existe em `AtacarState`
- **Legibilidade:** cada arquivo tem uma responsabilidade só
- **Testabilidade:** dá para testar um estado sem montar a FSM inteira

---

<!-- _class: exercise -->

# O que o padrão State **não** resolve

<div class="objectives">

O número de regras de transição continua o mesmo — só está mais organizado. A explosão de transições, identificada na Semana 2, segue de pé.

</div>

---

<!-- _class: section -->

# Implementação guiada

Refatorando a FSM da Semana 2 para o padrão State.

---

## Passo a passo

1. Revisar como sua FSM foi implementada (Animator, `switch` ou já padrão State);
2. Definir a interface `IState` (ou equivalente) com Enter/Update/Exit;
3. Criar uma classe concreta para cada estado já existente;
4. Implementar o contexto (a FSM), que troca entre estados;
5. Testar: o comportamento deve ser **idêntico** ao de antes.

---

## O contexto: quem manda na troca

<div class="tip">

O estado decide **quando** pedir a troca (dentro do seu `Update`). O contexto (a FSM) é quem de fato **realiza** a troca, guardando a referência ao estado ativo.

</div>

---

<!-- _class: exercise -->

# Erro comum

Colocar toda a lógica de transição dentro de cada classe de estado, sem um contexto central que controle qual estado está ativo.

<div class="objectives">

Pergunta-chave: "quem guarda a referência ao estado ativo?" Se a resposta não for "o contexto", reveja o desenho.

</div>

---

## Discussão técnica: `switch` versus padrão State

Compare a legibilidade e a testabilidade do código antes e depois da refatoração.

<div class="warning">

A quantidade de transições escritas mudou? Não. O que ainda falta resolver é a mesma coisa de sempre: reordenar prioridades e reutilizar comportamento continuam trabalhosos — gancho para a Semana 4.

</div>

---

<!-- _class: summary -->

## Resumo da semana

- O `switch` de FSM cresce mal quando o número de estados aumenta
- O padrão State isola cada estado em sua própria classe
- Estado, transição, evento e ação mapeiam diretamente para a estrutura do padrão
- O contexto (a FSM) mantém o estado ativo e delega as chamadas
- A explosão de transições **continua sem solução** — não é isso que o padrão State resolve

---

## Preparação para a Semana 4

**Tema:** Árvores de Comportamento, Blackboard e Engenharia Reversa

- Ler o Capítulo 6 da Apostila (Árvores de Comportamento) e o Capítulo 14 (Engenharia Reversa)
- Trazer a FSM (padrão State) funcional implementada hoje, no Micro Game NPC Decision

<div class="tip">

Pergunta que abre a Semana 4: como tornar a decisão do NPC modular e escalável, migrando direto da FSM para uma Árvore de Comportamento?

</div>
