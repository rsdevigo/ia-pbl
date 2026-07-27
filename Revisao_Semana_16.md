# Revisão — Semana 16

**Tema:** Inferência com Sentis e consolidação
**Módulo:** 6 — Como um agente aprende? (parte 3, fim da Unidade VI e do ciclo dos seis módulos)
**Documentos revisados:** Plano de Aula (Semana 16) e Slides (Semana 16 — `slides.md`, PDF e PPTX) — não existe Tutorial nesta disciplina (nenhuma semana possui esse artefato), confirmado nas Revisões anteriores; o item de coerência com Tutorial é, portanto, não aplicável.
**Referência de verdade:** Cronograma (linha Semana 16 e Plano de Contingência); CLAUDE.md — "Micro Games — Exemplos de Implementação" (Módulo 6: Adaptive AI — Coletor de Recompensas); `Incrementos_MicroGames.md` (linha S16 – 2º Encontro); Plano de Ensino / Critérios de Notas (item 4 e 5); Manual do Professor (§ Sentis/Inference Engine, linha 179–183; § 6.5 GOAP).

**Nota metodológica:** como nas Revisões anteriores, a Apostila não está disponível como arquivo neste ambiente de trabalho (é mantida em repositório externo, `rsdevigo.github.io/apostila-ia`, uma aplicação que renderiza o conteúdo via JavaScript e não expõe o texto a uma busca direta). A verificação de alinhamento à Apostila foi feita por triangulação entre os números de seção citados no Plano de Aula, nos Slides e no Cronograma, e por continuidade com o conteúdo já revisado nas semanas anteriores — não por leitura direta do texto da Apostila. Onde isso limita a confiança de uma constatação, isso é sinalizado explicitamente.

---

## Resumo Geral

A Semana 16 fecha com coerência o ciclo iniciado na Semana 14: separa com clareza treinar (ML-Agents, já concluído) de executar (Sentis, foco desta semana), segue a Filosofia da Disciplina ao apresentar primeiro a distinção conceitual "treinar × executar" antes de qualquer configuração de ferramenta, e articula corretamente os quatro instrumentos avaliativos que encerram o Módulo 6. Os tempos de ambos os encontros fecham exatamente em 90 minutos, e a sequência dos Slides espelha fielmente a do Plano de Aula. A revisão identificou três pontos de ajuste — ausência do tema fixo do Micro Game 6 ("Coletor de Recompensas"), ausência de alerta sobre a mudança de identificador do pacote Sentis (`com.unity.sentis` → `com.unity.ai.inference`, documentada no Manual do Professor) e ausência de um slide de síntese do encerramento dos seis módulos — e todos foram corrigidos diretamente no Plano de Aula e nos Slides.

---

## Pontos Fortes

- **Sequência didática rigorosamente respeitada.** A distinção "treinar (ML-Agents) × executar (Sentis)" é apresentada antes de qualquer instrução prática de importação de modelo, tanto no Plano (Encontro 1, etapas 1–2) quanto nos Slides (retomada da Semana 15 → pergunta norteadora → ciclo do Módulo 6 → tabela Treinar×Executar → "O que é o Sentis"), coerente com "nunca apresentar ferramentas antes dos conceitos".
- **Tempos exatos e coerentes entre Plano e Slides.** Encontro 1: 10+20+25+25+10 = 90 minutos; Encontro 2: 30+25+20+15 = 90 minutos. A ordem dos blocos nos Slides acompanha fielmente a sequência do Plano, incluindo os dois momentos avaliados (Desafio de Escolha Tecnológica e Engenharia Reversa) claramente identificados por classe própria (`_class: exercise`).
- **Fechamento coerente do ciclo do Módulo 6.** O Plano articula com precisão a cadeia das três semanas (planejamento S14 → treinamento S15 → inferência S16) tanto na retomada quanto no Micro Game e na seção "Relação com módulos anteriores", e os Slides reforçam essa mesma cadeia no diagrama do ciclo e na retomada da Semana 15.
- **Consistência numérica com os documentos normativos.** O peso de 11,67% do Módulo 6 na nota final citado no Plano confere exatamente com o item 5 dos Critérios de Notas ("Módulos 1 a 6 ... 70% (11,67% cada módulo)"), e a distribuição 50/25/15/10% entre Micro Game, AI Design Log, Desafio de Escolha Tecnológica e Engenharia Reversa confere com a matriz do item 4.
- **Engenharia Reversa bem fundamentada.** A escolha entre *Black & White* (aprendizado real por reforço/imitação) e *Left 4 Dead* (adaptação por regras, sem aprendizado de máquina) dá ao professor uma opção deliberadamente contrastante, e a pergunta de discussão do Plano retoma de forma explícita o tema central da semana (aprendizagem real × ilusão de adaptação) — coerente com o eixo de Engenharia Reversa da disciplina desde a Semana 1.
- **Reconhecimento explícito, no próprio Cronograma, do risco de compressão desta semana.** O Plano de Contingência já classifica o Encontro 2 da Semana 16 como não compressível ("concentram três dos quatro instrumentos avaliativos do módulo"), e o Plano de Aula reflete essa mesma leitura ao não deixar folga nesse encontro — risco conhecido e não uma omissão do material.

---

## Problemas Encontrados

