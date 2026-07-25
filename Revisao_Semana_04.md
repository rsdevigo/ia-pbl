# Revisão da Semana 4 — Plano de Aula e Slides

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência
**Curso:** Superior de Tecnologia em Jogos Digitais — IFMS
**Objeto da revisão:** `Plano_de_Aula_Semana_04.md` e `Slides/Semana 4/slides.md` (+ `semana_4_slides.pptx`)
**Referência de verdade:** Apostila — Parte II, Capítulo 6 (Árvores de Comportamento) e Parte VII, Capítulo 14 (Metodologia de Engenharia Reversa de IA)
**Observação:** não há Tutorial dedicado para a Semana 4 no repositório, assim como nas Semanas 2 e 3 — coerente, pois a implementação é conduzida pela "Atividade de Laboratório" e pelo Encontro 2 do próprio Plano. Não há, portanto, lacuna de documento, apenas ausência de um arquivo separado.

---

## Resumo Geral

A Semana 4 encerra a Unidade I com um material sólido e tecnicamente correto. Plano e Slides seguem com precisão a sequência da Apostila (6.1 → 6.2.1 → 6.2.2/6.2.3 → 6.3 → 6.4/demonstração), usam a mesma terminologia (sequência/seletor/paralelo, decoradores, blackboard, tick, sucesso/falha/em execução) e não antecipam GOAP (6.6) nem IA de Utilidade (6.7), tratando-os corretamente apenas no panorama comparativo da seção 6.8 — exatamente como o Cronograma e o Manual do Professor determinam. A introdução formal da metodologia de Engenharia Reversa (Cap. 14, seções 14.1 a 14.3) também é fiel ao roteiro de seis etapas e aos rótulos [Documentado]/[Inferência]/[Especulação] da Apostila, e o caso Halo 2 é corretamente descrito como fonte documentada (GDC 2005, Damian Isla).

O ponto que mais pede atenção é uma quebra de continuidade entre semanas: a seção "Micro Game" do Plano descreve o estado final da Semana 4 com subárvores "Sobreviver"/"Combate" e "Pacífico", mas a Semana 3 — a fonte da HFSM que está sendo migrada — define explicitamente apenas **dois** superestados ("Pacífico" e "Combate"), sem nunca introduzir um superestado "Sobreviver". Um segundo ponto, de impacto moderado, é que a seção "Conteúdos" promete cobertura das seções 6.4 (exemplo comparativo do guarda) e 6.5 (vantagens e limitações), mas nenhuma etapa do Encontro 1 nem slide algum trata esses dois conteúdos de forma dedicada. Nenhum dos dois problemas inviabiliza a aplicação da semana, mas ambos merecem ajuste antes da aula.

---

## Pontos Fortes

- **Sequência didática fiel à Apostila.** Problema (6.1) → nós compostos (6.2.1) → decoradores/folhas/blackboard (6.2.2/6.2.3) → tick e estados de retorno (6.3) → demonstração no Unity Behavior é seguida sem saltos, tanto no Plano quanto nos Slides, com a mesma ordem e os mesmos rótulos de seção usados na Apostila.
- **Exclusão correta e bem justificada de GOAP e Utilidade.** O Plano é explícito ao dizer que a IA de Utilidade será retomada na Semana 9 e que o GOAP é exclusão deliberada do Cronograma (remetendo ao Capítulo 6.5 do Manual do Professor), tratando ambos apenas no quadro comparativo da seção 6.8 — coerente com a nota do CLAUDE.md sobre a remoção de GOAP/ReGoap da lista de ferramentas apresentadas em aula.
- **Introdução da Engenharia Reversa fiel ao Capítulo 14.** O roteiro de seis etapas (definição do problema, coleta, registro, hipóteses, validação, documentação) e os rótulos [Documentado]/[Inferência]/[Especulação] aparecem, em Plano e Slides, com a mesma nomenclatura e ordem da Apostila; o caso *Halo 2* é apresentado com a mesma ressalva de fonte documentada (palestra de Damian Isla, GDC 2005) usada no Capítulo 6 (seção 6.9) e no Capítulo 14.
- **"Dificuldades Esperadas" bem calibradas.** As cinco dificuldades listadas no Plano (confundir sequência/seletor, blackboard indisciplinado, Desafio sem comparação real de alternativas, hipótese apresentada como certeza, superestimar a complexidade de *Halo 2*) espelham exatamente os blocos "❌ Erro Comum" e "⚠️ Atenção" da Apostila nos Capítulos 6 e 14, e não inventam problemas alheios ao conteúdo da semana.
- **Ferramentas corretamente restritas ao panorama comparativo.** Tanto o Plano quanto os Slides deixam explícito que NodeCanvas e Behavior Designer aparecem "apenas como panorama comparativo, sem uso prático nesta semana" — coerente com a seção 6.10 da Apostila e com a tabela de Ferramentas do Cronograma.
- **Verificação da aprendizagem bem ancorada na Rubrica e nos instrumentos já prontos.** A seção "Verificação da Aprendizagem" distribui corretamente os quatro instrumentos do módulo pelos critérios da Rubrica e reforça o uso dos Exercícios de fixação do Capítulo 6 — instrumentos que já existem na Apostila, evitando a criação de questões redundantes.
- **Coerência com os Critérios de Notas.** O peso de 11,67% atribuído ao Módulo 1 confere exatamente com a matriz "Módulos 1 a 6" dos Critérios de Notas (70% dividido em seis módulos iguais).

