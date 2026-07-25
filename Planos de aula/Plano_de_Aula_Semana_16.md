# Plano de Aula — Semana 16

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 16 de 17 |
| **Unidade** | Unidade VI — Aprendizagem e Adaptação (Semanas 14–16) |
| **Módulo** | Módulo 6 — Como um agente aprende? |
| **Tema** | Inferência com Sentis e consolidação |
| **Pergunta Norteadora** | Como um agente aprende? (parte 3) |
| **Tipo de semana** | 🔴 Semana de encerramento de módulo — Desafio de Escolha Tecnológica (M6) e Engenharia Reversa |

---

## Objetivos de Aprendizagem

Ao final da Semana 16, o estudante deverá ser capaz de:

1. **Explicar** o papel do Unity Sentis no ciclo de aprendizagem por reforço, distinguindo claramente a etapa de treinamento (ML-Agents, Semana 15) da etapa de inferência/execução (Sentis, seção 12.9).
2. **Importar** um modelo treinado (`.onnx`) no Sentis e **configurar** um componente de inferência que substitua a política de decisão do agente em tempo de execução, sem o motor Python de treinamento.
3. **Executar** o agente do Micro Game Adaptive AI de forma autônoma, com decisões tomadas pelo modelo treinado via Sentis, e **comparar** esse comportamento ao observado durante o treinamento (Semana 15).
4. **Consolidar** o Micro Game Adaptive AI como parte funcional do AI Playground, integrando as decisões conceituais das Semanas 14 e 15 à execução final.
5. **Justificar tecnicamente**, no Desafio de Escolha Tecnológica do Módulo 6, a escolha entre Aprendizagem por Reforço (ML-Agents/Sentis) e abordagens mais simples (FSM, Utility AI, scripts determinísticos) para um cenário de IA adaptativa proposto.
6. **Analisar criticamente**, no sexto momento de Engenharia Reversa, um jogo comercial com IA adaptativa ou aprendizado perceptível pelo jogador, relacionando o comportamento observado aos conceitos de Aprendizagem por Reforço estudados nas Semanas 14–16.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte VI, Capítulo 12 da Apostila — Aprendizagem por Reforço (aplicação) e introdução ao Sentis**:

- Unity Sentis como solução oficial da Unity para inferência de modelos treinados dentro do próprio motor, sem dependência do ambiente Python de treinamento — seção 12.9 (parte de inferência);
- o ciclo completo do Módulo 6: planejamento de estado/ação/recompensa (Semana 14) → treinamento via ML-Agents (Semana 15) → inferência via Sentis (Semana 16);
- vantagens e limitações do uso de Aprendizagem por Reforço em produção, em contraste com soluções determinísticas mais simples — seção 12.10;
- síntese do Módulo 6 a partir dos estudos de caso comentados da Apostila — seção 12.11.

Não é objetivo desta semana retomar o treinamento em si (Q-Learning, hiperparâmetros, curva de recompensa), já consolidado na Semana 15, nem antecipar conteúdo da Semana 17.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte VI, Capítulo 12, seção 12.9 completa (foco na parte de inferência com Sentis), seção 12.10 (Vantagens e Limitações) e seção 12.11 (Estudos de Caso Comentados); **Encerramento da Parte VI**, que só agora pode ser lido por completo (Capítulos 12 e 13 vistos), com destaque para a *Tabela Comparativa — Q-Learning × Deep RL × Algoritmos Genéticos*, que fecha a comparação "otimizar × aprender a agir" aberta na Semana 13; **Apêndice C.1** e **C.2** como apoio ao Desafio |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub e o pacote Sentis importado; modelo `.onnx` e curva de recompensa preservados por cada grupo na Semana 15; formulário ou roteiro do Desafio de Escolha Tecnológica já utilizado nos módulos anteriores |
| **Cena Unity utilizada** | Cena do Micro Game Adaptive AI já treinada na Semana 15, agora recebendo o componente de inferência do Sentis em substituição ao vínculo com o ML-Agents/Python |
| **Assets** | Nenhum asset de arte adicional; reaproveitamento do cenário já montado |
| **Exemplos** | Comparação lado a lado do comportamento do agente durante o treinamento (Semana 15, decisões via política em treino) e após a inferência (Semana 16, decisões via modelo `.onnx` executado pelo Sentis); estudos de caso comentados da seção 12.11 como referência de aplicação em jogos comerciais |
| **Vídeos** | Não obrigatório; caso disponível, vídeo curto demonstrando um NPC com comportamento adaptativo perceptível em um jogo comercial, para apoiar a Engenharia Reversa |
| **Jogos para Engenharia Reversa** | Um jogo com IA adaptativa ou aprendizado perceptível pelo jogador (por exemplo, jogos com oponentes que ajustam dificuldade ou estratégia ao longo da partida), a critério do professor, para o sexto momento de Engenharia Reversa |

