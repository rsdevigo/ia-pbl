# Plano de Aula — Semana 9

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 9 de 17 |
| **Unidade** | Unidade III — Tomada de Decisão Tática (Semanas 8–9) |
| **Módulo** | Módulo 3 — Como um NPC escolhe sua melhor ação? |
| **Tema** | Mapas de Influência e Utility AI |
| **Pergunta Norteadora** | Como um NPC escolhe sua melhor ação? (parte 2) |
| **Tipo de semana** | 🔴 Encerramento de módulo (Desafio de Escolha Tecnológica + Engenharia Reversa) |

---

## Objetivos de Aprendizagem

Ao final da Semana 9, o estudante deverá ser capaz de:

1. **Diferenciar** com precisão a pergunta do mapa de influência ("onde ir?") da pergunta do pathfinding, já consolidada no Módulo 2 ("como chegar?"), retomando a distinção introduzida na Semana 8.
2. **Definir** com precisão os conceitos de fonte, propagação e decaimento, e **explicar** como eles transformam pontos isolados em campos de decisão contínuos sobre o mapa.
3. **Comparar** o decaimento por distância euclidiana com o decaimento por distância de caminhada (propagação pela grade navegável), justificando por que o segundo é preferível para raciocínio tático fiel.
4. **Explicar** como camadas simples de influência (aliada, inimiga) se combinam por aritmética célula a célula em campos derivados — controle, tensão, vulnerabilidade, ameaça, segurança.
5. **Justificar** as técnicas que tornam a atualização do mapa de influência viável em tempo real — baixa frequência, atualização incremental, *time-slicing* e resolução reduzida — e reconhecer o erro de recalcular o campo inteiro a cada quadro.
6. **Explicar** o problema resolvido pela IA de Utilidade — escolher, entre múltiplos alvos candidatos (jogador, aliados), aquele que deve receber a ação do NPC, combinando distância, vida e ameaça em uma pontuação contínua — **continuando**, por combinação ponderada, a mesma seleção de alvo iniciada por testes encadeados na árvore de decisão da Semana 8, e **relacionar** essa lógica à combinação de camadas do mapa de influência.
7. **Justificar** por que não existe solução oficial da Unity equivalente a mapas de influência nem a Utility AI, e **implementar**, em C#, uma versão própria mínima de cada técnica.
8. **Consolidar**, em grupo, o Micro Game Tactical AI, integrando árvore de decisão (Semana 8), mapa de influência e Utility AI.
9. **Justificar** tecnicamente, por escrito e oralmente, a escolha de uma solução de tomada de decisão tática para um cenário proposto, no Desafio de Escolha Tecnológica do Módulo 3.
10. **Aplicar** o roteiro completo de seis etapas da metodologia de Engenharia Reversa de IA a um jogo comercial com decisão espacial ou por utilidade visível, distinguindo [Documentado], [Inferência] e [Especulação], e **confrontar** as próprias hipóteses com a análise publicada na Apostila (Capítulo 15).

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte IV, Capítulo 10 da Apostila — Mapas de Influência** (aprofundamento, seções 10.2 a 10.7) e à **Parte II, Capítulo 6, seções 6.7 e 6.8 — IA de utilidade (Utility AI)**, retomada aqui por afinidade de problema, com reutilização da metodologia da **Parte VII, Capítulo 14 — Metodologia de Engenharia Reversa de IA**, já apresentada na Semana 4 e aplicada de forma completa na Semana 7.

> **Nota de fonte.** A IA de utilidade **tem tratamento próprio na Apostila**: a seção 6.7 apresenta considerações, curvas de utilidade, combinação e seleção, e a seção 6.8 a situa no quadro comparativo FSM × HFSM × árvore de decisão × BT × GOAP × utilidade. Essa seção foi deliberadamente **não antecipada** na Semana 4 (ver o plano daquela semana) justamente para ser estudada aqui, ao lado dos mapas de influência, com os quais compartilha a lógica de combinação ponderada de fatores. A bibliografia básica (MILLINGTON; BOURG; SEEMANN) é complemento, e não fonte principal.


