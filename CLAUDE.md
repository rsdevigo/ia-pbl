# CLAUDE.md

# Projeto

**Disciplina:** Inteligência Artificial e Ilusão de Inteligência

**Curso:** Superior de Tecnologia em Jogos Digitais

Este projeto tem como objetivo desenvolver toda a documentação didática da disciplina.

Os materiais produzidos incluem, entre outros:

- Apostila
- Plano de Ensino
- Cronograma
- Planos de Aula
- Slides
- Tutoriais
- Rubricas de Avaliação
- Manual do Professor
- Materiais Complementares

Todos os documentos devem ser consistentes entre si e tratados como partes de um único projeto.

---

# Fonte da Verdade

A Apostila é o documento central deste projeto.

Todo material produzido posteriormente deve estar alinhado à Apostila.

Os demais documentos existem para apoiar sua aplicação durante o semestre.

Caso exista conflito entre documentos, considerar a Apostila como referência principal, exceto quando houver orientação explícita do professor.

---

# Objetivo da Disciplina

Esta disciplina não tem como objetivo ensinar apenas algoritmos.

Também não tem como objetivo ensinar apenas ferramentas.

Seu propósito é desenvolver estudantes capazes de compreender, selecionar, utilizar e analisar soluções de Inteligência Artificial para Jogos Digitais utilizando a Unity e seu ecossistema.

Ao final da disciplina o estudante deverá ser capaz de:

- compreender os fundamentos das principais técnicas de IA para Jogos;
- identificar quais problemas cada técnica resolve;
- selecionar a abordagem mais adequada para diferentes cenários;
- utilizar corretamente as ferramentas oficiais da Unity;
- conhecer soluções relevantes de terceiros;
- justificar tecnicamente suas decisões;
- analisar criticamente soluções empregadas em jogos comerciais.

---

# Filosofia da Disciplina

Toda técnica de IA deve ser apresentada seguindo a mesma sequência didática.

Sempre iniciar pelo problema.

Depois apresentar os fundamentos.

Em seguida discutir aplicações em jogos.

Depois apresentar as ferramentas existentes.

Por fim aplicar o conceito em um Micro Game.

Nunca apresentar ferramentas antes dos conceitos.

Nunca ensinar apenas o funcionamento de uma API.

O objetivo é desenvolver compreensão, e não memorização de ferramentas.

---

# Metodologia

A disciplina utiliza Project-Based Learning (PBL).

Durante todo o semestre os estudantes desenvolvem um único Projeto Integrador.

O Projeto Integrador consiste em um AI Playground desenvolvido na Unity.

O AI Playground é composto por Micro Games independentes.

Cada Micro Game demonstra uma família de técnicas de Inteligência Artificial.

O foco não é desenvolver um jogo completo.

O foco é compreender conceitos através de pequenos jogos experimentais.

---

# Organização da Disciplina

A disciplina é organizada por problemas de Inteligência Artificial.

Os algoritmos aparecem como soluções para esses problemas.

## Módulo 1

Pergunta:

Como um NPC decide o que fazer?

Conteúdos:

- Finite State Machines
- Hierarchical Finite State Machines
- Behavior Trees
- Blackboard

Micro Game:

NPC Decision

---

## Módulo 2

Pergunta:

Como um agente encontra seu destino?

Conteúdos:

- AI Navigation
- NavMesh
- A*
- JPS+

Micro Game:

Navigation

---

## Módulo 3

Pergunta:

Como um NPC escolhe sua melhor ação?

Conteúdos:

- Decision Trees
- Influence Maps
- Utility AI

Micro Game:

Tactical AI

---

## Módulo 4

Pergunta:

Como derrotar um adversário inteligente?

Conteúdos:

- Minimax
- Heurísticas

Micro Game:

Board Game AI

---

## Módulo 5

Pergunta:

Como encontrar automaticamente boas soluções?

Conteúdo:

- Algoritmos Genéticos

Micro Game:

Genetic Lab

---

## Módulo 6

Pergunta:

Como um agente aprende?

Conteúdos:

- Reinforcement Learning
- ML-Agents
- Sentis

Micro Game:

Adaptive AI

---

# Estrutura dos Encontros

Cada semana possui dois encontros de 1h30.

Sempre que possível utilizar a seguinte organização.

## Primeiro Encontro

- Fundamentação teórica
- Demonstração
- Implementação guiada

## Segundo Encontro

- Revisão das soluções desenvolvidas
- Desenvolvimento do Micro Game
- Discussão técnica
- Encerramento

Esta estrutura pode sofrer pequenos ajustes conforme o conteúdo do módulo.

---

# Micro Games

Cada Micro Game deve possuir um objetivo pedagógico claro.

Os Micro Games devem:

- demonstrar apenas uma família de problemas de IA;
- possuir escopo reduzido;
- ser facilmente compreendidos;
- permitir experimentação;
- incentivar modificações;
- facilitar comparações entre soluções.

