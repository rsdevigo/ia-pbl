# Revisão — Semana 15

**Tema:** Treinamento com ML-Agents
**Módulo:** 6 — Como um agente aprende? (parte 2, meio da Unidade VI)
**Documentos revisados:** Plano de Aula (Semana 15) e Slides (Semana 15 — `slides.md`, PDF e PPTX) — não existe Tutorial nesta disciplina (nenhuma semana possui esse artefato), confirmado nas Revisões anteriores; o item de coerência com Tutorial é, portanto, não aplicável.
**Referência de verdade:** Cronograma (linha Semana 15); CLAUDE.md — "Micro Games — Exemplos de Implementação" (Módulo 6: Adaptive AI — Coletor de Recompensas); `Incrementos_MicroGames.md` (linha S15 – 2º Encontro); Manual do Professor (seção sobre a cadeia versionada ML-Agents ↔ Python ↔ `.onnx`, §6.0/linha 167 e 185).

**Nota metodológica:** como nas Revisões anteriores, a Apostila não está disponível como arquivo neste ambiente de trabalho (é mantida em repositório externo). A verificação de alinhamento à Apostila foi feita por triangulação entre os números de seção citados no Plano de Aula, nos Slides e no Cronograma, e por continuidade com o conteúdo já revisado nas semanas anteriores — não por leitura direta do texto da Apostila. Onde isso limita a confiança de uma constatação, isso é sinalizado explicitamente.

---

## Resumo Geral

A Semana 15 dá sequência coerente à Semana 14: fecha a lacuna teórica do Q-Learning (tabela Q, equação de Bellman, exemplo da trilha S1–S5) antes de qualquer configuração de ferramenta, faz a ponte conceitual da tabela para a rede neural, e só então avança para os componentes reais do ML-Agents e o treinamento efetivo — respeitando a Filosofia da Disciplina. Plano e Slides estão bem alinhados em conteúdo e sequência, os tempos de ambos os encontros fecham em 90 minutos, e a semana resolve de forma explícita a pendência mais crítica identificada na Revisão da Semana 14: o esqueleto do script `Agent`, cuja conclusão (`CollectObservations`, `OnActionReceived`, `AddReward`) agora aparece corretamente ancorada tanto no Plano quanto no `Incrementos_MicroGames.md`. O ponto mais relevante encontrado nesta revisão é, mais uma vez, a ausência do tema fixo do Micro Game 6 ("Coletor de Recompensas", itens positivos/negativos) no Plano e nos Slides — mesmo padrão já sinalizado nas Revisões das Semanas 12, 13 e 14 — e uma dependência técnica de alto risco (ambiente Python do ML-Agents) que, embora mitigada por recomendações em três documentos, concentra praticamente todo o Encontro 2 em uma única atividade sem plano de contingência explícito para o caso de falha generalizada. São problemas localizados que não comprometem a estrutura pedagógica da semana, mas merecem atenção antes da aplicação em turma.

---

## Pontos Fortes

- **Sequência didática rigorosamente respeitada.** O Encontro 1 completo (75 dos 90 minutos) trata do fundamento — tabela Q, equação de Bellman, exemplo S1–S5, limite de escala e a ponte para a rede neural — antes de qualquer menção a componentes do ML-Agents; a introdução às ferramentas se concentra nos últimos 20 minutos do Encontro 1 e no Encontro 2, coerente com "nunca apresentar ferramentas antes dos conceitos".
- **Fechamento da lacuna da Semana 14.** A pendência mais crítica apontada na Revisão da Semana 14 — o esqueleto do script `Agent` não aparecer nas "Funcionalidades esperadas" nem nos Slides — está resolvida nesta semana: o Plano de Aula (Preparação do Professor, Atividade de Laboratório etapa 1) e o `Incrementos_MicroGames.md` (linha S15) tratam explicitamente a conclusão do script (`CollectObservations`, `OnActionReceived`, `AddReward`) como pré-requisito e entregável técnico da semana.
- **Continuidade conceitual bem ancorada.** O paralelo entre Q(s, a) tabular e a aproximação por rede neural retoma diretamente o vocabulário da Semana 14 (V(s), Q(s, a), MDP) e situa o PPO como "o mesmo problema, caminho diferente" — evitando reensinar e ao mesmo tempo evitando o salto abrupto de tabela para rede neural sem justificativa.
- **Tempos exatos e coerentes entre Plano e Slides.** Encontro 1: 15+25+15+20+15 = 90 minutos; Encontro 2: 10+55+15+10 = 90 minutos. A ordem dos blocos nos Slides (tabela Q → limite → Bellman → exemplo S1–S5 → erro comum → rede neural → seção ML-Agents → três componentes → diagrama → hiperparâmetros → seção laboratório → o que fazer hoje → leitura da curva → industry box → erro comum/exercise → resumo → preparação S16) espelha fielmente a sequência do Plano.
- **Tratamento cuidadoso de expectativa e diagnóstico.** O alerta contra esperar aprendizado "visível em poucos minutos" aparece de forma consistente no Plano (Dificuldades Esperadas), nos Slides (industry box com Walker/Crawler e slide de "erro comum") e retoma o exemplo do CoastRunners da Semana 14 como um dos "três suspeitos" de curva problemática — mostrando reaproveitamento deliberado de material já ensinado, sem repetição redundante.
- **Risco técnico identificado e mitigado em múltiplos documentos.** A dependência do ambiente Python do ML-Agents é sinalizada no Cronograma (Semana 14, "Observação"), no Plano de Aula da Semana 14 e, nesta semana, retomada na "Preparação do Professor" e nas "Dificuldades Esperadas" com uma estratégia de contingência (redirecionar o grupo a uma máquina já configurada). O Manual do Professor reforça a mesma cadeia frágil (ML-Agents ↔ Python ↔ `.onnx`) como ponto que exige verificação prévia.