- retomada breve do problema (seção 10.1), já introduzido na Semana 8: "como chegar?" (pathfinding) versus "onde ir?" (mapa de influência);
- fundamentos aprofundados: campo escalar sobre o mapa; fonte, propagação e decaimento (seção 10.2.1); a fórmula direta e a propagação iterativa por vizinhança; decaimento por distância euclidiana versus distância de caminhada pela grade navegável — seção 10.2.1;
- combinação de camadas: influência (controle), tensão, vulnerabilidade/fronteira, ameaça e segurança, combinadas por soma ponderada célula a célula — seção 10.2.2;
- funcionamento e atualização em tempo real: coleta de fontes, recálculo do campo, combinação de camadas; as quatro técnicas que tornam a atualização viável — baixa frequência, atualização incremental, *time-slicing* e resolução reduzida — seção 10.3;
- exemplos: seleção de cobertura, avanço de exército, mapa de perigo via descida de gradiente e controle territorial — seção 10.4;
- vantagens (generalidade, integração de muitos fatores, comportamento emergente e crível, controle de autoria, reaproveitamento da base espacial) e limitações (custo de atualização, dilema de resolução, memória por camada, escalabilidade, limite conceitual de não substituir raciocínio individual/sequencial) — seção 10.5;
- jogos conhecidos: Age of Empires, Civilization, StarCraft — seção 10.6;
- ferramentas: ausência de sistema nativo da Unity; construção sobre grid, NavMesh/AI Navigation e C# (com Job System/Burst para escalar); o EQS da Unreal como termo de comparação — campo persistente e global versus consulta pontual e local — seção 10.7;
- IA de utilidade (seção 6.7): **considerações** normalizadas sobre cada alvo candidato (distância, vida, ameaça) — os três mesmos atributos já testados pela árvore de decisão da Semana 8, agora avaliados de forma contínua em vez de por testes binários; **curvas de utilidade** que transformam cada consideração em pontuação parcial (decaimento acentuado para distância, decréscimo linear para vida, degrau para ameaça — a forma da curva é a principal alavanca de design da técnica); **combinação** das parciais, por soma ponderada, em uma utilidade final por alvo; e **seleção** do alvo de maior valor — gulosa ou probabilística, esta última para evitar comportamento repetitivo;
- articulação entre as duas técnicas da semana: a IA de utilidade generaliza, para a escolha de **alvos**, a mesma lógica de combinação ponderada que o mapa de influência aplica à escolha de **posições** (retomando a nota da seção 10.2.2 sobre a proximidade entre elas), e o quadro da seção 6.8 situa ambas frente às arquiteturas discretas do Módulo 1; a Semana 9 substitui, assim, os testes sim/não da árvore de decisão (Semana 8) por uma pontuação gradual dos mesmos candidatos (jogador, aliados), sem alterar o problema resolvido — apenas a forma de resolvê-lo; ausência de solução oficial equivalente na Unity em ambos os casos, implementação própria em C#;
- reutilização da metodologia de Engenharia Reversa de IA (roteiro de seis etapas e rótulos [Documentado]/[Inferência]/[Especulação]), aplicada de forma completa a um terceiro caso — desta vez com a vantagem de o caso escolhido já estar analisado na Apostila (seção 15.7 ou 15.4), o que permite validar as hipóteses da turma contra fonte publicada.

