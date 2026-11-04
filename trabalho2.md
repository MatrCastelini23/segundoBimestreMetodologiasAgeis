# B2-T2 — Plano de colaboração, comunicação e organização do time (ERP)

### Alunos: 
- Matheus Janoca Castelini  --  RA: 250289
- Lyzandra Henrique  --  RA: 250395
- Pedro Henrique Gonçalvez de Souza  --  RA: 250275
- Gislaine Rodrigues da SIlveira  --  RA: 250385
- Elienay Henrique da Silva Souza  --  RA: 250283
- Lucas Mateus Galdino dos Santos -- RA: 250272

## 1. Contexto do time e do produto

Seis estudantes constroem um ERP web que guarda dados sensíveis (clientes, faturamento, notas fiscais, contratos) e atende os setores fiscal, comercial, financeiro e executivo. O time trabalha com Scrum (papéis e sprints), Kanban (quadro de fluxo) e TDD do XP (testes junto da entrega), como definido no trabalho 1.

**Time:** Matheus Janoca Castelini, Lyzandra Henrique, Pedro Henrique Gonçalvez de Souza, Gislaine Rodrigues da Silveira, Elienay Henrique da Silva Souza e Lucas Mateus Galdino dos Santos.

**Tecnologias:** PostgreSQL (auditoria em JSON), NestJS (integração com prefeituras e SEFAZ), Java (cálculos pesados, como faturamento) e NextJS (front-end com renderização no servidor).

**Fluxo de entrega no quadro:** Aguardando desenvolvimento → Desenvolvendo → Testando → Resultado do teste → Entrega.

**Riscos que orientam este plano** (do trabalho 1): vazamento de dados sensíveis (LGPD), não conformidade fiscal e falta de rastreabilidade. O risco de adoção também vem de lá: só o PO falar com o stakeholder concentra a interpretação em uma pessoa.

| Papel | Responsabilidade | Responsável |
| --- | --- | --- |
| Product Owner (PO) | Fala com o stakeholder, apresenta protótipos e MVPs, prioriza o backlog | A definir pelo time |
| Scrum Master (SM) | Conduz cerimônias, remove impedimentos, cuida do quadro Kanban | A definir pelo time |
| Desenvolvedores | Constroem os módulos, escrevem os testes (TDD), revisam código | Demais integrantes, por módulo |

## 2. Stakeholders principais

O gerente geral é o stakeholder decisivo; os demais definem requisitos e usam o sistema todos os dias.

| Stakeholder | Interesse | Influência | Como queremos tratá-lo |
| --- | --- | --- | --- |
| Gerente geral | Organizar todo o processo da empresa no sistema | Alta | Participa da Review e valida o Product Goal |
| Gerentes de setor (administradores) | Permissões, relatórios e regras do seu setor | Alta | Validam requisitos e protótipos do seu módulo |
| Colaboradores (fiscal, comercial, financeiro, executivo) | Operação diária simples e correta | Média | Testam MVPs e dão feedback de uso |
| Órgãos externos (SEFAZ, prefeituras, ANPD) | Conformidade fiscal e proteção de dados | Alta, indireta | Seguimos as regras e APIs deles; sem contato direto |

Para reduzir o risco de interpretação única, três pessoas acompanham o stakeholder: o PO, o Scrum Master e um desenvolvedor do módulo em discussão.

## 3. Mapa de comunicação

Cada informação tem um canal, uma frequência e um lugar de registro, para que ninguém dependa de memória ou de conversa solta.

| De → Para | O que circula | Canal | Frequência | Registro |
| --- | --- | --- | --- | --- |
| Time → Time | Andamento e dúvidas rápidas | Grupo de mensagens (WhatsApp ou Discord) | Diária, até 1 dia útil para responder | Pendências viram cartão no quadro |
| Time → Time | Status das tarefas | Quadro Kanban | Atualizado ao mover cada tarefa | O próprio quadro |
| Time → Time | Código e testes | Pull request no repositório | A cada tarefa concluída | Histórico do repositório |
| PO → Time | Prioridades e mudanças de escopo | Planning e quadro | A cada sprint; mudança do PO entra como cartão | Backlog e ata da Planning |
| PO + SM + 1 dev → Stakeholders | Protótipos, MVPs, requisitos | Reunião (presencial ou chamada) | A cada sprint, na Review | Ata de decisões |
| Stakeholders → Time | Feedback e novos pedidos | Via PO, anotado na Review | A cada sprint | Backlog, com a origem do pedido |
| SM → Time | Impedimentos e bloqueios | Daily e grupo | Diária | Lista de impedimentos no quadro |
| Time → Professor | Entregas e dúvidas | Aula e canal indicado pelo professor | Conforme o calendário | Arquivos versionados no repositório |