---

## Problemas Encontrados

**Problema 1 — corrigido**
- **Documento:** Plano de Aula e Slides (Semana 15)
- **Local:** Plano — seção "Micro Game" (tema) e "Preparação do Professor" (linha "Cena Unity utilizada"); Slides — capa e slide "O que fazer hoje"
- **Descrição:** O CLAUDE.md ("Micro Games — Exemplos de Implementação", Módulo 6) e o `Incrementos_MicroGames.md` definem o tema fixo do Micro Game 6 como "Coletor de Recompensas" (itens positivos/negativos). Nem o Plano nem os Slides desta semana mencionavam esse tema, tratando a cena apenas como "Adaptive AI" de forma genérica — mesmo padrão de lacuna já identificado nas Revisões das Semanas 12 a 14.
- **Ação tomada:** adicionada a menção "Coletor de Recompensas" / "itens positivos/negativos" na seção "Micro Game" e na linha "Cena Unity utilizada" do Plano, na capa dos Slides e no slide "O que fazer hoje".
- **Prioridade original:** Média

**Problema 2 — corrigido**
- **Documento:** Plano de Aula (Semana 15) — "Dificuldades Esperadas"
- **Local:** Tabela do Encontro 2, etapa 2 (55 dos 90 minutos do encontro), e tabela de "Dificuldades Esperadas"
- **Descrição:** O Encontro 2 concentrava mais da metade do tempo em uma única atividade técnica (treinamento via linha de comando) sem plano de contingência para falha ampla do ambiente Python — apenas para o caso de "algum grupo" isolado.
- **Ação tomada:** adicionada uma nova linha em "Dificuldades Esperadas" cobrindo o cenário de falha ampla, com estratégia de contingência (treinamento de referência preparado com antecedência para demonstração, enquanto os grupos afetados corrigem o ambiente).
- **Prioridade original:** Média

**Problema 3 — corrigido**
- **Documento:** Plano de Aula (Semana 15) — "Preparação do Professor"
- **Local:** Linha "Leitura recomendada"
- **Descrição:** A seção "Conteúdos" já previa a introdução da seção 12.7 como ponte conceitual (etapa 3 do Encontro 1), mas a "Leitura recomendada" listava apenas as seções 12.6 e 12.9.
- **Ação tomada:** adicionada a introdução da seção 12.7 à linha "Leitura recomendada".
- **Prioridade original:** Baixa

**Reavaliação — não é um problema real**
- **Item:** Nota "FIGURA A PRODUZIR" no slide "Do vocabulário ao código"
- **Descrição:** Verificação adicional mostrou que `assets/mermaid-1.png` (o diagrama efetivamente usado no slide) já existe e está corretamente referenciado. A nota do apresentador não trata desse diagrama, e sim de uma captura de tela real da Unity ainda não produzida (`componentes-mlagents-adaptive-ai.webp`, mencionada explicitamente na nota) — uma figura complementar distinta, genuinamente pendente. Esse padrão (diagrama Mermaid já renderizado no slide + nota de apresentador pedindo uma captura de tela real complementar) é usado de forma consistente em outras 12 semanas do curso, não sendo uma inconsistência da Semana 15. O item apontado na primeira revisão foi retirado da lista de problemas; nenhuma ação foi necessária.

---

## Sugestões de Melhoria

Todas as sugestões da revisão original foram aplicadas diretamente no Plano de Aula e nos Slides (ver "Problemas Encontrados" acima). Não há sugestões pendentes.

Observação operacional: as edições foram feitas em `slides.md` (fonte). O PDF e o PPTX da Semana 15 são gerados automaticamente por CI (workflow "Gerar slides com Marp") a partir desse arquivo — será necessário um push do repositório para que os artefatos renderizados reflitam as mudanças.

---

## Parecer Final

**Classificação:** Pronta para aplicação.

**Justificativa:** Os três problemas identificados na revisão original (tema do Micro Game ausente, falta de contingência para falha ampla do ambiente Python, leitura recomendada incompleta) foram corrigidos diretamente no Plano de Aula e nos Slides. O quarto item apontado inicialmente foi reavaliado e não configura um problema — o padrão de nota de apresentador é consistente com o restante do curso. A Semana 15 mantém a qualidade estrutural já observada (sequência didática correta, tempos exatos, coerência entre Plano e Slides) e, com os ajustes aplicados, não há pendências conhecidas para aplicação em turma. Recomenda-se apenas confirmar que o PDF/PPTX foram regenerados pelo CI após o commit das alterações em `slides.md`.
