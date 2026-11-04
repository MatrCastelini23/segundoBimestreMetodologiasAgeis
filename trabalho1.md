# Adaptação de metodologia para 


### Alunos: 
- Matheus Janoca Castelini  --  RA: 250289
- Lyzandra Henrique  --  RA: 250395
- Pedro Henrique Gonçalvez de Souza  --  RA: 250275
- Gislaine Rodrigues da SIlveira  --  RA: 250385
- Elienay Henrique da Silva Souza  --  RA: 250283
- Lucas Mateus Galdino dos Santos -- RA: 250272


### Descrição do caso, desenvolvimento de ERP (Enterprise Resource Planning).

Enterprise Resource Planning ou ERP é um sistema de gestão de empresas aonde se guardam dados sensiveis como dados de clientes, faturamento da empresa, notas fiscais geradas, contratos de prestação de serviço ou de compra e venda.

### Usuários e StalkeHolders:

O stakeholder principal seria o gerente geral, com uma finalidade de organizar todo o processo da empresa. <br>
Usuarios se dividiriam em gerentes de setor com permissões de Administrador e colaboradores que ficariam responsaveis pela operação nos setores fiscal, comercial, financeiro, executivo. 

### Diagnóstico:

A divisão das demandas devem partir do produto ou serviço da empresa, aonde todos os setores giram entorno. Definindo como o produto ou serviço será criado, atualizado, lido e, se requirido, excluido podemos trabalhar no desenvolvimento do módulos que atenderam os demais setores. <br>
A equipe seria divida na modalidade Scrum, aonde o Product Owner teria contato direto com o stakeholder e apresataria protótipos, MVPs e colheiria feedbacks. O Scrum master que controlaria a gestão de tarefas com cada time de desenvolvimento.<br>
As tecnologias utilizados Postgresql como banco de dados pelo suporte a JSON e Dados semi-estruturados para tabela de autitoria, NESTJS para consumir APIs de prefeituras e Sefaz para fiscal, Java para eventos com calculos pesados como faturamento da empresa. FrontEnd com seria feito com NextJS para trabalhar pela possibilidade de página carregadas no server side otimizando entrega no navegador e o componentes Reacts dinamizando a navegação dos usuários. <br>
Organizariamos o desenvolvimento em Scrum, as Sprints Goals orientariam o time a chegar no Product Goal que é a gestão da empresa dentro do sistema web. Para organizar as tarefas das sprints utilizariamos o quadro do Kanban para acompanhar o desenvolvimento. E utilizariamos da XP o TDD (Test-Driven Developement) para que as funcionadades finalizadas tenham seus testes. <br>
As restrições seriam herdadas do Kaban, aonde um tarefa filha precisa que sua tarefa pai seja finalizada antes de ser iniciada, também herdariamos do TDD, apenas as tarefas verdes seriam aprovadas, as vermelhas e refatorar devem ser revista (no de refatorar, sejam melhoradas o código). E todo alteração vinda do PO entraria no fluxo do Kanban.<br>

### Problemas e riscos prioritarios

1. Falha de segurança e vazamento de dados sensíveis (LGPD)
O que é: acesso indevido, vazamento ou fraude envolvendo dados financeiros, fiscais, de clientes ou de funcionários.
Exemplo: um desenvolvedor deixa um endpoint de relatório sem verificação de perfil. Qualquer usuário logado, mesmo do estoque, consegue abrir a URL /relatorios/folha e ver os salários de todos os funcionários. 
Consequência: multa da ANPD, obrigação de comunicar o incidente aos titulares, processos judiciais e perda de clientes.

2. Não conformidade regulatória (fiscal, LGPD, auditoria)
O que é: o sistema não cumpre uma obrigação legal.
Exemplo: o módulo fiscal calcula o ICMS-ST com a alíquota errada para vendas interestaduais a um estado específico. Durante meses o sistema emite notas com imposto menor que o devido. A empresa só descobre numa fiscalização e paga a diferença, com multa e juros
Consequência: autuações, multas, notas rejeitadas pela SEFAZ e risco de interdição de operações.

3. Ausência de rastreabilidade e evidências
O que é: não ser possível provar quem fez o quê, quando e com qual aprovação.
Exemplo: o auditor pergunta quem alterou o limite de crédito do cliente X de R$ 10 mil para R$ 100 mil. O sistema não registra o usuário nem a data da alteração.

### Composição proposta + Praticas selecionadas

A abordagem escolhida mistura práticas  do Scrum, XP e Kaban. <br>
Do Scrum utilizariamos sua distribuição de tarefas e responsabilidades em PO, Scrum Master, Sprints, Product Goals. <br>
Do XP utilizariamos o TDD para testar as entregas das sprints. <br>
E do Kaban utilizariamos o quadro para visualizar o status de cada tarefa dentro das sprints.

### Fluxo de entrega

O fluxo resumido dentro das sprints:
> Aguardando desenvolvimento -> Desenvolvendo -> Testando -> Resultado teste -> Entrega.

- Aguardando desevolvimento: 
    - tarefa de menor importancia ou aguardando tarefa pai dentro da sprint.
- Desevolvimento: 
    - Tarefa sendo desenvolvida (e desenvolvimento do teste)
- Testando:
    - Teste de integração.
- Resultado do teste: 
    - Resultado do teste de integração.
- Entrega:
    - Entrega da tarefa.

### Risco da adoção e ações para mitigar

Como principal risco vemos a falha de comunicação se as pontas do desenvolvimento estiverem muito distantes, se apenas o PO tiver contato com o StalkeHolder, ficariamos a merce da interpretação de apenas um membro da equipe para definir o Product Goal e Sprint Goal. Para mitigar esse risco, seria interessante cerimonias entre PO, Scrum Master e um membro da equipe do time de desenvolvimento do módulo junto ao StalkeHolder.

### Evidências para avaliar a proposta

A escolha de misturar essas três abordagens não é apenas comum, mas é considerada uma das formas mais eficientes de gerenciar projetos de alta complexidade como um ERP.
- Evidência de Mercado (The State of Agile Report): Historicamente, os relatórios anuais State of Agile apontam que o Scrum é a estrutura mais utilizada no mundo (geralmente mais de 50%-60% dos times). No entanto, o uso combinado de Scrum + Kanban (Scrumban) e a adoção de práticas de engenharia do XP aparecem logo em seguida como a escolha de times maduros.
- O "Porquê" Científico: O Scrum fornece o ritmo e os papéis de gestão (PO, SM, Sprints), o Kanban melhora o fluxo de valor e a visibilidade (evitando gargalos no desenvolvimento), e o XP traz a excelência técnica (TDD). Sem o XP, o Scrum vira apenas gestão visual, mas o código pode perder qualidade.