---

## Encontro 1 (1h30)

**Foco:** Do treinamento à execução — importar e operar o modelo treinado via Sentis, encerrando o ciclo técnico do Módulo 6.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Retomada do ciclo do Módulo 6 | 10 min | Situar a inferência como etapa final do ciclo iniciado na Semana 14 | Recapitula o percurso: planejamento de estado/ação/recompensa (S14) → treinamento com ML-Agents (S15) → inferência com Sentis (S16); apresenta a pergunta norteadora da semana | Relembram o modelo `.onnx` e a curva de recompensa que preservaram ao final da Semana 15 |
| 2. Unity Sentis — fundamentos e papel no ciclo | 20 min | Compreender o que o Sentis faz e por que ele é necessário | Apresenta a seção 12.9 (parte de inferência): o Sentis como motor de inferência de redes neurais dentro da Unity, que executa um modelo já treinado sem exigir o ambiente Python; contrasta explicitamente "treinar" (ML-Agents) com "executar" (Sentis) | Relacionam a distinção treinar/executar ao alerta já reforçado na Semana 15; identificam por que um jogo publicado não pode depender do ambiente de treinamento em Python |
| 3. Demonstração — importação e configuração do modelo | 25 min | Observar, na prática, a importação de um modelo `.onnx` e sua configuração como asset do Sentis | Demonstra, na cena do Adaptive AI, a importação do arquivo `.onnx` gerado na Semana 15 como asset do Sentis, a criação do worker de inferência e a substituição do vínculo com o Decision Requester/ML-Agents pela leitura direta do modelo | Observam a demonstração e identificam, na cena, onde a política aprendida passa a ser consultada localmente, sem comunicação externa |
| 4. Implementação guiada | 25 min | Configurar, em duplas ou grupos, a inferência do próprio modelo treinado | Orienta cada grupo a importar seu próprio modelo `.onnx` (Semana 15) no Sentis e a configurar o componente de inferência na cena do Adaptive AI, circulando para resolver dúvidas técnicas | Importam o modelo treinado e configuram o componente de inferência do Sentis na própria cena, sob orientação do professor |
| 5. Vantagens, limitações e cenários de uso | 10 min | Situar a Aprendizagem por Reforço no conjunto de técnicas do semestre | Apresenta a seção 12.10 (Vantagens e Limitações): custo de desenvolvimento e treinamento, imprevisibilidade do comportamento aprendido, dificuldade de depuração, versus a capacidade de gerar comportamento emergente difícil de scriptar manualmente | Comparam, brevemente, o custo/benefício da Aprendizagem por Reforço com o das técnicas determinísticas estudadas nos módulos anteriores (FSM, Utility AI, Minimax) |

---

## Encontro 2 (1h30)

**Foco:** Consolidação do Micro Game Adaptive AI, Desafio de Escolha Tecnológica do Módulo 6 e sexto momento de Engenharia Reversa — encerramento do ciclo dos seis módulos de conteúdo.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Laboratório — consolidação do Micro Game | 30 min | Finalizar a execução autônoma do Adaptive AI via Sentis | Acompanha cada grupo na verificação do funcionamento do agente executando exclusivamente via Sentis (sem dependência do ambiente de treinamento), auxiliando no ajuste de eventuais falhas de integração | Testam o Micro Game Adaptive AI de ponta a ponta, com o agente decidindo por meio do modelo treinado; registram o comportamento observado para o AI Design Log |
| 2. Desafio de Escolha Tecnológica (M6) | 25 min | Justificar tecnicamente a escolha de Aprendizagem por Reforço para um cenário proposto | Apresenta um cenário de IA adaptativa (por exemplo, um oponente que deve ajustar sua estratégia ao estilo de jogo do usuário) e solicita que cada grupo justifique, por escrito ou oralmente, se usaria ML-Agents/Sentis ou uma alternativa mais simples (Utility AI, FSM), considerando requisitos, limitações, alternativas e ferramentas disponíveis, conforme praticado nos módulos anteriores | Analisam o cenário proposto e produzem a justificativa técnica, comparando explicitamente Aprendizagem por Reforço com as abordagens determinísticas já estudadas |
| 3. Engenharia Reversa — 6º momento | 20 min | Relacionar teoria e prática a partir de um jogo comercial com IA adaptativa | Conduz a análise do jogo selecionado, levantando hipóteses sobre a arquitetura de IA por trás do comportamento adaptativo observado (aprendizado real via RL, heurísticas adaptativas simples, ou ilusão de adaptação por regras predefinidas) | Observam o jogo, formulam hipóteses sobre a técnica empregada e debatem se o comportamento indica aprendizagem genuína ou ilusão de adaptação |
| 4. Encerramento do ciclo dos seis módulos | 15 min | Consolidar a visão integrada dos seis módulos de conteúdo | Recapitula, em linhas gerais, os seis módulos e seus respectivos Micro Games, situando o AI Playground como conjunto integrado; orienta a preparação da apresentação final (Semana 17) | Revisam brevemente os Micro Games já desenvolvidos e anotam pendências para a consolidação final do AI Playground |

