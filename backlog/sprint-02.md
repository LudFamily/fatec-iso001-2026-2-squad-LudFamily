# Backlog — Sprint 2

## LudCommerce

**Período:** 29/08/2026 a 12/09/2026

**Objetivo da Sprint:**

Definir a arquitetura técnica inicial da LudCommerce, identificar seus principais componentes, processos e serviços, e mapear os riscos operacionais relacionados ao funcionamento da plataforma.

---

## Contexto

A LudCommerce é uma empresa de médio porte que atua no comércio eletrônico de produtos de informática. A plataforma atende consumidores e empresas e comercializa diferentes tipos de hardware e periféricos.

O modelo de negócio utiliza estoque próprio para produtos disponíveis e aquisição sob demanda junto a fornecedores parceiros quando necessário.

A Sprint 2 dará continuidade à definição do cenário de negócio, avançando para a arquitetura técnica e para a identificação dos riscos operacionais que deverão ser tratados nas próximas Sprints.

---

# Backlog da Sprint

## S2-01 — Definir requisitos iniciais

**Descrição:**

Identificar os principais requisitos funcionais e não funcionais necessários para o funcionamento da LudCommerce.

**Responsável:** Lucas Eugenio

**Prioridade:** Alta

### Critérios de aceite

- [ ] Os principais requisitos funcionais estão documentados.
- [ ] Os requisitos relacionados a catálogo, estoque e pedidos estão contemplados.
- [ ] Os requisitos relacionados a pagamento e entrega estão contemplados.
- [ ] Os principais requisitos não funcionais estão identificados.
- [ ] Disponibilidade, segurança, desempenho e integridade são considerados.

### Conexão com Sistemas Operacionais

- Processos e serviços.
- Memória e desempenho.
- Armazenamento.
- Permissões.
- Logs e observabilidade.

### Evidência esperada

Documento `docs/02-requisitos.md`.

---

## S2-02 — Identificar componentes da solução

**Descrição:**

Identificar os principais componentes técnicos necessários para sustentar as operações da LudCommerce.

**Responsável:** Lucas Eugenio

**Revisão técnica:** Kemilly da Silva

**Prioridade:** Alta

### Critérios de aceite

- [ ] Aplicação identificada.
- [ ] API identificada.
- [ ] Banco de dados identificado.
- [ ] Armazenamento de arquivos identificado.
- [ ] Serviços externos identificados.
- [ ] Serviço de pagamento identificado.
- [ ] Serviços de entrega identificados.
- [ ] Sistema de logs e monitoramento considerado.

### Conexão com Sistemas Operacionais

- Processos.
- Serviços.
- Filesystem.
- Entrada e saída.
- Rede.
- Armazenamento.

### Evidência esperada

Documentação da arquitetura e diagrama de componentes.

---

## S2-03 — Definir arquitetura técnica inicial

**Descrição:**

Definir uma arquitetura técnica inicial para a LudCommerce, estabelecendo como os principais componentes se comunicam e onde serão executados.

**Responsável:** Lucas Eugenio

**Revisão técnica:** Kemilly da Silva

**Prioridade:** Alta

### Critérios de aceite

- [ ] Fronteira da solução definida.
- [ ] Componentes internos identificados.
- [ ] Sistemas externos identificados.
- [ ] Principais fluxos de comunicação definidos.
- [ ] Banco de dados identificado.
- [ ] Storage identificado.
- [ ] Logs e monitoramento considerados.
- [ ] Relação entre arquitetura e Sistemas Operacionais documentada.

### Conexão com Sistemas Operacionais

- Processos e serviços.
- Armazenamento.
- Filesystem.
- Rede.
- I/O.
- Observabilidade.
- Disponibilidade.

### Evidência esperada

- `docs/03-arquitetura.md`
- `diagrams/contexto.mmd`
- `diagrams/containers.mmd`

---

## S2-04 — Mapear processos e serviços

**Descrição:**

