# Plano de Aula — Semana 15

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais
**Metodologia:** Project-Based Learning (PBL)

---

## Informações Gerais

| Campo | Conteúdo |
|---|---|
| **Semana** | 15 de 17 |
| **Unidade** | Unidade VI — Aprendizagem e Adaptação (Semanas 14–16) |
| **Módulo** | Módulo 6 — Como um agente aprende? |
| **Tema** | Treinamento com ML-Agents |
| **Pergunta Norteadora** | Como um agente aprende? (parte 2) |
| **Tipo de semana** | 🔵 Semana de aprofundamento teórico-prático e treinamento efetivo (sem entrega formal) |

---

## Objetivos de Aprendizagem

Ao final da Semana 15, o estudante deverá ser capaz de:

1. **Descrever** o algoritmo Q-Learning — a tabela Q, a equação de Bellman e a regra de atualização — e **calcular** manualmente a atualização de uma célula Q(s, a) a partir de um exemplo simples.
2. **Explicar** por que a tabela Q se torna inviável em espaços de estado grandes ou contínuos, e **relacionar** essa limitação à necessidade de uma rede neural como aproximador de função (ponte conceitual para o ML-Agents).
3. **Configurar**, no Unity ML-Agents, os componentes básicos de um agente treinável (Behavior Parameters, observações, ações e recompensa já planejados na Semana 14).
4. **Identificar** os principais hiperparâmetros de treinamento (taxa de aprendizagem, tamanho de lote, unidades ocultas, número máximo de passos) e seu efeito qualitativo sobre o treino.
5. **Executar** um treinamento efetivo com ML-Agents e **interpretar** a curva de recompensa cumulativa ao longo do tempo, relacionando-a ao progresso do aprendizado.
6. **Diagnosticar**, com apoio do professor, sinais de treinamento problemático (recompensa estagnada, recompensa mal especificada, instabilidade) e propor ajustes.

---

## Conteúdos

Conteúdo previsto no Cronograma para esta semana, correspondente à **Parte VI, Capítulo 12 da Apostila — Aprendizagem por Reforço (aprofundamento prático)**:

- Q-Learning: a tabela Q, a equação de Bellman, a regra de atualização, a taxa de aprendizagem (α) e o fator de desconto (γ), com o exemplo passo a passo da trilha S1–S5 — seção 12.6;
- a limitação da tabela Q em espaços grandes/contínuos e a ideia de substituí-la por uma rede neural aproximadora — introdução da seção 12.7, apenas como ponte conceitual para o ML-Agents (sem aprofundar DQN, *experience replay* ou rede-alvo);
- Unity ML-Agents em profundidade de uso: definição de observações, ações e recompensa em C#, o ciclo treinamento (Python) → política treinada → execução na Unity, e os algoritmos que o pacote implementa (PPO, SAC) — seção 12.9;
- Unity Sentis, citado apenas como o componente que executará a política já treinada (aprofundamento reservado à Semana 16) — seção 12.9.

Não é objetivo desta semana aprofundar o Deep Q-Network (DQN), *experience replay* ou rede-alvo (seção 12.7 completa), nem operar o Sentis (seção 12.9, parte de inferência) — ambos fora do escopo previsto pelo Cronograma para a Semana 15.

---

## Preparação do Professor