Não deve ser antecipado o conteúdo da Unidade IV (Módulo 4 — Minimax e heurísticas): a transição de "como escolher a melhor ação" para "como derrotar um adversário inteligente" fica para a Semana 10. Também não é objetivo desta semana aprofundar a implementação de Behavior Trees (Módulo 1) ou de NavMesh/A* (Módulo 2): esses conceitos são retomados apenas como pano de fundo comparativo, quando pertinente.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte IV, Capítulo 10, completo (seções 10.1 a 10.7, com ênfase em 10.2 a 10.7, já que 10.1 e o início de 10.2 foram vistos na Semana 8); Parte II, Capítulo 6, **seções 6.7 e 6.8** (IA de utilidade e quadro comparativo); Parte VII, Capítulo 15, **seções 15.4 (The Sims) e 15.7 (Age of Empires / Civilization)**, como preparação do momento de Engenharia Reversa; revisão da Parte VII, Capítulo 14, seção 14.3 (roteiro de seis etapas). Complemento opcional na bibliografia básica (MILLINGTON, *AI for Games*; BOURG; SEEMANN, *AI for Game Developers*); **Apêndice C.1** (tabela-decisão) e **C.2** (tabela consolidada de arquiteturas) como apoio ao Desafio desta semana. *Observação:* a Parte IV é a única sem Encerramento próprio na Apostila — a consolidação do Capítulo 10 é feita pelo Apêndice C.2 |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o projeto AI Playground de cada grupo, com a árvore de decisão do Micro Game Tactical AI da Semana 8 implementada; acesso a vídeo ou build do jogo escolhido para o terceiro momento de Engenharia Reversa |
| **Cena Unity utilizada** | A mesma cena do Micro Game Tactical AI (Semana 8), estendida com uma grade simples de células (para o mapa de influência) e, se possível, mais de um NPC ou ponto de ameaça, permitindo observar propagação e decaimento de forma visível |
| **Assets** | Nenhum asset de arte adicional; reaproveita-se a cena e os scripts da Semana 8 |
| **Exemplos** | Diagrama de fonte, propagação e decaimento sobre uma grade com obstáculo (seção 10.2.1); diagrama de combinação de camadas — controle, tensão e fronteira (seção 10.2.2); quadro comparativo mapa de influência × EQS (seção 10.7); exemplo de IA de Utilidade que retoma os **mesmos alvos candidatos da árvore de decisão da Semana 8** (jogador, Aliado A, Aliado B) e os mesmos três atributos (distância, vida, ameaça), agora combinados por pesos e curvas de utilidade em vez de testes sim/não, mostrando que a IA de Utilidade pode escolher um alvo diferente do que a árvore escolheria para a mesma configuração |
| **Vídeos** | Recomenda-se, opcionalmente, uma captura de debug de um RTS mostrando a visualização de um mapa de calor de controle territorial, para tornar concreta a Seção 10.3 antes da implementação |
| **Jogos para Engenharia Reversa** | Escolher **um** dos dois casos já analisados na Apostila: ***Age of Empires*** ou ***Civilization*** (seção 15.7 — mapas de influência, eixo espacial) ou ***The Sims*** (seção 15.4 — IA de utilidade, eixo de ações). **Não usar *F.E.A.R.***: a Apostila o documenta como caso de GOAP (seção 15.2), técnica não estudada nesta disciplina — ver a nota na seção Engenharia Reversa deste plano. Manter a análise estritamente comportamental, conforme a seção 14.4 |

---

## Encontro 1 (1h30)