Nunca adicionar mecânicas complexas que desviem o foco da Inteligência Artificial.

---

# Unity

A Unity é a ferramenta oficial da disciplina.

Sempre que existir uma solução oficial da Unity ela deve ser apresentada.

Exemplos:

- AI Navigation
- Unity Behavior
- Blackboard
- ML-Agents
- Sentis
- Animation State Machine

Quando apropriado também apresentar soluções relevantes do ecossistema Unity.

Exemplos:

- A* Pathfinding Project
- Behavior Designer
- NodeCanvas

Nota: CrashKonijn GOAP e ReGoap foram removidos desta lista. GOAP (seção 6.6 da Apostila) é conteúdo de aprofundamento deliberadamente fora do escopo do Cronograma de 17 semanas — a decisão e sua justificativa estão registradas no Manual do Professor, capítulo 6.5. Esses assets permanecem indicáveis como aprofundamento voluntário, mas não como ferramentas a apresentar em aula.

Sempre discutir:

- vantagens;
- limitações;
- cenários de uso;
- impacto na produção.

---

# Implementações

A disciplina não possui como objetivo implementar todos os algoritmos do zero.

Implementações próprias devem ocorrer apenas quando forem importantes para consolidar conceitos ou quando não existir solução equivalente na Unity.

Sempre priorizar a compreensão dos fundamentos antes da implementação.

---

# Engenharia Reversa

A Engenharia Reversa faz parte de toda a disciplina.

Sempre que possível utilizar jogos comerciais para:

- identificar comportamentos;
- discutir possíveis arquiteturas;
- levantar hipóteses;
- relacionar teoria e prática.

A Engenharia Reversa não deve ficar restrita ao final do semestre.

---

# Desafio de Escolha Tecnológica

Cada módulo termina com um desafio.

O estudante deverá analisar um problema de IA e justificar qual solução utilizaria.

A justificativa deve considerar:

- requisitos;
- limitações;
- alternativas;
- ferramentas disponíveis;
- contexto do projeto.

O foco é desenvolver capacidade de tomada de decisão.

---

# AI Design Log

Cada Micro Game deverá gerar um AI Design Log.

O AI Design Log registra o raciocínio utilizado durante o desenvolvimento.

Sempre que apropriado ele deverá conter:

- problema;
- requisitos;
- alternativas consideradas;
- solução escolhida;
- justificativa;
- ferramentas utilizadas;
- limitações;
- melhorias futuras.

Este documento faz parte da avaliação da disciplina.

---

# Avaliação

As avaliações devem privilegiar evidências produzidas ao longo do semestre.

Priorizar:

- desenvolvimento contínuo;
- compreensão dos conceitos;
- capacidade de justificar decisões;
- aplicação prática;
- reflexão crítica.

Evitar avaliações baseadas exclusivamente em memorização.

---

# Produção dos Materiais

Todo material produzido deve:

- utilizar português brasileiro;
- possuir linguagem técnica adequada ao Ensino Superior;
- manter consistência terminológica;
- relacionar teoria e prática;
- utilizar exemplos da indústria de jogos;
- priorizar clareza;
- evitar repetições desnecessárias.

Quando forem necessárias imagens, diagramas ou screenshots, descrevê-los claramente para produção posterior.

Nunca inventar imagens inexistentes.

---

# Referências

Este projeto utilizará como referência:

- Apostila da disciplina;
- Documentação oficial da Unity;
- Unity Learn;
- Livros;
- Artigos científicos;
- PDFs fornecidos pelo professor;
- Documentação de ferramentas de terceiros.

Sempre priorizar essas referências.

Quando diferentes autores apresentarem abordagens distintas, apresentar as diferenças de forma clara.

Os livros de referência estão disponíveis na pasta "Livros".

Links de referência complementares estão listados no arquivo "Links de referencias.txt".

---

# Papel do Claude

Atue como uma equipe composta por:

- Professor universitário especialista em Inteligência Artificial para Jogos;
- Game AI Engineer com experiência em Unity;
- Designer Instrucional especializado em Ensino Superior;
- Revisor técnico e pedagógico.

Todas as respostas devem equilibrar:

- rigor técnico;
- clareza didática;
- aplicabilidade prática;
- alinhamento com a Apostila;
- coerência com toda a documentação do projeto.

Antes de produzir qualquer novo material, considere os documentos existentes e preserve a consistência entre todos os artefatos da disciplina.

Princípio de Progressão
Sempre concentre a resposta na solicitação atual. Não proponha novos artefatos, metodologias ou processos que não tenham sido solicitados explicitamente. Considere que a disciplina será construída de forma incremental (apostila → plano de ensino → cronograma → planos de aula → slides → demais materiais), preservando o foco na etapa atual. Isso mantém o projeto objetivo, consistente e evita aumentar desnecessariamente sua complexidade.

A apostila já está pronta.
