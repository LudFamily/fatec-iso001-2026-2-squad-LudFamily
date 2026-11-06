# Sprint 3 — Processos, Escalonamento e Observabilidade

**Período:** 12/09/2026 a 26/09/2026

## Objetivo da Sprint

A Sprint 3 tem como objetivo aprofundar a relação entre os processos da LudCommerce e os recursos do sistema operacional, analisando processos, escalonamento e observabilidade.

Durante a sprint serão realizados experimentos práticos em ambiente Linux para observar o comportamento dos processos, a utilização da CPU, a prioridade de execução e métricas básicas do sistema.

Os resultados dos experimentos serão utilizados como evidências e relacionados à arquitetura e à operação da LudCommerce.

---

## S3-01 — Processos e estados

### Descrição

Analisar o conceito de processo no contexto da LudCommerce e sua relação com os recursos administrados pelo sistema operacional.

Um processo representa um programa em execução. Cada processo possui um identificador único (PID) e pode apresentar diferentes estados durante sua execução, como execução, espera e encerramento.

Na LudCommerce, os serviços da aplicação dependem do gerenciamento desses processos pelo sistema operacional. A execução concorrente de diferentes atividades pode gerar competição pelos recursos disponíveis, principalmente CPU e memória.

### Conceitos de Sistemas Operacionais relacionados

- Processo;
- PID (Process ID);
- Estados de processo;
- Concorrência;
- CPU;
- Memória;
- PCB (Process Control Block).

### Critérios de aceite

- [ ] Documentar o conceito de processo.
- [ ] Explicar a função do PID.
- [ ] Relacionar processos aos recursos de CPU e memória.
- [ ] Relacionar processos concorrentes ao contexto da LudCommerce.
- [ ] Registrar evidência prática utilizando comandos do Linux.

### Evidências

- Consulta de processos utilizando `ps`.
- Observação dos estados e consumo de recursos dos processos.
- Evidência complementar em `evidencias/sprint-03/01-observabilidade.txt`.
- Experimentos realizados no ambiente Linux/WSL.

---

## S3-02 — Escalonamento e prioridade de processos

### Descrição

Realizar experimentos práticos no Linux para observar a competição entre processos pelo uso da CPU e analisar a influência da prioridade relativa dos processos.

Foram utilizados processos `yes` para gerar carga de CPU e os comandos `nice` e `renice` para alterar o valor de prioridade relativa dos processos.

### Conceitos de Sistemas Operacionais relacionados

- Escalonamento de processos;
- Prioridade;
- Concorrência;
- Preempção;
- Tempo de CPU;
- Valor de `nice`;
- Comandos `nice` e `renice`.

### Experimentos realizados

Foram executados processos concorrentes utilizando:

```bash
yes > /dev/null &
nice -n 10 yes > /dev/null &
```

A inspeção dos processos foi realizada com:

```bash
ps -eo pid,stat,ni,%cpu,%mem,comm --sort=-%cpu
```

Também foi utilizado o comando `top` para acompanhar os processos em execução.

Para alterar a prioridade de um processo existente, foi executado:

```bash
renice 10 -p 3121
```

Os processos de teste foram encerrados com:

```bash
pkill yes
```

### Critérios de aceite

- [ ] Documentar o funcionamento do escalonador.
- [ ] Explicar a relação entre prioridade e utilização da CPU.
- [x] Registrar a execução de processos concorrentes com `yes`.
- [x] Registrar a utilização de `nice` para iniciar processo com prioridade relativa menor.
- [x] Registrar a utilização de `renice` para alterar a prioridade de processo existente.
- [x] Registrar comandos de inspeção dos processos.
- [ ] Preservar resultados numéricos da comparação entre processos com prioridades diferentes.

### Evidências

- `evidencias/sprint-03/02-escalonamento.txt`.
- Histórico do terminal com comandos de execução e inspeção.
- Documentação complementar em `docs/03-arquitetura.md`, seção 10.2.1.

**Observação:** o histórico confirma a execução dos comandos, mas não preserva todos os resultados numéricos apresentados pelo terminal. Por isso, não são atribuídos percentuais específicos de CPU aos processos.

---

## S3-03 — Observabilidade e monitoramento de recursos

### Descrição

Observar o comportamento do ambiente Linux por meio de métricas básicas de utilização de recursos e informações sobre processos.

A observabilidade permite acompanhar condições operacionais do ambiente, identificar possíveis gargalos e apoiar a análise de desempenho dos serviços da LudCommerce.

### Conceitos de Sistemas Operacionais relacionados

- Monitoramento;
- CPU;
- Memória RAM;
- Swap;
- Processos;
- Load average;
- Utilização de recursos;
- Logs e observabilidade.

### Experimento realizado

Foram utilizados comandos Linux para coletar informações do ambiente:

```bash
uptime
free -h
ps -eo pid,stat,ni,%cpu,%mem,comm --sort=-%cpu
top -b -n 1
```

Os resultados foram registrados em arquivo de evidência.

### Critérios de aceite

- [x] Registrar informações de carga média do sistema com `uptime`.
- [x] Registrar utilização de memória RAM e swap com `free -h`.
- [x] Registrar informações de processos com `ps`.
- [x] Registrar uma coleta de monitoramento com `top`.
- [x] Documentar os resultados observados.
- [ ] Relacionar os indicadores coletados a possíveis situações de gargalo na LudCommerce.

### Evidências

- `evidencias/sprint-03/01-observabilidade.txt`.
- Documentação complementar na arquitetura da LudCommerce.

---

## Definition of Done — Sprint 3

A Sprint 3 será considerada concluída quando:

- [ ] Os conceitos de processos e estados estiverem documentados.
- [ ] O escalonamento e a prioridade de processos estiverem documentados.
- [ ] Os experimentos de concorrência e prioridade estiverem registrados.
- [ ] As métricas de CPU, memória e processos estiverem documentadas.
- [ ] As evidências práticas estiverem versionadas no repositório.
- [ ] Os resultados estiverem relacionados ao funcionamento da LudCommerce.
- [ ] A documentação estiver revisada e consistente com as evidências.

## Observações gerais

Os experimentos foram realizados em ambiente Linux disponibilizado pelo Codespaces. Os resultados representam as condições desse ambiente no momento das coletas e não devem ser interpretados como medições de uma infraestrutura de produção da LudCommerce.