---

## Problemas Encontrados

### Problema 1
- **Documento:** Plano de Aula (seção "Micro Game") / continuidade com a Semana 3
- **Local:** "Estado ao final da Semana 4" — "subárvores correspondentes aos superestados definidos na Semana 3 (por exemplo, 'Sobreviver'/'Combate' e 'Pacífico')"
- **Descrição:** O `Plano_de_Aula_Semana_03.md` define, de forma consistente e repetida (Objetivos, Conteúdos, Atividade de Laboratório, Dificuldades Esperadas), **exatamente dois** superestados para o Micro Game NPC Decision: "Pacífico" e "Combate". Não há, em nenhum ponto da Semana 3, um superestado "Sobreviver". O Plano da Semana 4, ao descrever o estado final do Micro Game após a migração para Árvore de Comportamento, cita três rótulos — "Sobreviver"/"Combate" e "Pacífico" — misturando os dois superestados reais da Semana 3 com "Sobreviver", que é na verdade o nome de uma das quatro subárvores do exemplo **hipotético e genérico** do guarda usado pela própria Apostila na seção 6.4 (Sobreviver, Combater, Investigar, Patrulhar). O efeito é uma citação que parece descrever o Micro Game real da turma, mas na verdade importa, sem aviso, um rótulo do exemplo de livro que não corresponde ao que os grupos efetivamente implementaram nas Semanas 2 e 3. Isso pode levar o professor a esperar, incorretamente, que os grupos já possuam uma lógica de sobrevivência separada como superestado próprio.
- **Prioridade:** Alta

### Problema 2
- **Documento:** Plano de Aula (seção "Conteúdos") / Slides
- **Local:** Bullets "exemplo do inimigo guarda reexpresso como árvore de comportamento, com comparação às versões FSM (Cap. 3) e HFSM (Cap. 4)... (seção 6.4)" e "vantagens e limitações da árvore de comportamento (seção 6.5)"
- **Descrição:** Ambos os itens são listados como conteúdo previsto da semana, mas nenhuma etapa do Encontro 1 os trata de forma dedicada, e os Slides também não os cobrem como conteúdo autônomo. A etapa 6 do Encontro 1 ("Demonstração no Unity Behavior", 10 min) apresenta apenas um seletor genérico com dois ou três filhos — não a árvore completa do guarda com as quatro subárvores de prioridade (Sobreviver/Combater/Investigar/Patrulhar) e a comparação interpretativa com as versões FSM e HFSM que a seção 6.4 da Apostila desenvolve. Da mesma forma, não há etapa nem slide chamado "vantagens e limitações": o slide mais próximo ("Discussão técnica", ao final) toca em apenas *uma* limitação (a BT não pondera opções graduadas, gancho para a Semana 9), sem cobrir as demais vantagens (modularidade, legibilidade, autoria visual, reatividade, escalabilidade) nem as demais limitações (natureza prescritiva, decisão booleana/ordinal, não generalização) que a seção 6.5 apresenta. A soma dos tempos do Encontro 1 (5+10+15+15+10+10+20+5 = 90 min) já fecha exatamente em 1h30, sem folga para acrescentar essas duas seções sem cortar outra coisa.
- **Prioridade:** Média

