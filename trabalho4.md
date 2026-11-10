# Trabalho 4

### Alunos: 
- Matheus Janoca Castelini  --  RA: 250289
- Lyzandra Henrique  --  RA: 250395
- Pedro Henrique Gonçalvez de Souza  --  RA: 250275
- Gislaine Rodrigues da SIlveira  --  RA: 250385
- Elienay Henrique da Silva Souza  --  RA: 250283
- Lucas Mateus Galdino dos Santos -- RA: 250272

# Planejamento do Produto: Módulo de Geração de Nota Fiscal

> Observação: o documento original (trabalho3.md) define o contexto, o quadro Kanban com limites de WIP e o exemplo da Nota Fiscal. Backlog priorizado, estimativas, plano de sprint, papéis e riscos foram propostos a partir dele e devem ser validados pelo time, principalmente as estimativas.

## 1. Contexto e objetivo do produto

O produto é um módulo de **geração de Nota Fiscal (NF)** para uma empresa prestadora de serviços. O usuário emite a NF a partir da composição de cada serviço ou produto, e o sistema faz a emissão via integração com a **Sefaz**.

- **Objetivo:** permitir que o usuário gere NFs de forma automatizada, receba o retorno da Sefaz (emitida ou com erro), envie a nota ao cliente por e-mail e gere relatórios e fechamentos do período.
- **Fora do escopo:** integração com sistemas de prefeitura.
- **Restrições:** suporte a vários tipos de nota; o usuário é responsável por editar a composição do produto ou serviço.

## 2. Abordagem adaptada

Recomendação: **Scrumban**, ou seja, o fluxo Kanban já configurado com uma cadência leve de Scrum por cima.

- **Do Kanban:** quadro com 5 colunas (Aguardando desenvolvimento, Em desenvolvimento, Em testes, Refatorando, Entregue), limites de WIP (4/2/2/2/sem limite), labels de status e puxada de tarefas conforme a capacidade.
- **Do Scrum:** sprints de 2 semanas com objetivo definido, planning, daily, review e retrospectiva.
- **Por que misturar:** o Kanban dá controle de gargalos, mas sozinho não dá um horizonte de entrega. A sprint dá meta e ritmo, sem abrir mão dos limites de WIP.

## 3. Backlog priorizado

A ordem segue dependência técnica e valor de negócio (MoSCoW).

| # | Item | Prioridade | Justificativa |
|---|---|---|---|
| 1 | Integração com a Sefaz | Must | Sem ela não existe NF; é a base de tudo |
| 2 | Composição editável de produtos/serviços | Must | Alimenta os dados da nota |
| 3 | Suporte a vários tipos de nota | Must | Restrição explícita do documento |
| 4 | Notificação dos retornos da Sefaz (sucesso/erro) | Must | Critério de aceitação |
| 5 | Envio da NF por e-mail ao cliente | Must | Critério de aceitação |
| 6 | Sistema de filas | Should | Necessário para relatório e fechamento |
| 7 | Geração de relatórios por período | Should | Parte da Definição de Pronto |
| 8 | Exportação em PDF e Excel | Should | Complementa os relatórios |
| 9 | Fechamento de NF (.zip com XML e PDF) | Should | Parte da Definição de Pronto |

## 4. Estimativas justificadas

Story points em Fibonacci, por complexidade relativa. Sugere-se confirmar com planning poker.

| Item | Pontos | Justificativa |
|---|---|---|
| Integração Sefaz | 13 | Maior incerteza: API externa, autenticação, tratamento de respostas e ambiente de homologação |
| Composição editável | 8 | Regras de negócio e interface de edição |
| Vários tipos de nota | 8 | Variação de layout e campos, com mais casos de teste |
| Notificação de retornos | 5 | Depende da resposta da Sefaz; baixa complexidade própria |
| Envio por e-mail | 3 | Integração conhecida e escopo pequeno |
| Sistema de filas | 8 | Infraestrutura nova, com reprocessamento e falhas |
| Relatórios por período | 5 | Consultas e filtros por data |
| Exportação PDF/Excel | 5 | Duas bibliotecas e formatos |
| Fechamento (.zip) | 5 | Agrupar arquivos XML/PDF, rodando pela fila |
| **Total** | **60** | |

Com velocidade assumida de cerca de 20 a 24 pontos por sprint, o produto fecha em **3 sprints**. Esse valor deve ser calibrado após a Sprint 1.

## 5. Objetivo e planejamento de Sprint