Identificar os principais processos e serviços envolvidos no funcionamento da LudCommerce e suas responsabilidades.

**Responsável:** Lucas Eugenio

**Prioridade:** Alta

### Critérios de aceite

- [ ] Processos relacionados ao atendimento das requisições identificados.
- [ ] Processamento de pedidos identificado.
- [ ] Processamento de pagamentos identificado.
- [ ] Atualização de estoque identificada.
- [ ] Comunicação com serviços externos identificada.
- [ ] Serviços de logs e monitoramento considerados.
- [ ] Dependências entre processos e serviços documentadas.

### Conexão com Sistemas Operacionais

- Processos.
- Serviços.
- Concorrência.
- Comunicação entre processos.
- Gerenciamento de recursos.

### Evidência esperada

Seção de processos e serviços no documento de arquitetura.

---

## S2-05 — Mapear riscos operacionais

**Descrição:**

Identificar os principais riscos operacionais da arquitetura da LudCommerce e seus impactos para o negócio.

**Responsável:** Lucas Eugenio

**Prioridade:** Alta

### Critérios de aceite

- [ ] Riscos relacionados à concorrência identificados.
- [ ] Riscos de indisponibilidade identificados.
- [ ] Riscos relacionados a memória e desempenho identificados.
- [ ] Riscos relacionados ao armazenamento identificados.
- [ ] Riscos relacionados a serviços externos identificados.
- [ ] Riscos relacionados à perda de dados identificados.
- [ ] Cada risco possui impacto de negócio.
- [ ] Cada risco possui relação com um conceito de Sistemas Operacionais.

### Evidência esperada

Matriz de riscos em `docs/03-arquitetura.md` ou documentação específica.

---

## S2-06 — Criar diagrama de contexto

**Descrição:**

Representar visualmente os atores, sistemas externos e a fronteira da solução LudCommerce.

**Responsável:** Lucas Eugenio

**Revisão técnica:** Kemilly da Silva

**Prioridade:** Alta

### Critérios de aceite

- [ ] Clientes representados.
- [ ] Administrador representado.
- [ ] Equipe operacional representada.
- [ ] Fornecedor representado.
- [ ] Serviço de pagamento representado.
- [ ] Transportadora/Correios representados.
- [ ] LudCommerce delimitada como sistema principal.
- [ ] Relações entre os elementos representadas.

### Evidência esperada

`diagrams/contexto.mmd`

---

## S2-07 — Criar diagrama inicial de containers/deployment

**Descrição:**

Representar os principais componentes técnicos da solução e seus relacionamentos.

**Responsável:** Lucas Eugenio

**Revisão técnica:** Kemilly da Silva

**Prioridade:** Alta

### Critérios de aceite

- [ ] Aplicação representada.
- [ ] API representada.
- [ ] Banco de dados representado.
- [ ] Storage representado.
- [ ] Serviços externos representados.
- [ ] Logs/monitoramento considerados.
- [ ] Fluxos de comunicação representados.
- [ ] Relação com o ambiente operacional identificada.

### Evidência esperada

`diagrams/containers.mmd`

---

## S2-08 — Produzir evidências da Sprint

**Descrição:**

Organizar as evidências produzidas durante a Sprint 2 e relacioná-las às decisões do projeto.

**Responsável:** Lucas Eugenio

**Prioridade:** Média

### Critérios de aceite

- [ ] Evidências organizadas na pasta da Sprint.
- [ ] Evidências possuem identificação.
- [ ] Evidências possuem relação com uma tarefa ou decisão.
- [ ] Experimentos relevantes de Sistemas Operacionais são registrados.
- [ ] Evidências não possuem informações desnecessárias ou sensíveis.

### Evidência esperada

Diretório `evidencias/sprint-02/`.

---

## S2-09 — Identificar processos críticos

**Descrição:**

Identificar os processos essenciais para o funcionamento da LudCommerce e avaliar suas dependências e impactos em caso de falha.

**Responsável:** Lucas Eugenio