Regra de ouro: decisão e combinado que não estão escritos no registro do canal não valem como decisão.

## 4. Roteiro das cerimônias

Quatro encontros sustentam o ciclo. Cada um tem objetivo, participantes, duração, roteiro e uma saída registrada. Sprint sugerida: 2 semanas (ajustável ao calendário da disciplina).

### 4.1 Sprint Planning

- **Objetivo:** definir o Sprint Goal e escolher o que cabe na sprint.
- **Participantes:** todo o time; o PO traz o backlog priorizado.
- **Duração:** até 1h30, no início da sprint.
- **Roteiro:** (1) PO apresenta o objetivo e as prioridades (15 min); (2) time esclarece dúvidas e critérios de aceite (25 min); (3) quebra em tarefas filhas e pais, respeitando as dependências do Kanban (35 min); (4) cada tarefa recebe um responsável e um teste esperado, TDD (15 min).
- **Saída:** Sprint Goal escrito e quadro montado em "Aguardando desenvolvimento".

### 4.2 Daily (15 minutos)

- **Objetivo:** alinhar o dia e expor impedimentos cedo.
- **Participantes:** time; SM conduz.
- **Duração e frequência:** 15 min, a cada dia combinado (presencial ou em chamada curta).
- **Roteiro:** cada pessoa diz o que avançou, o que fará e o que a bloqueia, olhando o quadro. Discussões longas saem da Daily e viram conversa à parte.
- **Saída:** impedimentos registrados na lista do quadro, cada um com um responsável por resolver.

### 4.3 Sprint Review com stakeholders

- **Objetivo:** mostrar o que foi entregue e colher feedback do gerente geral e dos gerentes de setor.
- **Participantes:** PO, SM, um desenvolvedor do módulo e os stakeholders; os demais assistem se possível.
- **Duração:** até 1h, no fim da sprint.
- **Roteiro:** (1) PO relembra o Sprint Goal (5 min); (2) demonstração do que passou nos testes (25 min); (3) stakeholders comentam e priorizam (20 min); (4) combinar os próximos passos (10 min).
- **Saída:** ata com decisões e pedidos novos, que entram no backlog como cartões.

### 4.4 Retrospectiva

- **Objetivo:** melhorar a forma de trabalhar, olhando o processo e não as pessoas.
- **Participantes:** todo o time; SM facilita; PO participa como membro do time.
- **Duração:** até 1h, depois da Review.
- **Roteiro:** (1) revisar as ações da retrospectiva anterior e os indicadores de saúde (10 min); (2) o que funcionou, o que travou e o que tentar (25 min); (3) votar até 3 melhorias (10 min); (4) definir no máximo 2 ações, com dono e prazo (15 min).
- **Saída:** 1 a 2 ações registradas no quadro, revisadas na próxima retrospectiva.

Cerimônia extra (opcional): **refinamento do backlog**, 30 min no meio da sprint, para quebrar itens grandes e antecipar dúvidas técnicas e legais (LGPD e fiscal).

## 5. Acordos de trabalho

Cada acordo pode ser observado no quadro, no repositório ou nas atas. Se não dá para verificar, não é um acordo.