| Sprint | Objetivo | Itens | Pontos |
|---|---|---|---|
| **1** | Emitir uma NF de teste (homologação) a partir de uma composição editável e receber o retorno da Sefaz | Integração Sefaz, Composição editável | 21 |
| **2** | Cobrir os tipos de nota e fechar o ciclo com o cliente (notificação e e-mail), com a fila pronta | Tipos de nota, Notificação, E-mail, Filas | 24 |
| **3** | Entregar relatórios e fechamento, com a fila processando os eventos | Relatórios, Exportação, Fechamento + correções | 15 + buffer |

Na Sprint 1, os cartões entram em "Aguardando desenvolvimento" (WIP 4) e são puxados para "Em desenvolvimento" (WIP 2). O objetivo da sprint é medido pela demonstração de uma NF emitida em homologação.

## 6. Políticas e Definition of Done

### Políticas do quadro

- Respeitar os limites de WIP. Ao chegar no limite, ninguém puxa tarefa nova; o time ajuda a destravar a coluna.
- Só se puxa tarefa da coluna anterior quando ela está pronta para essa etapa.
- Tarefa bloqueada recebe etiqueta visível e é tratada na daily.
- "Refatorando" só recebe cartões com débito técnico identificado, para não virar fila de retrabalho.
- Cada cartão deve ter objetivo, critérios de aceitação, observações e responsável (como no template da NF).

### Definition of Done (por item)

- Código revisado por outro integrante (pull request aprovado).
- Testes executados e aprovados.
- Critérios de aceitação do cartão atendidos.
- Funcionamento validado em ambiente de homologação.
- Documentação básica atualizada.
- Cartão movido para "Entregue" (código em produção).

### Definição de Pronto da funcionalidade NF (do documento original)

- Integração com a Sefaz funcionando.
- Campos de edição de composição de serviços e produtos.
- Geração de relatório e fechamento.

## 7. Comunicação e responsabilidades

Papéis sugeridos, a serem ajustados pelo grupo:

| Papel | Responsabilidade | Sugestão |
|---|---|---|
| Product Owner | Priorizar o backlog e validar critérios de aceitação | 1 integrante |
| Facilitador (Scrum Master) | Conduzir cerimônias, cuidar dos WIP e remover impedimentos | 1 integrante |
| Desenvolvedores | Implementar, revisar código e testar | Os demais, com divisão por módulo (Sefaz, composição, relatórios/filas) |

### Cerimônias

- **Planning** (início da sprint): define o objetivo e puxa itens.
- **Daily** (15 min): o que foi feito, o que vem a seguir e impedimentos.
- **Revisão do quadro** (semanal): checa gargalos e WIP.
- **Review** (fim da sprint): demonstração do incremento.
- **Retrospectiva** (após a review): melhorias de processo.

### Canais

- Trello como fonte única da verdade das tarefas.
- Grupo de mensagens (WhatsApp ou Discord) para dúvidas rápidas.
- GitHub para código e revisão.

## 8. Riscos, respostas e evidências

| Risco | Prob./Impacto | Resposta | Evidência |
|---|---|---|---|
| Instabilidade ou complexidade da integração com a Sefaz | Alta / Alto | Começar por ela na Sprint 1, usar homologação e tratar erros e reenvio | Cartão da integração e retorno de teste |
| Acúmulo de tarefas em "Em testes" (WIP 2) | Média / Médio | Respeitar WIP, parar de puxar e ajudar a testar | Quadro Kanban com limiteas visíveis |
| Variedade de tipos de nota maior que o previsto | Média / Alto | Dividir por tipo, entregar o mais comum primeiro e revisar a estimativa | Backlog atualizado |
| Fila de processamento causar atrasos ou perda de eventos | Média / Alto | Reprocessamento e logs; testar com carga | Testes e logs da fila |
| Erro no cálculo ou composição da nota | Baixa / Alto | Revisão de código, testes e validação pelo PO | Critérios de aceitação no cartão |
| Dependência de poucas pessoas em módulos críticos | Média / Médio | Revisão cruzada e rodízio de tarefas | Histórico de revisões |
| Acúmulo de débito técnico | Média / Médio | Coluna "Refatorando" com WIP 2 e itens na retro | Cartões de refatoração |

### Evidências de acompanhamento

- Captura do quadro com as colunas e limites de WIP (imagens já presentes no trabalho3.md).
- Detalhamento de um cartão.
- A cada sprint, o resultado da retrospectiva com os riscos revistos.