| Item | Detalhamento |
|---|---|
| **Leitura recomendada** | Apostila — Parte VI, Capítulo 12, seção 12.6 (obrigatória) e seção 12.9 completa (obrigatória, foco em ML-Agents) |
| **Materiais necessários** | Projetor/tela; computadores com Unity Hub, o pacote ML-Agents importado e o ambiente Python do ML-Agents já instalado (conforme recomendação da Semana 14); planejamento escrito de estado/ação/recompensa de cada grupo, produzido na Semana 14; acesso ao TensorBoard (ou visualizador de métricas equivalente) para acompanhar a curva de recompensa |
| **Cena Unity utilizada** | Cena do Micro Game Adaptive AI montada na Semana 14 (agente, ambiente, alvo/obstáculos), agora recebendo os componentes de ML-Agents (Behavior Parameters, Decision Requester, script de Agent em C#) |
| **Assets** | Nenhum asset de arte adicional; reaproveitamento do cenário mínimo já montado |
| **Exemplos** | O exemplo passo a passo da trilha S1–S5 (seção 12.6) para fixar a equação de Bellman antes de ir ao computador; exemplos oficiais do ML-Agents (Walker/Crawler) como referência de curva de recompensa saudável; o exemplo do *CoastRunners* (retomado da Semana 14) caso surjam sinais de recompensa mal especificada durante o treino |
| **Vídeos** | Não obrigatório; caso disponível, um vídeo curto mostrando uma curva de recompensa subindo ao longo do treinamento em um exemplo oficial do ML-Agents ajuda a calibrar a expectativa dos estudantes antes do laboratório |
| **Jogos para Engenharia Reversa** | Não há momento formal de Engenharia Reversa previsto nesta semana pelo Cronograma |

---

## Encontro 1 (1h30)

**Foco:** Configuração do treinamento no ML-Agents — hiperparâmetros básicos e observação das primeiras curvas de recompensa. Antes disso, fecha-se a lacuna teórica deixada pela Semana 14: o Q-Learning.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Retomada e Q-Learning: a tabela Q | 15 min | Apresentar a tabela Q como representação da função de valor de ação | Retoma o planejamento da Semana 14 (estado, ações, recompensa do Adaptive AI); apresenta a seção 12.6 — a tabela Q, sua estrutura (estados nas linhas, ações nas colunas) e o limite de viabilidade para espaços pequenos | Relacionam a ideia de tabela Q ao Q(s, a) já discutido na Semana 14, revisando por que Q simplifica a decisão a "escolha a ação de maior valor" |
| 2. A equação de Bellman e a regra de atualização | 25 min | Compreender e calcular a regra de atualização do Q-Learning | Apresenta a fórmula `Q(s,a) ← Q(s,a) + α·[r + γ·maxₐ′Q(s′,a′) − Q(s,a)]`, decompondo cada termo (recompensa imediata, melhor futuro, erro de diferença temporal, α e γ); conduz, junto à turma, o exemplo passo a passo da trilha S1–S5 (seção 12.6) | Acompanham e refazem, em duplas, ao menos uma atualização de Q(s, a) a partir de valores dados, verificando o "escorrimento" do valor da recompensa terminal para trás |
| 3. Da tabela à rede neural — ponte para o ML-Agents | 15 min | Entender por que o ML-Agents não usa uma tabela Q | Apresenta, de forma conceitual e breve (introdução da seção 12.7), por que espaços de estado grandes ou contínuos inviabilizam a tabela Q, e como uma rede neural passa a desempenhar o papel de aproximador da função de valor/política; situa o PPO (algoritmo do ML-Agents) como um método moderno que resolve o mesmo problema que o Q-Learning, por caminho diferente | Relacionam a limitação da tabela Q ao próprio Micro Game: se o estado do Adaptive AI incluir posições contínuas, uma tabela seria inviável — daí a necessidade do ML-Agents |
| 4. Componentes do ML-Agents na cena | 20 min | Reconhecer, na prática, onde o vocabulário do capítulo aparece nos componentes do ML-Agents | Demonstra, na cena do Adaptive AI, a adição do script de Agent (C#), do Behavior Parameters e do Decision Requester; mostra como observações, ações e recompensa (já planejadas na Semana 14) se traduzem em código (`CollectObservations`, `OnActionReceived`, `AddReward`) | Observam a demonstração e identificam, no código apresentado, a correspondência com o estado, as ações e a recompensa que o próprio grupo definiu na Semana 14 |
| 5. Hiperparâmetros básicos de treinamento | 15 min | Reconhecer os principais hiperparâmetros e seu efeito qualitativo | Apresenta, em nível de configuração (arquivo YAML), os hiperparâmetros básicos: taxa de aprendizagem, tamanho de lote (*batch size*), unidades ocultas da rede e número máximo de passos de treinamento; explica o efeito qualitativo de cada um, sem exigir domínio matemático de redes neurais | Anotam, para cada hiperparâmetro, uma hipótese de como ele deveria ser ajustado para o problema específico do próprio grupo |

---

## Encontro 2 (1h30)

**Foco:** Treinamento efetivo do agente do Micro Game Adaptive AI. Semana predominantemente prática, com acompanhamento contínuo do professor.

| Etapa | Duração | Objetivo | Atividade do Professor | Atividade dos Estudantes |
|---|---|---|---|---|
| 1. Preparação do treinamento | 10 min | Garantir que todos os grupos estejam prontos para iniciar o treinamento | Verifica, com cada grupo, se o Behavior Parameters, o arquivo de configuração YAML e a cena estão corretamente configurados; relembra o comando de início de treinamento do ML-Agents | Conferem a própria configuração (observações, ações, recompensa, hiperparâmetros) antes de iniciar |
| 2. Laboratório — treinamento efetivo | 55 min | Executar o treinamento do agente do Micro Game Adaptive AI e acompanhar a curva de recompensa | Circula entre os grupos, orientando a leitura da curva de recompensa cumulativa no TensorBoard (ou equivalente), ajudando a diagnosticar estagnação, instabilidade ou sinais de recompensa mal especificada | Executam o treinamento; observam a curva de recompensa em tempo real; registram observações sobre o comportamento emergente do agente ao longo do treino |
| 3. Discussão técnica | 15 min | Comparar curvas de recompensa e decisões de projeto entre grupos | Conduz a discussão comparando as curvas obtidas pelos diferentes grupos, relacionando diferenças de comportamento a diferenças em estado, recompensa ou hiperparâmetros escolhidos | Apresentam brevemente sua curva de recompensa e o comportamento observado do agente, recebendo retorno dos colegas e do professor |
| 4. Encerramento | 10 min | Consolidar o que foi observado e preparar a Semana 16 | Recapitula a diferença entre treinar (Semana 15) e executar/inferir (Semana 16, com Sentis); orienta os grupos a preservar o modelo treinado (arquivo `.onnx`) gerado ao final do treinamento | Registram o estado do treinamento (curva obtida, comportamento observado, modelo gerado) para uso na Semana 16 |

---

## Micro Game

**Micro Game em desenvolvimento:** Adaptive AI (Módulo 6) — **treinamento**.

**Objetivo pedagógico:** demonstrar, na prática, o ciclo completo de treinamento de um agente de Aprendizagem por Reforço com o ML-Agents — da configuração de hiperparâmetros à leitura da curva de recompensa —, consolidando que o sucesso do treinamento depende tanto das decisões conceituais da Semana 14 (estado, ações, recompensa) quanto da configuração técnica desta semana.

**Funcionalidades esperadas ao final da Semana 15:**

- componentes de ML-Agents (Agent, Behavior Parameters, Decision Requester) configurados na cena do Adaptive AI, implementando o planejamento de estado, ações e recompensa da Semana 14;
- ao menos um treinamento efetivo executado, com curva de recompensa observada e registrada;
- um modelo treinado (arquivo `.onnx`) gerado ao final do treino, preservado para uso na Semana 16.

**Relação com módulos anteriores:** opera diretamente sobre o planejamento produzido na Semana 14, e retoma o paralelo entre a função valor aprendida e a função de avaliação do Minimax (Módulo 4) e o mapa de influência (Módulo 3). Prepara diretamente a Semana 16, na qual o modelo treinado nesta semana será executado via Sentis, encerrando o Módulo 6.

---

## Engenharia Reversa

O Cronograma **não prevê** um momento formal de Engenharia Reversa na Semana 15. O foco permanece integralmente na configuração e execução do treinamento do Micro Game Adaptive AI.

---

## Ferramentas

| Ferramenta | Uso nesta semana |
|---|---|
| **Unity ML-Agents** | Uso efetivo e central: configuração dos componentes de agente (Behavior Parameters, Decision Requester), definição de hiperparâmetros de treinamento (arquivo YAML) e execução do treinamento via linha de comando (motor Python) |
| **TensorBoard (ou visualizador de métricas equivalente)** | Acompanhamento da curva de recompensa cumulativa ao longo do treinamento |
| **Unity Sentis** | Apenas citado, como o componente que executará o modelo `.onnx` gerado nesta semana — sua operação efetiva é reservada para a Semana 16 |

Nenhuma ferramenta de terceiros é indicada para esta semana, uma vez que o ML-Agents é a solução oficial e única prevista pelo Cronograma para o treinamento do Módulo 6.

---

## Atividade de Laboratório

**Objetivo:** configurar e executar o treinamento efetivo do agente do Micro Game Adaptive AI com o Unity ML-Agents, a partir do planejamento de estado, ações e recompensa definido na Semana 14, e interpretar a curva de recompensa resultante.

**Etapas:**

1. Adicionar à cena os componentes de ML-Agents (script de Agent em C#, Behavior Parameters, Decision Requester), implementando o estado (observações), o espaço de ações e a função de recompensa já planejados.
2. Configurar o arquivo YAML de treinamento com os hiperparâmetros básicos (taxa de aprendizagem, tamanho de lote, unidades ocultas, número máximo de passos).
3. Iniciar o treinamento via linha de comando e acompanhar, no TensorBoard, a curva de recompensa cumulativa ao longo do tempo.
4. Observar o comportamento do agente durante o treino, identificando se ele está progredindo, estagnado ou apresentando sinais de recompensa mal especificada.
5. Ajustar, se necessário e com orientação do professor, um hiperparâmetro ou um detalhe da recompensa, documentando a mudança e seu efeito.
6. Preservar o modelo treinado (`.onnx`) e registrar a curva de recompensa obtida para a discussão técnica.

**Resultado esperado:** ao final do Encontro 2, cada grupo deve ter executado ao menos um treinamento completo do Adaptive AI, com uma curva de recompensa registrada e um modelo `.onnx` gerado, prontos para serem executados via Sentis na Semana 16.

---

## Verificação da Aprendizagem

A Semana 15 é predominantemente prática, sem entrega formal nem fechamento de módulo. Conforme a Rubrica de Avaliação, o professor deve observar, de forma formativa:

- **Compreensão Conceitual** — se o estudante consegue explicar a regra de atualização do Q-Learning e a razão pela qual o ML-Agents substitui a tabela Q por uma rede neural;
- **Aplicação Prática** — o uso adequado do ML-Agents (soluções oficiais de IA da Unity), incluindo a configuração correta dos componentes de agente e dos hiperparâmetros de treinamento, e a leitura correta da curva de recompensa como evidência de progresso ou de problema no treino;
- **Comunicação Técnica** — se o grupo consegue apresentar e justificar, na discussão técnica do Encontro 2, a curva de recompensa obtida e as decisões tomadas diante dela.

Como não há entrega nesta semana, a observação serve de insumo formativo para a avaliação do Módulo 6, que será consolidada ao final da Semana 16.

---

## Entregas

Conforme o Cronograma, a Semana 15 não possui entrega formal — o campo correspondente indica **"acompanhamento do projeto"**. O modelo treinado (`.onnx`) e a curva de recompensa registrada por cada grupo devem ser preservados para uso direto na Semana 16.

---

## Dificuldades Esperadas

| Dificuldade comum | Estratégia de intervenção |
|---|---|
| Dificuldade em acompanhar o cálculo manual da regra de atualização do Q-Learning, especialmente o termo `maxₐ′Q(s′,a′)` | Refazer o exemplo da trilha S1–S5 (seção 12.6) passo a passo no quadro, isolando cada termo antes de combiná-los |
| Esperar que o agente aprenda de forma visível em poucos minutos de treinamento | Retomar o alerta da seção 12.3 sobre o volume de interações necessário; mostrar que curvas de recompensa saudáveis costumam ser graduais, não instantâneas |
| Curva de recompensa estagnada ou decrescente, sem diagnóstico claro do grupo | Conduzir o grupo a revisar, em ordem, os três suspeitos mais prováveis: recompensa mal especificada (retomar o exemplo do *CoastRunners*), estado insuficiente (violação da propriedade de Markov, Semana 14) e hiperparâmetros inadequados |
| Confundir o papel do ML-Agents (treinar) com o do Sentis (executar), tentando "rodar o jogo final" ainda nesta semana | Reforçar explicitamente a distinção conceitual da seção 12.9: ML-Agents treina, Sentis executa; a execução do modelo treinado é o foco da Semana 16 |
| Ambiente Python do ML-Agents mal configurado, consumindo tempo de aula com problemas de instalação | Verificar a instalação antes do início do Encontro 1, conforme recomendação já feita na Semana 14; caso o problema persista para algum grupo, redirecioná-lo para uma máquina com ambiente já configurado, sem interromper o treinamento dos demais |

---

## Preparação para a Próxima Semana

Para a Semana 16 (Inferência com Sentis e consolidação), o professor deve:

- confirmar que todos os grupos possuem um modelo treinado (`.onnx`) preservado, resultado do treinamento desta semana;
- confirmar que todos os grupos registraram sua curva de recompensa e suas observações sobre o comportamento do agente treinado;
- solicitar a leitura prévia da seção 12.9 (parte do Sentis, se ainda não revisada) e, se pertinente ao fechamento do módulo, da seção 12.10 (Vantagens e Limitações) e da seção 12.11 (Estudos de Caso);
- lembrar que a Semana 16 encerra o Módulo 6 e é semana de Desafio de Escolha Tecnológica e Engenharia Reversa, conforme indicado no Cronograma — vale revisar com antecedência o formato desse desafio já utilizado em módulos anteriores.