**Problema 1 — corrigido**
- **Documento:** Plano de Aula e Slides (Semana 16)
- **Local:** Plano — seção "Micro Game" e linhas "Materiais necessários"/"Cena Unity utilizada" em "Preparação do Professor"; Slides — capa e slide "O que fazer hoje"
- **Descrição:** O CLAUDE.md ("Micro Games — Exemplos de Implementação", Módulo 6) e o `Incrementos_MicroGames.md` definem o tema fixo do Micro Game 6 como "Coletor de Recompensas" (itens positivos/negativos). Nem o Plano nem os Slides mencionavam esse tema, tratando a cena apenas como "Adaptive AI" de forma genérica — a mesma lacuna já identificada nas Revisões das Semanas 12 a 14 e corrigida na Semana 15, reincidente nesta semana de encerramento do módulo.
- **Ação tomada:** adicionada a menção "Coletor de Recompensas" na seção "Micro Game" e na linha "Cena Unity utilizada" do Plano, na capa dos Slides e no slide "O que fazer hoje".
- **Prioridade original:** Média

**Problema 2 — corrigido**
- **Documento:** Plano de Aula (Semana 16) — "Preparação do Professor" e "Ferramentas"; Slides — slide "O que é o Sentis"
- **Local:** Linha "Materiais necessários" e seção "Ferramentas" do Plano; slide "O que é o Sentis"
- **Descrição:** O Manual do Professor (linha 179–183) registra que o identificador do pacote de inferência da Unity mudou de `com.unity.sentis` para `com.unity.ai.inference`, e que o nome de exibição oscila entre "Sentis" e "Inference Engine" nas diferentes versões — alertando explicitamente que a busca no Package Manager deve ser feita pelo identificador, não pelo nome, para evitar confusão. Nem o Plano nem os Slides da Semana 16 — a semana em que este pacote é usado de forma central e pela primeira vez em sala — repassavam esse alerta operacional, o que poderia gerar perda real de tempo de aula na "Demonstração" ou na "Implementação guiada" caso a versão instalada exibisse o pacote sob o novo nome.
- **Ação tomada:** adicionado aviso na linha "Materiais necessários" e na seção "Ferramentas" do Plano, e um box de aviso no slide "O que é o Sentis", todos remetendo ao identificador `com.unity.ai.inference` / nome "Inference Engine" e ao Manual do Professor.
- **Prioridade original:** Média

**Problema 3 — corrigido**
- **Documento:** Slides (Semana 16)
- **Local:** Ausência de slide equivalente à etapa 4 do Encontro 2 do Plano ("Encerramento do ciclo dos seis módulos", 15 min)
- **Descrição:** O Plano de Aula prevê explicitamente a recapitulação, em linhas gerais, dos seis módulos e de seus respectivos Micro Games, situando o AI Playground como conjunto integrado — um momento único no semestre, já que nenhuma outra semana de encerramento de módulo fecha o ciclo completo. Os Slides não tinham um slide correspondente: o "Resumo da semana" cobria apenas o conteúdo desta semana, e "Preparação para a Semana 17" mencionava reunir os Micro Games apenas como tarefa futura, sem caráter de síntese retrospectiva.
- **Ação tomada:** adicionado, antes do "Resumo da semana", um novo slide "Encerramento do ciclo dos seis módulos" com uma tabela dos seis módulos, perguntas norteadoras e Micro Games correspondentes.
- **Prioridade original:** Baixa

**Nota — não é um problema**
- **Item:** Nota "FIGURA A PRODUZIR" no slide "Três passos da inferência"
- **Descrição:** Segue o mesmo padrão já observado e validado em outras semanas do curso (diagrama Mermaid já renderizado no slide do ciclo + nota de apresentador pedindo uma captura de tela real complementar, ainda não produzida). Não constitui inconsistência da Semana 16.
- **Item:** Slides sem rótulo textual "Encontro 1" / "Encontro 2"
- **Descrição:** Padrão consistente com todas as demais semanas (confirmado por comparação com a Semana 15): os Slides usam marcadores de seção (`_class: section`) para separar blocos temáticos, não uma divisão literal por encontro. Não é uma inconsistência desta semana especificamente.

---

## Sugestões de Melhoria

Todas as sugestões da revisão original foram aplicadas diretamente no Plano de Aula e nos Slides (ver "Problemas Encontrados" acima). Não há sugestões pendentes.

Observação operacional: as edições foram feitas em `slides.md` (fonte). O PDF e o PPTX da Semana 16 são gerados automaticamente por CI (workflow "Gerar slides com Marp") a partir desse arquivo — será necessário um push do repositório para que os artefatos renderizados reflitam as mudanças (o ambiente de trabalho local não tem um navegador instalado para rodar o Marp CLI e regenerá-los manualmente).

---

## Parecer Final

**Classificação:** Pronta para aplicação.

**Justificativa:** A estrutura pedagógica da semana já estava correta — sequência conceito-antes-de-ferramenta respeitada, tempos exatos e coerentes entre Plano e Slides, pesos avaliativos conferindo com os Critérios de Notas, e Engenharia Reversa bem fundamentada com duas opções deliberadamente contrastantes. Os três problemas identificados (tema do Micro Game ausente, falta de alerta sobre a mudança de identificador do pacote Sentis, ausência de um slide de síntese dos seis módulos) foram corrigidos diretamente no Plano de Aula e nos Slides. Não há pendências conhecidas para aplicação em turma. Recomenda-se apenas confirmar que o PDF/PPTX foram regenerados pelo CI após o commit das alterações em `slides.md`.
