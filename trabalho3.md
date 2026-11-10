# Trabalho 3

### Alunos: 
- Matheus Janoca Castelini  --  RA: 250289
- Lyzandra Henrique  --  RA: 250395
- Pedro Henrique Gonçalvez de Souza  --  RA: 250275
- Gislaine Rodrigues da SIlveira  --  RA: 250385
- Elienay Henrique da Silva Souza  --  RA: 250283
- Lucas Mateus Galdino dos Santos -- RA: 250272


## Board no Trelo
Link:
https://trello.com/b/6n9UZGS3/meu-quadro-do-trello

![alt text](image.png)

## Demonstração do Board:

| Tarefa | Aguardando desenvolvimento | Em desenvolvimento | Em testes | Refatorando | Entregue |
| --- | --- | --- | --- | --- | --- |
| Explicação | Aguardando dev fazer o pull | Task sendo desenvolvida | Tarefa sendo testada | Código sendo melhorado | Código em produção |
| WIP | 4 | 2 | 2 | 2 | No limit |
| Labels | Aguardando | Desenvolvendo | Testando | Refatorando | Em Produção |


## Template de Exemplo: 

### Geração de Nota Fiscal:

- Objetivo: 
> Como usuario quero gerar nota fiscal de acordo com a composição de cada serviço prestado na empresa.
- Critério de aceitação:
    - A NF deve ser gerada via integração com Sefaz
    - Quando gerada deve ser notificado que a nota foi emitida
    - Quando emitida a Nota deve ser enviada por e-mail para o respectivo cliente
    - Se der erro na emissão da nota deve ser notificado ao usuário responsavel pela emissão

- Observações e restrições:
    - O sistema deve aceitar varios tipos de Notas
    - O sistema deve dar ao usuario a responsabilidade de editar a composição do produto ou serviço para emissão da nota
    - Não é necessário integração com sistemas de prefeitura nesse objetivo

- Definição de Pronto:
    - Integração com o Sefaz funcionando
    - Campos de edição de composição de serviços e produtos
    - Geração de relatório e fechamento.

### Itens do Fluxo

- Sistemas de Filas:
    - As filas vão ficar responsaveis para as grandes operações.
    - No caso das NF os eventos de relatório e fechamento entraram em uma fila para que sejam processados.

- Exportação em Excel e PDF
    - Os relatórios devem ser exportados em dois formatos de arquivo (PDF e Excel)

- Geração de Relatórios
    - Uma função para geração de relatórios de notas fiscais emitadas em um periodo determinado pelo usuario.

- Integração com o Sefaz
    - Integração completa com o sistema do Sefaz para que as notas sejam enviadas para serem enviadas para emissão e a resposta seja processada para que o usuario saiba se a nota enviada foi emitida ou deu falha.

- Fechamento de NF
    - A opção de fechamento deve disponibilizar ao usuarios baixar uma pasta .zip com todas as notas (XML e PDF) emitidas em um período determinado pelo usuário. 

- Notificação de notas
    - Sistema que notifica os retornos do Sefaz para o usuario

### Evidencias de uso do Fluxo

#### Aplicação do fluxo Kanban
![alt text](image-1.png)

#### Detalhamento de uma tarefa:
![alt text](image-2.png)

### Breve justificativa da configuração

A configuração do quadro Kanban foi definida com o objetivo de proporcionar maior organização, transparência e controle sobre o fluxo de desenvolvimento.

Foram estabelecidas cinco etapas para representar o ciclo de vida das tarefas:
- Aguardando desenvolvimento: reúne tarefas que já foram planejadas, mas ainda aguardam o início do desenvolvimento. O limite de WIP é 4 para evitar o acúmulo excessivo de atividades pendentes.
- Em desenvolvimento: concentra as tarefas que estão sendo implementadas pelos desenvolvedores. O limite de WIP é 2 para incentivar o foco e evitar que muitas atividades sejam iniciadas simultaneamente.
- Em testes: reúne as funcionalidades que passaram pelo desenvolvimento e precisam ser validadas. O limite de WIP é 2 para garantir atenção adequada à qualidade das entregas.
- Refatorando: representa as tarefas que necessitam de melhorias estruturais, otimização ou ajustes no código. O limite de WIP é 2 para evitar o acúmulo de atividades de melhoria.
- Entregue: contém as tarefas concluídas e disponibilizadas em produção. Essa coluna não possui limite de WIP, pois representa o histórico de entregas realizadas.
As etiquetas (Labels) foram utilizadas para facilitar a identificação visual da situação de cada tarefa. Além disso, os limites de WIP (Work in Progress) foram definidos para controlar o volume de atividades simultâneas, reduzir gargalos e incentivar a conclusão das tarefas antes do início de novas atividades.

Dessa forma, o fluxo permite acompanhar o progresso do projeto, identificar etapas com acúmulo de tarefas e melhorar a previsibilidade das entregas.