### Problema 3
- **Documento:** Plano de Aula ("Preparação do Professor" × "Verificação da Aprendizagem")
- **Local:** Linha "Leitura recomendada" versus parágrafo "Instrumentos de verificação disponíveis na Apostila"
- **Descrição:** A "Leitura recomendada" lista as seções 6.1 a 6.5, 6.8 e 6.10 (mais o Capítulo 14 completo) como leitura do professor, excluindo explicitamente 6.11 (Resumo, Exercícios de fixação e Referências). No entanto, a seção "Verificação da Aprendizagem" instrui o professor a usar justamente "os Exercícios de fixação ao final do Capítulo 6" — que estão na seção 6.11 — como principal fonte de verificação formativa. A leitura recomendada deveria incluir 6.11, já que o próprio Plano depende dela para a condução do Encontro 2.
- **Prioridade:** Baixa

---

## Sugestões de Melhoria

- Corrigir a seção "Micro Game" do Plano, substituindo "Sobreviver"/"Combate" e "Pacífico" por uma referência exata aos dois superestados definidos na Semana 3 ("Pacífico" e "Combate"), ou — caso a intenção seja de fato introduzir uma nova subárvore de sobrevivência nesta semana — explicitar isso como uma decisão nova da Semana 4, e não como algo "definido na Semana 3".
- Incluir, no Encontro 1, uma breve exposição (2 a 3 minutos, aproveitando espaço da etapa "Demonstração no Unity Behavior" ou do "Fechamento") mostrando ao menos o diagrama completo do guarda com as quatro subárvores da seção 6.4, e uma frase de fechamento explícita cobrindo vantagens e limitações (seção 6.5) — mesmo que de forma sintética — para que a lista de "Conteúdos" corresponda ao que é de fato entregue.
- Incluir a seção 6.11 na "Leitura recomendada" do Plano, já que os Exercícios de fixação dali são usados na "Verificação da Aprendizagem".

---

## Atualização

Os três problemas e as três sugestões desta revisão foram aplicados em `Plano_de_Aula_Semana_04.md` e em `Slides/Semana 4/slides.md`:

- **Problema 1 (corrigido):** a seção "Micro Game" do Plano agora referencia exatamente os dois superestados da Semana 3 ("Pacífico" e "Combate"), sem citar "Sobreviver" como se fosse algo definido naquela semana.
- **Problema 2 (corrigido):** a etapa 6 do Encontro 1 foi ampliada (de 10 para 14 min, compensado reduzindo as etapas 1 e 8 de 5 para 3 min cada, mantendo o total de 90 min) para incluir a árvore completa do guarda (seção 6.4, explicitamente rotulada como exemplo da Apostila, distinto do Micro Game da turma) e o quadro de vantagens e limitações (seção 6.5); os Slides ganharam dois novos slides correspondentes ("Exemplo da Apostila: o guarda completo" e "Vantagens e limitações da BT").
- **Problema 3 (corrigido):** a "Leitura recomendada" do Plano agora inclui a seção 6.11.

Os PDFs e PPTX da Semana 4 são gerados automaticamente pelo workflow `marp-slides.yml` a partir do `slides.md` atualizado; não foram editados manualmente.

---

## Parecer Final

**Pronta com pequenos ajustes.**

A Semana 4 cumpre bem sua dupla função de encerrar o Módulo 1 com Árvores de Comportamento e Blackboard e de abrir formalmente a metodologia de Engenharia Reversa que atravessará todo o semestre, com terminologia e sequência consistentes entre Plano e Slides e sem antecipar GOAP ou IA de Utilidade. O Problema 1 (a citação equivocada de "Sobreviver" como superestado da Semana 3) deve ser corrigido antes da aplicação, pois pode gerar expectativa incorreta sobre o que os grupos já implementaram. Os Problemas 2 e 3 são lacunas de conteúdo declarado e de leitura recomendada, de impacto médio a baixo, e podem ser resolvidos em uma revisão de rotina do Plano e dos Slides sem comprometer a aplicação da semana.
