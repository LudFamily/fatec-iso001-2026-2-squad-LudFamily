# Sprint 3 — Processos, Escalonamento e Observabilidade

**Período:** 12/09/2026 a 26/09/2026

## Objetivo da Sprint

A Sprint 3 tem como objetivo aprofundar a relação entre os processos da
LudCommerce e os recursos do sistema operacional, analisando processos,
escalonamento e observabilidade.

Durante a sprint serão realizados experimentos práticos em ambiente Linux
para observar o comportamento dos processos, a utilização da CPU, a
prioridade de execução e métricas básicas do sistema.

Os resultados dos experimentos serão utilizados como evidências e
relacionados à arquitetura e à operação da LudCommerce.

## S3-01 — Processos e estados

### Descrição

Analisar o conceito de processo no contexto da LudCommerce e sua relação
com os recursos administrados pelo sistema operacional.

Um processo representa um programa em execução. Cada processo possui um
identificador único (PID) e pode apresentar diferentes estados durante
sua execução, como execução, espera e encerramento.

Na LudCommerce, os serviços da aplicação dependem do gerenciamento desses
processos pelo sistema operacional. A execução concorrente de diferentes
atividades pode gerar competição pelos recursos disponíveis, principalmente
CPU e memória.

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
- Experimentos realizados no ambiente Linux/WSL.

## S3-02 — Escalonamento e prioridade de processos

### Descrição

Realizar experimentos práticos no Linux para observar a competição entre
processos pelo uso da CPU e analisar a influência da prioridade relativa
dos processos.

Foram utilizados processos `yes` para gerar carga de CPU e os comandos
`nice` e `renice` para alterar o valor de prioridade relativa dos
processos.

### Experimento realizado

Foram executados processos concorrentes utilizando:

```bash
yes > /dev/null &