| Tema | Acordo | Como verificamos |
| --- | --- | --- |
| Quadro | Quem começa uma tarefa a move para "Desenvolvendo" no mesmo dia | Cartões sem movimento por mais de 2 dias aparecem na Daily |
| Dependências | Tarefa filha só começa quando a tarefa pai estiver concluída | Cartão filho bloqueado enquanto o pai não está em "Entrega" |
| Testes (TDD) | Nenhuma tarefa vai para "Entrega" sem teste verde; testes vermelhos ou de refatoração voltam para revisão | Resultado do teste anexado ao cartão |
| Código | Todo pull request é revisado por pelo menos 1 colega antes do merge | Histórico do repositório |
| Segurança e LGPD | Endpoint novo só entra com verificação de perfil e sem dado sensível em log | Item no checklist do pull request |
| Rastreabilidade | Alteração de dado crítico grava usuário, data e valor anterior na tabela de auditoria | Teste automatizado cobre a gravação |
| Respostas | Mensagens ao time são respondidas em até 1 dia útil | Combinado revisto na retrospectiva |
| Presença | Quem não puder comparecer avisa antes e lê a ata depois | Ata registra ausências e quem recebeu o resumo |
| Mudanças do PO | Toda mudança entra como cartão no Kanban, nunca só em conversa | Cartão com data e origem |
| Divisão de trabalho | Conhecimento de cada módulo é compartilhado por pelo menos 2 pessoas | Revisão de código cruzada entre módulos |

## 6. Regras para feedback e decisão

### Feedback

- Feedback fala do trabalho (código, tarefa, entrega), não da pessoa. Formato: o que observei, o efeito, o que sugiro.
- Feedback sobre código vai no pull request, por escrito. Feedback sobre comportamento ou ritmo vai em conversa direta ou na retrospectiva.
- Quem recebe responde em até 2 dias úteis: aceita, discute ou explica por que não fará.
- Feedback de stakeholders é anotado na Review e registrado pelo PO como cartão, com a origem do pedido.

### Decisão

| Tipo de decisão | Quem decide | Como |
| --- | --- | --- |
| Prioridade do backlog e escopo | PO, ouvindo o time | Decide na Planning; mudança no meio da sprint entra como cartão e só é aceita se o time confirmar a capacidade |
| Como implementar (técnica) | Quem desenvolve, com revisão de pelo menos 1 colega | Discussão no pull request; empate vai para a Daily |
| Processo do time (acordos, cerimônias) | Todo o time | Consenso na retrospectiva; sem consenso, votação com maioria simples |
| Temas de segurança, LGPD e fiscal | Time inteiro, com a regra mais conservadora | Se há dúvida, vale o caminho mais seguro até esclarecer |
| Prazos e entregas | Todo o time, com o Scrum Master | Decisão na Planning, registrada na ata |

### Registro de decisões

Toda decisão relevante vira uma linha em um arquivo `decisoes.md` no repositório, com data, decisão, motivo, quem participou e o que foi descartado. O SM confere na retrospectiva se as decisões da sprint foram registradas.

## 7. Estratégia inicial para conflitos

Conflito é esperado em um time de seis com um produto complexo. O objetivo é tratá-lo cedo, sobre o problema e não sobre a pessoa.

1. **Conversa direta.** Quem percebeu o problema fala primeiro com a pessoa envolvida, em até 2 dias, usando o formato do feedback (observação, efeito, pedido).
2. **Mediação do Scrum Master.** Se não resolver, o SM ouve as partes separadamente e depois juntas, e propõe um combinado por escrito.
3. **Pauta da retrospectiva.** Se o tema é recorrente ou afeta o time inteiro, vira item da retrospectiva, tratado como problema de processo.
4. **Escalonamento ao professor.** Se continuar sem solução depois dos passos anteriores, o time apresenta o caso ao professor, com os fatos registrados.

Se o conflito envolve o próprio SM, a mediação é feita por outro integrante escolhido pelas partes.

| Situação provável | Primeira resposta |
| --- | --- |
| Divergência técnica (por exemplo, Java ou NestJS para um cálculo) | Critérios objetivos (desempenho, prazo, domínio do time), teste rápido e registro em `decisoes.md` |
| Prioridade disputada entre setores | PO decide com base no Product Goal e explica o motivo na Planning |
| Tarefa atrasada ou sobrecarga | Dividir a tarefa, pedir ajuda na Daily e rever a capacidade na próxima Planning |
| Mudança de escopo no meio da sprint | Vira cartão; time confirma capacidade antes de aceitar |
| Falta de participação de alguém | Conversa direta sobre o que está travando, sem julgamento, antes de qualquer escalonamento |