**Foco:** Aprofundamento de Mapas de Influência (fundamentos completos, combinação de camadas, atualização em tempo real, vantagens e limitações, ferramentas) e extensão conceitual para Utility AI.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Abertura e retomada | 5 min | Reconectar com a introdução da Semana 8 | Recapitula a distinção "como chegar?" versus "onde ir?" e o conceito inicial de campo escalar, fonte, propagação e decaimento, introduzidos na Semana 8 | Relembram, em voz alta, um exemplo próprio de decisão espacial levantado na semana anterior |
| 2. Fonte, propagação e decaimento em profundidade | 15 min | Aprofundar os três pilares do mapa de influência | Apresenta a seção 10.2.1 completa: fórmula direta versus propagação iterativa, e a distinção entre decaimento euclidiano e decaimento pela grade navegável, com o diagrama de fonte/obstáculo | Identificam, para a cena do Micro Game Tactical AI, se o decaimento deveria ser euclidiano ou pela grade, justificando a escolha |
| 3. Combinação de camadas | 20 min | Explicar como campos derivados nascem de camadas simples | Apresenta a seção 10.2.2: influência/controle, tensão, vulnerabilidade/fronteira, ameaça e segurança, com o diagrama de camadas sobrepostas e a ideia de soma ponderada | Calculam manualmente, para um exemplo simples de grade com poucas células, os valores de controle e tensão a partir de camadas aliada e inimiga fornecidas pelo professor |
| 4. Atualização em tempo real | 15 min | Explicar o compromisso entre atualidade e custo | Apresenta a seção 10.3: baixa frequência, atualização incremental, *time-slicing* e resolução reduzida; retoma o Erro Comum de recalcular tudo a cada quadro | Discutem, em duplas, qual frequência de atualização seria adequada para o próprio Micro Game Tactical AI, e por quê |
| 5. Exemplos, jogos conhecidos, vantagens, limitações e ferramentas | 12 min | Consolidar o balanço da técnica, situar sua implementação na Unity e mostrar aplicações reais | Apresenta rapidamente a seção 10.4 (exemplos: seleção de cobertura, avanço de exército, mapa de perigo via descida de gradiente, controle territorial) e a seção 10.6 (jogos conhecidos: *Age of Empires*, *Civilization*, *StarCraft*), depois a seção 10.5 (vantagens e limitações) e a seção 10.7 (ausência de sistema nativo da Unity; construção sobre grid, NavMesh e C#; comparação com o EQS da Unreal — campo persistente e global versus consulta pontual e local) | Relacionam cada um dos quatro exemplos da seção 10.4 a uma situação do próprio AI Playground, e a ausência de solução oficial da Unity ao caráter "artesanal e específico do jogo" da técnica, discutido na seção 10.7 |
| 6. Do mapa de influência à Utility AI | 13 min | Estender a lógica de combinação ponderada da escolha de posições para a escolha de alvos, continuando a seleção de alvo da Semana 8 | Apresenta o problema da IA de Utilidade retomando explicitamente os candidatos e os três atributos já usados pela árvore de decisão da Semana 8 (jogador e aliados; distância, vida, ameaça): em vez de testes sim/não, cada candidato recebe uma pontuação contínua por consideração, combinada por soma ponderada em uma utilidade final — o alvo de maior utilidade é o escolhido; apresenta também o conceito de curva de utilidade (linear, acelerada, em degrau), retomando explicitamente a nota da seção 10.2.2 sobre a proximidade entre mapa de influência e IA de utilidade | Preenchem, em grupo, uma tabela de considerações e pesos para os mesmos alvos candidatos (jogador, aliados) já usados na árvore de decisão da Semana 8, calculando a utilidade de cada um e comparando o alvo escolhido pela utilidade com o alvo que a árvore de decisão escolheria para a mesma configuração |
| 7. Ferramentas para Utility AI | 5 min | Situar a ausência de solução oficial equivalente | Reforça que, como o mapa de influência, a IA de Utilidade não possui pacote oficial da Unity, sendo implementada em C# como serviço consultado pelos NPCs | Registram a decisão de implementar a IA de Utilidade em C#, reaproveitando a estrutura de scripts já usada nos módulos anteriores |
| 8. Encerramento e preparação do Encontro 2 | 5 min | Orientar a consolidação prática | Anuncia que o Encontro 2 implementará o mapa de influência e/ou a IA de Utilidade no Micro Game Tactical AI, aplicará o Desafio de Escolha Tecnológica e realizará o terceiro momento de Engenharia Reversa | Organizam-se em grupo, decidindo qual das duas técnicas (mapa de influência, IA de utilidade, ou ambas) será priorizada na implementação, conforme o escopo do NPC já definido na Semana 8 |

---

## Encontro 2 (1h30)

**Foco:** Consolidação do Micro Game Tactical AI. Desafio de Escolha Tecnológica do Módulo 3. Terceiro momento de Engenharia Reversa, em jogo com IA tática visível.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Revisão rápida | 5 min | Retomar os conceitos do Encontro 1 antes da prática | Conduz uma discussão breve recuperando fonte, propagação, decaimento, combinação de camadas e a lógica de utilidade ponderada | Respondem perguntas de verificação oral, relacionando os conceitos ao NPC do Micro Game Tactical AI |
| 2. Implementação guiada em C# | 35 min | Consolidar o Micro Game Tactical AI com mapa de influência e/ou Utility AI | Acompanha os grupos na implementação de uma grade simples de influência (fontes, propagação, decaimento) e/ou de uma função de utilidade ponderada para seleção de ação, integrando ao NPC já dotado de árvore de decisão desde a Semana 8 | Implementam, em grupo, o mapa de influência e/ou a IA de utilidade em C#, testando o comportamento resultante do NPC do Micro Game Tactical AI |
| 3. Discussão técnica | 10 min | Consolidar a compreensão da implementação realizada | Conduz a discussão sobre a frequência de atualização escolhida por cada grupo e sobre os pesos definidos na função de utilidade, relacionando-os às seções 10.3 e à combinação ponderada de considerações | Justificam, em voz alta, a frequência de atualização e os pesos escolhidos para a própria solução |
| 4. Desafio de Escolha Tecnológica do Módulo 3 | 15 min | Desenvolver a capacidade de justificar tecnicamente uma escolha de tomada de decisão tática | Apresenta um cenário não idêntico ao Micro Game (por exemplo, um esquadrão de NPCs que precisa decidir, simultaneamente, quem avança, quem cobre e quem recua) e solicita que cada grupo compare ao menos duas soluções (árvore de decisão, mapa de influência, IA de utilidade) e justifique a escolhida | Analisam o cenário, comparam alternativas com base em requisitos e limitações, e registram a justificativa por escrito |
| 5. Terceiro momento de Engenharia Reversa | 20 min | Aplicar o roteiro completo de seis etapas a um caso de decisão tática | Apresenta trechos de vídeo ou sessão ao vivo do jogo escolhido (*Age of Empires*/*Civilization* ou *The Sims*), conduz a definição do problema e a observação orientada — distribuição espacial de forças ou balanço de necessidades concorrentes —, e orienta a formulação, validação e documentação das hipóteses; na etapa de validação, confronta as hipóteses da turma com a análise da Apostila (seção 15.7 ou 15.4), reforçando os rótulos [Documentado]/[Inferência]/[Especulação] | Aplicam as seis etapas do roteiro ao comportamento observado, com nível de confiança explícito para cada afirmação, e comparam suas hipóteses com a análise publicada |
| 6. Encerramento do Módulo 3 e da Unidade III | 5 min | Fechar o módulo e indicar o caminho da próxima semana | Recapitula a evolução de árvore de decisão (Semana 8) a mapa de influência e Utility AI (Semana 9), confirma as entregas da semana e anuncia que a Semana 10 abre a Unidade IV com Minimax | Registram pendências das quatro entregas do módulo para finalização até o prazo definido pelo professor |

---

## Micro Game

**Micro Game em desenvolvimento:** Tactical AI (Módulo 3) — **consolidação final**.

**Objetivo pedagógico:** demonstrar como um NPC escolhe entre múltiplos alvos candidatos (jogador, aliados) aquele que deve receber sua ação, evoluindo da estrutura mais simples e transparente dessa família de técnicas — a árvore de decisão de seleção de alvo por testes sim/não (Semana 8) — até uma seleção do mesmo alvo por combinação ponderada e contínua de distância, vida e ameaça — a IA de Utilidade —, apoiada pelo mapa de influência como avaliação espacial complementar (onde se posicionar em relação ao alvo escolhido), consolidando o Módulo 3 do AI Playground.

**Funcionalidades esperadas ao final da Semana 9:**

- a árvore de decisão de seleção de alvo do NPC (Semana 8), preservada e comparável a, no mínimo, uma das duas técnicas desta semana: um mapa de influência simples (grade com fontes, propagação e decaimento, atualizado em baixa frequência) e/ou uma função de utilidade ponderada que avalie os **mesmos alvos candidatos da Semana 8** (jogador, aliados) pelos **mesmos três atributos** (distância, vida, ameaça), agora combinados por pesos e curvas de utilidade em vez de testes encadeados;
- capacidade do grupo de explicar, para uma configuração dada de alvos e do ambiente, qual alvo (e, se aplicável, qual célula) seria escolhido e por quê, comparando o resultado da árvore de decisão com o da função de utilidade para o mesmo cenário;
- capacidade do grupo de justificar os pesos, as curvas de utilidade e/ou a frequência de atualização escolhidos;
- documentação consolidada do raciocínio do módulo no AI Design Log, registrando explicitamente os casos em que a árvore de decisão e a IA de Utilidade escolheriam alvos diferentes, e por quê.

**Relação com módulos anteriores:** encerra a trajetória iniciada na Semana 8 (árvore de decisão de seleção de alvo), demonstrando que a escolha do melhor alvo para um NPC pode ir de uma estrutura condicional simples a uma avaliação ponderada e contínua dos mesmos fatores — sem trocar o problema resolvido, apenas a forma de resolvê-lo. Reaproveita, quando pertinente, a mesma cena, os mesmos alvos candidatos e o mesmo NPC do Micro Game Tactical AI iniciado na Semana 8, e prepara o terreno conceitual para a função de avaliação do Minimax, no Módulo 4.

---

## Engenharia Reversa

**Terceiro momento formal de Engenharia Reversa da disciplina**, conforme o Cronograma, aplicando o roteiro completo de seis etapas da seção 14.3 da Apostila.

**Jogo analisado:** o professor escolhe **um** dos dois eixos do módulo, ambos com estudo de caso próprio na Apostila:

- **Eixo espacial — *Age of Empires* (Ensemble Studios, 1997) ou *Civilization*.** Caso de manual de mapas de influência, analisado na seção 15.7. O uso de camadas de influência em *Age of Empires* tem base documental (relatos de Dave Pottinger e da Ensemble), classificada pela Apostila como [Documentado / Inferência forte]; a arquitetura interna de *Civilization* é majoritariamente [Inferência].
- **Eixo de ações — *The Sims* (Maxis, 2000).** Caso canônico de IA de utilidade, analisado na seção 15.4, com a arquitetura de objetos inteligentes descrita pelos próprios criadores. Tem a vantagem rara de expor a função de utilidade na própria interface, por meio dos medidores de necessidade.

> **Atenção — mudança em relação a versões anteriores deste plano.** *F.E.A.R.* **não** deve ser usado como caso deste módulo. A Apostila o documenta na seção 15.2 como caso canônico de **GOAP** — planejamento orientado a objetivos, seção 6.6, conteúdo de aprofundamento não estudado nesta disciplina —, com base na palestra de Jeff Orkin (GDC 2006) e rótulo explícito [Documentado]. Pedir aos estudantes que hipotetizem entre mapa de influência e IA de utilidade para um comportamento cuja arquitetura já está documentada como outra coisa contraria a disciplina metodológica de separar fato documentado de inferência que o Capítulo 14 e esta própria atividade pretendem treinar. *F.E.A.R.* permanece disponível como caso de contraste na Semana 17, justamente por ser o exemplo em que a hipótese intuitiva ("parece um esquadrão coordenado") é refutada pela documentação.

**Comportamento observado:**

- em *Age of Empires* / *Civilization*: onde a IA concentra ataques, de que regiões recua, onde escolhe expandir, e como essas decisões mudam conforme a distribuição de forças no mapa;
- em *The Sims*: como um Sim sem ordens do jogador escolhe entre comer, dormir, socializar e higiene, e como essa escolha muda conforme os medidores de necessidade se esgotam.

**Perguntas para discussão:**

- A decisão observada parece avaliar múltiplos fatores simultaneamente e de forma **gradual**, ou seguir um critério único e binário? Que evidência distingue os dois casos?
- O comportamento é mais compatível com uma avaliação **espacial** ("onde agir", mapa de influência) ou com uma avaliação de **ações concorrentes** ("o que fazer", IA de utilidade)? O que no comportamento observado permite separar as duas?
- Há indício de reavaliação contínua conforme a situação muda, ou a escolha parece feita uma vez e mantida?
- No eixo espacial: a força da IA vem de avaliação genuína ou de **bônus assimétricos** de dificuldade? A seção 15.7 alerta que distinguir competência de compensação é parte da análise honesta.
- Que evidências sustentam a hipótese, e com que confiança? O que é [Documentado] pelos relatos públicos dos estúdios e o que permanece [Inferência] ou [Especulação]?

**Relação com os conceitos da semana:** aplica o roteiro completo de seis etapas (definição do problema, coleta de evidências, registro das observações, formulação de hipóteses, validação e documentação), já reutilizado nas Semanas 4 e 7, exercitando agora o vocabulário de fonte, propagação, decaimento, combinação de camadas (Cap. 10) e de considerações, curvas de utilidade e seleção (seção 6.7) construído nesta semana. Como ambos os casos estão analisados na Apostila, o professor pode confrontar diretamente as hipóteses da turma com a análise do Capítulo 15 na etapa 5 do roteiro — a etapa de validação, que nos momentos anteriores costuma ficar mais frágil por falta de fonte.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Scripting C#** | Implementação própria do mapa de influência (grid, fontes, propagação, decaimento, combinação de camadas) e/ou da função de utilidade ponderada, já que não há solução oficial da Unity equivalente a nenhuma das duas técnicas |
| **AI Navigation / NavMesh** (retomado) | Referenciado apenas como possível base topológica para a propagação do mapa de influência (distância de caminhada em vez de distância euclidiana), sem uso obrigatório nesta semana |
| **Unity Job System / Burst** (mencionado) | Citado como recurso de desempenho para escalar o cálculo do mapa de influência em mapas maiores, sem uso prático obrigatório no escopo reduzido do Micro Game |
| **EQS da Unreal** (comparação conceitual) | Utilizado apenas como termo de comparação (campo persistente e global versus consulta pontual e local), sem uso prático nesta semana |

Nenhuma ferramenta oficial da Unity é utilizada para mapa de influência ou Utility AI nesta semana: ambas as técnicas são implementações próprias em C#, conforme indicado pelo Cronograma e pela Apostila.

---

## Atividade de Laboratório

**Objetivo:** consolidar o Micro Game Tactical AI como entrega do Módulo 3, implementando um mapa de influência simples e/ou uma função de utilidade ponderada, aplicar o Desafio de Escolha Tecnológica a um cenário de esquadrão e concluir o terceiro momento de Engenharia Reversa.

**Etapas:**

1. Definir, em grupo, se o Micro Game Tactical AI será estendido com mapa de influência, com IA de Utilidade, ou com ambos, conforme o escopo do NPC já implementado na Semana 8.
2. Para o mapa de influência: implementar uma grade simples com ao menos uma fonte de influência (por exemplo, o jogador ou um ponto de ameaça), propagação por vizinhança e decaimento, atualizada em baixa frequência.
3. Para a IA de Utilidade: reutilizar os mesmos alvos candidatos e os três atributos já usados na árvore de decisão da Semana 8 (distância, vida, ameaça), atribuir pesos e uma curva a cada consideração, e calcular a utilidade de cada alvo, escolhendo o de maior valor; comparar o resultado com o que a árvore de decisão escolheria para a mesma configuração.
4. Testar o comportamento resultante do NPC, verificando se a escolha de célula (mapa de influência) e/ou de alvo (Utility AI) reflete corretamente as mudanças no ambiente.
5. Analisar o cenário do Desafio de Escolha Tecnológica (esquadrão que decide simultaneamente quem avança, quem cobre e quem recua), comparar ao menos duas soluções possíveis e registrar a justificativa por escrito.
6. Aplicar as seis etapas do roteiro de Engenharia Reversa ao comportamento tático observado no jogo escolhido, registrando evidências, hipóteses, validação e documentação com os rótulos de confiança apropriados.
7. Reunir as quatro entregas do módulo: Micro Game consolidado, AI Design Log, Desafio de Escolha Tecnológica e Engenharia Reversa do Módulo 3.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter o Micro Game Tactical AI consolidado como entrega do Módulo 3 — com árvore de decisão, mapa de influência e/ou Utility AI integrados —, uma justificativa técnica registrada para o cenário do Desafio de Escolha Tecnológica, e o registro completo das seis etapas de Engenharia Reversa aplicadas ao jogo escolhido.

---

## Verificação da Aprendizagem

A Semana 9 **encerra formalmente o Módulo 3 e a Unidade III**, e a verificação da aprendizagem gera nota, conforme os Critérios de Notas da disciplina. O professor deve aplicar a Rubrica de Avaliação aos quatro instrumentos previstos:

- **Micro Game (consolidação)** — avaliado principalmente por Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução, observando se o mapa de influência e/ou a IA de Utilidade produzem o comportamento esperado e se a implementação própria em C# está bem organizada, já que não há solução oficial da Unity a avaliar (peso 50% do módulo);
- **AI Design Log** — avaliado pelo critério de AI Design Log, verificando se o documento registra problema, alternativas consideradas ao longo do módulo (árvore de decisão, mapa de influência, IA de utilidade), solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras (peso 25% do módulo);
- **Desafio de Escolha Tecnológica** — avaliado principalmente por Tomada de Decisão, apoiado por Compreensão Conceitual, verificando se o grupo comparou alternativas viáveis para o cenário de esquadrão proposto e justificou tecnicamente a escolha (peso 15% do módulo);
- **Engenharia Reversa** — avaliado por Compreensão Conceitual e Tomada de Decisão, verificando a qualidade das hipóteses formuladas sobre a decisão tática observada em *Age of Empires*/*Civilization* ou *The Sims* e o uso correto dos rótulos [Documentado]/[Inferência]/[Especulação] (peso 10% do módulo).

A nota do Módulo 3 compõe 11,67% da nota final do semestre, conforme os Critérios de Notas. O professor deve registrar e comunicar aos estudantes a nota obtida em cada instrumento e a nota consolidada do módulo, conforme recomendado pela Rubrica, dando atenção especial ao critério de Evolução ao Longo do Semestre em relação ao checkpoint da Semana 8.


**Instrumentos de verificação disponíveis na Apostila.** Antes de recorrer a questões próprias, o professor deve usar o material já pronto e alinhado: os **Exercícios de fixação** ao final do Capítulo 10, e — nas semanas de encerramento de Parte — as **Questões de Revisão**, os **Exercícios Conceituais** e os **Exercícios de Integração** do Encerramento correspondente. Recomenda-se aplicar duas ou três questões na abertura do Encontro 2, como verificação rápida antes do laboratório, e usar o Apêndice C.2 como apoio à discussão técnica. Esse material é a principal fonte de verificação formativa da disciplina, e não deve ficar sem uso.

---

## Entregas

Conforme o Cronograma e a matriz dos Critérios de Notas (item 4), esta semana encerra o Módulo 3 e a Unidade III com **quatro** entregas avaliadas:

- **Micro Game 3 — Tactical AI consolidado (50%)** — árvore de decisão da Semana 8 acrescida de mapa de influência e/ou Utility AI implementados em C#, avaliado pelos critérios de Compreensão Conceitual, Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução;
- **AI Design Log — Micro Game 3 (25%)** — documento contendo problema, requisitos, alternativas consideradas (árvore de decisão, mapa de influência, IA de utilidade), solução escolhida, justificativa, ferramentas utilizadas, limitações e melhorias futuras, conforme o modelo dos Modelos de Entrega do Aluno (§1);
- **Desafio de Escolha Tecnológica — Módulo 3 (15%)** — justificativa escrita comparando ao menos duas alternativas de tomada de decisão tática para o cenário de esquadrão apresentado no Encontro 2;
- **3º momento de Engenharia Reversa (10%)** — registro completo das seis etapas do roteiro aplicado ao caso escolhido: *Age of Empires*/*Civilization* (seção 15.7) ou *The Sims* (seção 15.4).

O Micro Game Tactical AI permanece no AI Playground de cada grupo como base para os módulos seguintes, mas a versão consolidada nesta semana é **entrega formal avaliada**, e não apenas um artefato de trabalho.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir mapa de influência com a grade de navegação (NavMesh) já estudada no Módulo 2, tratando-os como o mesmo sistema por compartilharem a grade como suporte | Retomar o quadro de Atenção da seção 10.2, reforçando que a grade de navegação responde "posso ir?" (topológico) e o mapa de influência responde "vale a pena ir?" (avaliativo) |
| Usar decaimento por distância euclidiana sem perceber que a influência "atravessa" paredes, produzindo avaliações táticas incorretas | Retomar o Atenção da seção 10.2.1 e pedir que o grupo teste o campo com um obstáculo entre a fonte e a célula avaliada, comparando os dois tipos de decaimento |
| Recalcular o mapa de influência inteiro a cada quadro, sem aplicar nenhuma das quatro técnicas de viabilização | Retomar o Erro Comum da seção 10.3 e exigir que o grupo justifique, por escrito, a frequência de atualização escolhida para o próprio Micro Game |
| Atribuir pesos arbitrários à função de utilidade, sem justificar por que uma consideração pesa mais que outra | Retomar a lógica de "controle de autoria por pesos" da seção 10.2.2 e pedir que o grupo justifique cada peso em termos do comportamento tático desejado para o NPC |
| Na Engenharia Reversa, atribuir a posicionamento tático observado uma arquitetura mais sofisticada do que a evidência sustenta | Retomar o Erro Comum da seção 14.2.3 (navalha de Occam) e pedir que o grupo distinga, com os rótulos [Documentado]/[Inferência]/[Especulação], o que é garantido pelas fontes públicas e o que é hipótese própria |

---

## Preparação para a Próxima Semana

Para a Semana 10 (Minimax e Busca Adversarial — abertura da Unidade IV), o professor deve:

- garantir que as quatro entregas do Módulo 3 (Micro Game consolidado, AI Design Log, Desafio de Escolha Tecnológica, Engenharia Reversa) estejam recebidas e avaliadas antes do início da Semana 10, registrando a nota do módulo conforme a matriz dos Critérios de Notas (item 4);
- confirmar que todos os grupos possuem, ao final da Semana 9, o Micro Game Tactical AI consolidado no AI Playground, encerrando o Módulo 3 e a Unidade III;
- solicitar a leitura prévia da Parte V, Capítulo 11 da Apostila (Minimax e Busca Adversarial);
- anunciar a transição de unidade: da pergunta "como um NPC escolhe sua melhor ação?" para "como derrotar um adversário inteligente?", situando o Minimax como uma nova família de problemas — decisão em jogos de dois lados —, e não uma continuação direta do Módulo 3;
- destacar aos estudantes que o Micro Game Board Game AI (Semana 10) será uma implementação própria em C#, já que não há solução oficial da Unity para busca adversarial, retomando o padrão de implementação própria já exercitado nesta semana com o mapa de influência e a IA de Utilidade.
