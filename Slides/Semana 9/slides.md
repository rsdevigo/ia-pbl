---
marp: true
paginate: true
theme: academic-course
size: 16:9
header: "Tecnologia em Jogos Digitais • Inteligência Artificial e Ilusão de Inteligência"
footer: "IFMS • Semana 09"
---

<!-- _class: cover -->

![logo](https://dummyimage.com/280x90/ffffff/3b2f68&text=IFMS)

# Inteligência Artificial e Ilusão de Inteligência

## Semana 9 — Mapas de Influência (aprofundamento) e Utility AI

<div class="meta">

**Módulo 3:** Como um NPC escolhe sua melhor ação?
**Apostila:** Parte IV, Cap. 10 (10.2–10.7); extensão Utility AI
**Micro Game:** Tactical AI (consolidação)

</div>

---

## Objetivos da aula

Ao final de hoje você será capaz de:

- explicar fonte, propagação e decaimento de um campo de influência;
- comparar decaimento euclidiano com decaimento pela grade navegável;
- descrever a combinação de camadas em campos derivados (controle, tensão, ameaça);
- justificar as técnicas que viabilizam a atualização em tempo real;
- relacionar a IA de Utilidade à mesma lógica de combinação ponderada.

---

## Retomada da Semana 8

**Semana 8:** árvore de decisão escolhe uma ação a partir de condições — introdução ao mapa de influência.

**Pergunta em aberto:** "posso ir?" (NavMesh, Módulo 2) já foi respondida. Hoje: "vale a pena ir?"

<div class="tip">

O mapa de influência responde a uma pergunta avaliativa, não topológica.

</div>

---

<!-- _class: question -->

# Como um NPC escolhe sua melhor ação?

Parte 2 — avaliando múltiplas condições ao mesmo tempo, de forma ponderada.

---

## Fonte, propagação e decaimento

- **Fonte:** ponto de origem do valor de influência;
- **Propagação:** espalhamento por vizinhança, célula a célula;
- **Decaimento:** redução do valor com a distância da fonte.

Duas formas de medir distância: **euclidiana** ou pela **grade navegável** (distância de caminhada).

---

<!-- _class: diagram -->

## Decaimento euclidiano × decaimento pela grade

![diagram](assets/mermaid-1.png)

A distância euclidiana ignora obstáculos; a distância pela grade produz avaliação tática fiel.

---

<div class="warning">

**Erro comum:** usar decaimento euclidiano sem perceber que a influência "atravessa" paredes, produzindo avaliações táticas incorretas.

</div>

---

## Combinação de camadas

Camadas simples (aliada, inimiga) se combinam por **soma ponderada célula a célula**.

| Camada derivada | Origem |
|---|---|
| Controle | Influência aliada − inimiga |
| Tensão | Proximidade entre forças opostas |
| Ameaça / Segurança | Camada inimiga isolada / invertida |

---

## Atualização em tempo real

Recalcular o campo inteiro a cada quadro é inviável.

| Técnica | Ideia |
|---|---|
| Baixa frequência | Atualizar a cada N quadros |
| Atualização incremental | Recalcular apenas o que mudou |
| *Time-slicing* | Dividir o cálculo ao longo de vários quadros |
| Resolução reduzida | Grade mais grosseira que a de navegação |

---

<div class="warning">

**Erro comum:** recalcular o mapa de influência inteiro a cada quadro, ignorando as quatro técnicas de viabilização.

</div>

---

## Vantagens e limitações

| Vantagens | Limitações |
|---|---|
| Generalidade e integração de fatores | Custo de atualização |
| Comportamento emergente e crível | Dilema de resolução |
| Controle de autoria (pesos) | Memória por camada, escalabilidade |

---

## Ferramentas

| Situação | Solução |
|---|---|
| Mapa de influência nativo | **Não existe ferramenta dedicada na Unity** |
| Implementação | C# sobre grid / NavMesh (Job System/Burst para escalar) |
| Termo de comparação | EQS da Unreal — campo persistente e global × consulta pontual |

---

<!-- _class: question -->

# Da posição à ação

O mapa de influência escolhe **onde ir**. E entre várias ações, qual escolher?

---

## Utility AI: mesma lógica, novo alvo

IA de Utilidade combina considerações ponderadas (saúde, distância, munição) para escolher a **ação** de maior valor.

<div class="tip">

É a mesma lógica de combinação ponderada do mapa de influência — aplicada a ações, não a posições.

</div>

---

## Exemplo: três ações candidatas

| Ação | Saúde | Distância | Munição | Utilidade |
|---|---|---|---|---|
| Atacar | baixa | alta | alta | média |
| Recuar | alta | — | — | alta |
| Buscar cobertura | média | média | baixa | média-alta |

A ação de maior valor combinado é escolhida.

---

## Ferramentas para Utility AI

Assim como o mapa de influência, **não há pacote oficial da Unity** para Utility AI.

Implementação própria em C#, como serviço consultado pelos NPCs.

---

<div class="warning">

**Erro comum:** atribuir pesos arbitrários à função de utilidade, sem justificar por que uma consideração pesa mais que outra.

</div>

---

<!-- _class: exercise -->

# Erro comum

Confundir o mapa de influência com a grade de navegação (NavMesh) do Módulo 2, por compartilharem a grade como suporte.

<div class="objectives">

A grade de navegação responde "posso ir?" (topológico). O mapa de influência responde "vale a pena ir?" (avaliativo).

</div>

---

<!-- _class: section -->

# Micro Game Tactical AI — consolidação

Árvore de decisão (Semana 8) + mapa de influência e/ou Utility AI.

---

## O que implementar hoje

- grade simples com ao menos uma fonte de influência, propagação e decaimento em baixa frequência; **e/ou**
- função de utilidade ponderada para ao menos três ações candidatas;
- integração com a árvore de decisão já implementada na Semana 8;
- justificativa dos pesos e/ou da frequência de atualização escolhidos.

> [!FIGURA]
>
> **Objetivo didático**
>
> Tornar visível, antes da implementação, como fonte, propagação e decaimento se distribuem sobre uma grade com obstáculo.
>
> **Arquivo sugerido**
>
> ```
> assets/mapa-influencia-grade.webp
> ```
>
> **Descrição**
>
> Grade de células coloridas por intensidade de influência, com uma fonte destacada, um obstáculo interrompendo a propagação e uma legenda de decaimento por cor.
>
> **Como produzir**
>
> Captura de tela do próprio Micro Game em modo debug (visualização da grade via Gizmos no Unity), com anotações adicionadas no Krita.

---

<!-- _class: section -->

# Desafio de Escolha Tecnológica — Módulo 3

Cenário: um esquadrão de NPCs decide, simultaneamente, quem avança, quem cobre e quem recua.

---

## O que é esperado

Comparar ao menos **duas soluções** (árvore de decisão, mapa de influência, IA de utilidade) e justificar a escolha, considerando:

- requisitos do cenário;
- limitações de cada abordagem;
- ferramentas disponíveis;
- contexto do AI Playground do grupo.

---

<!-- _class: section -->

# 3º Momento de Engenharia Reversa

Jogo sugerido: **F.E.A.R.** (Monolith Productions, 2005) — posicionamento tático documentado por Jeff Orkin (GDC 2006).

---

## Perguntas para observação

- As posições escolhidas avaliam múltiplos fatores ao mesmo tempo, ou um critério único?
- Há reavaliação contínua da posição, ou a escolha é feita uma vez só?
- O comportamento é mais compatível com avaliação espacial, de ações, ou ambas?

<div class="industry">

Aplicar os rótulos [Documentado] / [Inferência] / [Especulação] a cada hipótese.

</div>

---

<!-- _class: summary -->

## Resumo da semana

- Fonte, propagação e decaimento formam o campo escalar do mapa de influência
- Decaimento pela grade navegável é preferível ao euclidiano para fidelidade tática
- Camadas simples se combinam por soma ponderada em campos derivados
- Atualização viável exige baixa frequência, incremental, *time-slicing* ou resolução reduzida
- Utility AI generaliza a combinação ponderada da escolha de posições para a escolha de ações
- Nenhuma das duas técnicas possui solução oficial da Unity — implementação própria em C#
- Módulo 3 e Unidade III encerrados: Micro Game, Desafio e Engenharia Reversa entregues

---

## Preparação para a Semana 10

**Tema:** Minimax e Busca Adversarial — abertura da Unidade IV

- Leitura prévia da Parte V, Cap. 11 da Apostila
- Nova pergunta: "como derrotar um adversário inteligente?" — não é continuação direta do Módulo 3

<div class="tip">

O Micro Game Board Game AI será implementação própria em C#, sem solução oficial da Unity para busca adversarial.

</div>