## 8. Indicadores de saúde do time

Os indicadores apoiam a conversa na retrospectiva e a melhoria do processo. Eles medem o time, não pessoas: nunca são usados para rotular, comparar ou avaliar alguém. As respostas individuais são anônimas e só o resultado do time é discutido.

| Indicador | Como medir (a cada sprint) | Sinal de alerta | Pergunta para a retrospectiva |
| --- | --- | --- | --- |
| Clareza de objetivo | Nota de 1 a 5: "Sei qual é o Sprint Goal e por que ele importa" | Média abaixo de 4 | O que ficou confuso no objetivo? |
| Segurança para falar | Nota de 1 a 5: "Posso discordar ou dizer que errei sem receio" | Média abaixo de 4 ou piora por 2 sprints | Que situação tornou difícil falar? |
| Impedimentos recorrentes | Quantidade de impedimentos da lista que se repetem em 2 sprints | 2 ou mais repetidos | Qual a causa comum e quem pode removê-la? |
| Participação nas decisões | Percentual de decisões registradas com participação de mais de 1 pessoa além do PO | Abaixo de 80% | Quais decisões foram tomadas sem o time? |
| Ações de retrospectiva concluídas | Ações concluídas dividido pelas ações definidas | Abaixo de 70% | As ações eram pequenas e realistas? |
| Dependência de especialistas | Módulos que só uma pessoa consegue alterar | 1 ou mais módulos | Como espalhar esse conhecimento (revisão cruzada, pares)? |
| Qualidade da comunicação com stakeholders | Nota de 1 a 5 de PO, SM e stakeholders: "O pedido foi entendido e o retorno veio no prazo" | Média abaixo de 4 | Que pedido foi mal interpretado e por quê? |

**Como usamos:** o SM coleta as notas em um formulário curto antes da retrospectiva, apresenta a tendência (e não a média de uma sprint isolada) e o time escolhe no máximo 1 indicador para trabalhar. Os limites acima são pontos de partida e podem ser ajustados pelo time.

## 9. Justificativas das escolhas

Cada escolha deste plano responde a um risco ou a uma característica do ERP descrita no trabalho 1.

| Escolha | Por que a fizemos | Risco que reduz |
| --- | --- | --- |
| Review com PO, SM e um desenvolvedor junto ao stakeholder | Evita que o Product Goal dependa da interpretação de uma só pessoa | Falha de comunicação entre as pontas |
| Mudança do PO sempre vira cartão | Mantém o escopo visível e a capacidade do time protegida | Escopo mudando sem registro |
| Ata e `decisoes.md` | Permite provar o que foi decidido, quando e por quem, o mesmo princípio da tabela de auditoria do sistema | Falta de rastreabilidade e evidências |
| Checklist de segurança e LGPD no pull request | Verifica perfil de acesso e dados sensíveis antes do merge | Vazamento de dados sensíveis |
| Regra mais conservadora em temas fiscais e de LGPD | Um erro de alíquota ou de permissão custa multa e perda de clientes | Não conformidade regulatória |
| Teste verde antes da entrega e revisão por pares | Une o TDD do XP ao fluxo do Kanban e distribui conhecimento | Qualidade baixa e dependência de especialistas |
| Daily curta e lista de impedimentos | Expõe bloqueios cedo e dá dono a cada um | Impedimentos recorrentes |
| Retrospectiva com no máximo 2 ações | Ações pequenas têm mais chance de serem concluídas | Retrospectivas sem efeito prático |
| Escada de conflitos (direta, SM, retrospectiva, professor) | Começa pelo nível mais leve e preserva a relação do time | Conflito escalando ou ficando escondido |
| Indicadores anônimos e por time | Apoiam melhoria sem expor ou rotular pessoas | Medo de falar e uso punitivo dos dados |

O plano mantém a lógica do trabalho 1: Scrum dá o ritmo e os papéis, Kanban dá visibilidade ao fluxo e XP garante a qualidade técnica. Este documento acrescenta o que faltava para o time funcionar junto: como conversar, decidir, discordar e aprender.