**Prioridade:** Alta

### Critérios de aceite

- [X] Processo da aplicação identificado como crítico.
- [X] Banco de dados identificado como serviço essencial.
- [X] Controle de estoque identificado como processo crítico.
- [X] Comunicação com pagamento identificada como dependência crítica.
- [X] Impactos da falha dos processos documentados.

### Evidência esperada

`docs/04-processos.md` — seção 4.

---

## S2-10 — Definir estratégia de Health Checks

**Descrição:**

Definir mecanismos para verificar a disponibilidade e a condição operacional dos principais serviços da LudCommerce.

**Responsável:** Lucas Eugenio

**Prioridade:** Alta

### Critérios de aceite

- [X] Health checks da aplicação considerados.
- [X] Verificação do banco de dados considerada.
- [X] Verificação de dependências externas considerada.
- [X] Condições de serviço saudável e não saudável documentadas.
- [X] Relação entre monitoramento e disponibilidade explicada.

### Evidência esperada

`docs/04-processos.md` — seção 5.

---

## S2-11 — Definir política de reinicialização e recuperação

**Descrição:**

Definir como os serviços deverão reagir a falhas e quais estratégias poderão ser utilizadas para sua recuperação.

**Responsável:** Lucas Eugenio

**Prioridade:** Alta

### Critérios de aceite

- [X] Política de reinicialização documentada.
- [X] Comportamento esperado após falhas definido.
- [X] Dependências entre serviços consideradas durante a recuperação.
- [X] Riscos de reinicializações repetidas considerados.
- [X] Relação com disponibilidade documentada.

### Evidência esperada

`docs/04-processos.md` — seção 6.

---

## S2-12 — Classificar workloads e consumo de recursos

**Descrição:**

Classificar os principais tipos de carga de trabalho da LudCommerce conforme o consumo de recursos computacionais.

**Responsável:** Lucas Eugenio

**Prioridade:** Média

### Critérios de aceite

- [X] Workloads dependentes de CPU identificados.
- [X] Workloads relacionados à memória identificados.
- [X] Workloads dependentes de I/O identificados.
- [X] Workloads relacionados à rede identificados.
- [X] Relação entre consumo de recursos e desempenho documentada.

### Evidência esperada

`docs/04-processos.md` — seção 7.

---

## S2-13 — Definir requisitos mínimos de logs

**Descrição:**

Identificar os eventos operacionais que precisam ser registrados para permitir o acompanhamento e a investigação de falhas.

**Responsável:** Lucas Eugenio

**Prioridade:** Média

### Critérios de aceite

- [X] Eventos de inicialização e encerramento considerados.
- [X] Erros operacionais considerados.
- [X] Falhas de comunicação com serviços externos consideradas.
- [X] Eventos relacionados a pedidos considerados.
- [X] Informações mínimas de rastreabilidade definidas.
- [X] Relação entre logs e observabilidade documentada.

### Evidência esperada

`docs/04-processos.md` — seção 8.

---

# Definition of Done

Uma tarefa da Sprint será considerada concluída quando:

- [ ] O trabalho previsto estiver realizado.
- [ ] O resultado estiver documentado.
- [ ] Os critérios de aceite forem atendidos.
- [ ] A relação com Sistemas Operacionais estiver explicitada quando aplicável.
- [ ] A evidência correspondente estiver registrada quando necessária.
- [ ] O arquivo estiver versionado no Git.
- [ ] O trabalho estiver pronto para revisão.

---

# Resultado esperado da Sprint 2

Ao final da Sprint 2, a LudCommerce deverá possuir uma definição inicial de sua arquitetura técnica, seus principais componentes, processos e serviços, além dos principais riscos operacionais que serão aprofundados nas Sprints seguintes.

A arquitetura deverá servir como base para os estudos posteriores de processos, escalonamento, observabilidade, memória, desempenho, armazenamento, filesystem, permissões, logs, backup, recuperação, E/S, rede, virtualização, containers e hardening.