---

## Micro Game

**Micro Game em desenvolvimento:** Adaptive AI (Módulo 6) — **consolidação final**.

**Objetivo pedagógico:** demonstrar a etapa de inferência do ciclo de Aprendizagem por Reforço, evidenciando que um modelo treinado pode ser executado dentro da própria Unity, via Sentis, sem depender do ambiente de treinamento — encerrando o Módulo 6 com o Micro Game funcional de ponta a ponta.

**Funcionalidades esperadas ao final da Semana 16:**

- modelo `.onnx` (treinado na Semana 15) importado e configurado como componente de inferência do Sentis na cena do Adaptive AI;
- agente executando de forma autônoma, com decisões tomadas exclusivamente pelo modelo treinado, sem dependência do ML-Agents/Python;
- Micro Game Adaptive AI consolidado como parte funcional do AI Playground.

**Relação com módulos anteriores:** encerra o percurso iniciado na Semana 14 (planejamento de estado/ação/recompensa) e consolidado na Semana 15 (treinamento); representa, junto aos Micro Games dos Módulos 1 a 5, mais uma peça do AI Playground a ser reunida na apresentação final da Semana 17.

---

## Engenharia Reversa

| Campo | Conteúdo |
|---|---|
| **Jogo analisado** | Dois casos já analisados na Apostila, à escolha do professor: ***Black & White*** (Lionhead, 2001), seção 15.8 — aprendizado efetivo da criatura por reforço e imitação, o caso mais próximo do conteúdo do módulo; ou ***Left 4 Dead*** (Valve, 2008), seção 15.5 — o Diretor de IA e o ritmo adaptativo, útil justamente por **não** ser aprendizagem de máquina, permitindo contrastar adaptação por regras com aprendizado real |
| **Comportamento observado** | Mudança perceptível na estratégia, dificuldade ou padrão de decisão do agente/oponente ao longo da partida, em resposta ao comportamento do jogador |
| **Perguntas para discussão** | O comportamento observado é resultado de aprendizagem real (rede neural treinada) ou de uma heurística adaptativa simples (ajuste de parâmetros predefinidos)? Que evidências levariam o jogador a essa conclusão? Como o estúdio provavelmente testou e validou esse comportamento antes do lançamento, dado o custo de depuração de sistemas de RL discutido na seção 12.10? |
| **Relação com os conceitos da semana** | Retoma a distinção entre treinamento e inferência: mesmo que o jogo utilize Aprendizagem por Reforço, o comportamento em produção é sempre inferência de um modelo já treinado, nunca treinamento ao vivo durante a partida do jogador |

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Unity Sentis** | Uso efetivo e central: importação do modelo `.onnx` treinado na Semana 15 e configuração do componente de inferência que executa o agente do Adaptive AI de forma autônoma |
| **Unity ML-Agents** | Apenas como referência retrospectiva — o modelo já treinado (Semana 15) é o insumo desta semana; não há novo treinamento |

Nenhuma ferramenta de terceiros é indicada para esta semana, uma vez que o Sentis é a solução oficial e única prevista pelo Cronograma para a inferência do Módulo 6.

---

## Atividade de Laboratório

**Objetivo:** importar o modelo treinado na Semana 15 no Unity Sentis, configurar a inferência na cena do Adaptive AI e validar a execução autônoma do agente, consolidando o Micro Game.

**Etapas:**

1. Importar o arquivo `.onnx` gerado na Semana 15 como asset do Sentis no projeto Unity.
2. Configurar, na cena do Adaptive AI, o componente de inferência do Sentis (worker), substituindo o vínculo com o Decision Requester do ML-Agents.
3. Executar o Micro Game e observar o comportamento do agente decidindo exclusivamente a partir do modelo treinado.
4. Comparar o comportamento observado nesta execução com o comportamento registrado durante o treinamento (Semana 15), anotando semelhanças e diferenças.
5. Registrar o resultado da consolidação (funcionamento do agente via Sentis) para o AI Design Log do Micro Game 6.

**Resultado esperado:** ao final do Encontro 1, cada grupo deve ter o agente do Adaptive AI executando de forma autônoma via Sentis, pronto para a consolidação e discussão do Encontro 2.

---

## Verificação da Aprendizagem

Conforme a Rubrica de Avaliação e os pesos definidos nos Critérios de Notas, a Semana 16 encerra o Módulo 6 e gera os quatro instrumentos avaliativos previstos:

- **Micro Game (peso 50% do módulo)** — avaliado por Aplicação Prática, Uso da Unity e do Ecossistema (uso correto do Sentis para inferência) e Qualidade Técnica da Solução, verificados na consolidação do Adaptive AI;
- **AI Design Log (peso 25% do módulo)** — avaliado pela qualidade da documentação do Micro Game 6, entregue ao final desta semana;
- **Desafio de Escolha Tecnológica (peso 15% do módulo)** — avaliado por Tomada de Decisão e Compreensão Conceitual, verificados na justificativa apresentada no Encontro 2;
- **Engenharia Reversa (peso 10% do módulo)** — avaliado por Compreensão Conceitual e Tomada de Decisão, verificados na discussão do sexto momento de Engenharia Reversa.

A nota do Módulo 6 corresponde a 11,67% da nota final do semestre, conforme os Critérios de Notas.


**Instrumentos de verificação disponíveis na Apostila.** Antes de recorrer a questões próprias, o professor deve usar o material já pronto e alinhado: os **Exercícios de fixação** ao final do Capítulo 12, e — nas semanas de encerramento de Parte — as **Questões de Revisão**, os **Exercícios Conceituais** e os **Exercícios de Integração** do Encerramento correspondente. Recomenda-se aplicar duas ou três questões na abertura do Encontro 2, como verificação rápida antes do laboratório, e usar a Tabela Comparativa do Encerramento da Parte VI como apoio à discussão técnica. Esse material é a principal fonte de verificação formativa da disciplina, e não deve ficar sem uso.

---

## Entregas

Conforme o Cronograma e a matriz dos Critérios de Notas (item 4), a Semana 16 encerra o Módulo 6 com **quatro** entregas avaliadas:

- **Micro Game 6 — Adaptive AI consolidado (50%)** — agente treinado na Semana 15 executando por inferência via Sentis na cena do Micro Game, avaliado pelos critérios de Compreensão Conceitual, Aplicação Prática, Uso da Unity e do Ecossistema e Qualidade Técnica da Solução;
- **AI Design Log — Micro Game 6 (25%)** — documentando problema, requisitos, alternativas consideradas, solução escolhida, justificativa, ferramentas utilizadas (ML-Agents e Sentis), limitações e melhorias futuras, conforme o modelo dos Modelos de Entrega do Aluno (§1);
- **Desafio de Escolha Tecnológica — Módulo 6 (15%)** — justificativa técnica produzida no Encontro 2;
- **6º momento de Engenharia Reversa (10%)** — registro da análise do jogo comercial selecionado.

Estas entregas encerram o ciclo avaliativo dos seis módulos de conteúdo. Restam, no semestre, apenas a apresentação final e o AI Design Log consolidado da Semana 17.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Confundir o Sentis com uma ferramenta de treinamento, tentando re-treinar o modelo dentro dele | Reforçar que o Sentis apenas executa (infere) um modelo já pronto; qualquer ajuste de comportamento exige retornar ao ML-Agents (Semana 15), não ao Sentis |
| Erro na importação do modelo `.onnx` ou incompatibilidade entre a versão exportada e o componente de inferência do Sentis | Verificar previamente, com cada grupo, se o arquivo `.onnx` preservado da Semana 15 está íntegro; ter um modelo de exemplo pronto como alternativa para grupos com problemas técnicos, evitando perda de aula |
| Dificuldade em justificar, no Desafio de Escolha Tecnológica, por que usar RL em vez de uma solução mais simples | Retomar explicitamente a seção 12.10 (Vantagens e Limitações) e o paralelo com o Utility AI (Módulo 3), incentivando o grupo a considerar o custo de desenvolvimento e depuração, não apenas a sofisticação da técnica |
| Na Engenharia Reversa, atribuir precipitadamente qualquer comportamento adaptativo a "aprendizagem por reforço" sem evidência suficiente | Reforçar a distinção entre aprendizagem real e ilusão de adaptação (ajuste de parâmetros predefinidos), tema recorrente desde o início da disciplina; exigir que a hipótese seja justificada por evidências observáveis, não por suposição |

---

## Preparação para a Próxima Semana

Para a Semana 17 (Engenharia Reversa integrada e apresentação final do AI Playground), o professor deve:

- confirmar que todos os grupos concluíram a consolidação do Micro Game Adaptive AI e entregaram o AI Design Log do Módulo 6;
- solicitar a leitura prévia da Parte VII, Capítulo 15 da Apostila (Estudos de Caso Comentados), que será retomada de forma integrada na Semana 17;
- orientar os grupos a reunir e testar, previamente, todos os Micro Games desenvolvidos ao longo do semestre (Módulos 1 a 6) para a montagem do AI Playground completo;
- lembrar que a Semana 17 encerra o semestre com a apresentação final e a entrega do AI Design Log consolidado, reunindo os seis Micro Games e as decisões técnicas tomadas ao longo do curso.
