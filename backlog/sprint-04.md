# Sprint 4 — Memória, Limites, Performance e Gargalos

**Período:** 26/09/2026 a 10/10/2026

## Objetivo da Sprint

A Sprint 4 tem como objetivo aprofundar a relação entre a memória e o desempenho da LudCommerce, analisando consumo de memória, limites, performance e possíveis gargalos de recursos.

Durante a sprint serão realizados experimentos práticos em ambiente Linux para observar o consumo de memória por processos, a redução da memória disponível e a competição por CPU.

Os resultados dos experimentos serão utilizados como evidências e relacionados à arquitetura e aos riscos operacionais da LudCommerce.

---

## S4-01 — Consumo de memória por processos

### Descrição

Analisar como processos em execução utilizam memória RAM e como esse consumo pode ser observado por meio das ferramentas do sistema operacional.

Foi utilizado um processo Python para reservar aproximadamente 500 MiB de memória e observar a alteração no consumo de RAM.

### Experimento realizado

Foi executado um processo Python para alocar aproximadamente 500 MiB:

```bash
python3 -c 'a = bytearray(500 * 1024 * 1024); input("Pressione Enter para liberar a memória...")'
```

O processo foi identificado por meio do PID e monitorado utilizando informações de consumo de memória, incluindo RSS e `%MEM`.

### Resultados observados

- Memória utilizada: aproximadamente 1,1 GiB para 1,6 GiB.
- Memória disponível: aproximadamente 2,7 GiB para 2,2 GiB.
- RSS do processo: 521.776 KiB.
- Swap utilizada: 0 B.
- Após o encerramento do processo, a memória utilizada retornou para aproximadamente 1,1 GiB.

### Critérios de aceite

- [x] Documentar o consumo de memória por processos.
- [x] Registrar a alocação controlada de aproximadamente 500 MiB.
- [x] Identificar o processo por meio do PID.
- [x] Registrar o consumo de memória utilizando RSS e `%MEM`.
- [x] Observar a liberação de memória após o encerramento do processo.

### Evidências

- `evidencias/sprint-04/01-memoria.txt`.
- Documentação complementar em `docs/03-arquitetura.md`, seção 10.3.

---

## S4-02 — Limites e pressão de memória

### Descrição

Analisar o comportamento do sistema operacional diante de um aumento significativo do consumo de memória por um processo e observar a redução da memória disponível.

O experimento foi realizado por meio de uma alocação de aproximadamente 2 GiB utilizando Python.

### Experimento realizado

```bash
python3 -c 'a = bytearray(2 * 1024 * 1024 * 1024); input("Pressione Enter para liberar...")'
```

### Resultados observados

- Memória utilizada: aproximadamente 1,1 GiB para 3,2 GiB.
- Memória disponível: aproximadamente 2,7 GiB para 642 MiB.
- RSS do processo: 2.106.864 KiB.
- Swap utilizada: permaneceu em 0 B.
- Após o encerramento, a memória disponível retornou para aproximadamente 2,6 GiB.

### Critérios de aceite

- [x] Registrar o consumo elevado de memória por processo.
- [x] Observar a redução da memória disponível.
- [x] Identificar o processo responsável pelo consumo.
- [x] Registrar o comportamento da swap durante o experimento.
- [x] Observar a recuperação da memória após o encerramento do processo.
- [x] Relacionar a pressão de memória aos possíveis riscos operacionais da LudCommerce.

### Evidências

- `evidencias/sprint-04/01-memoria.txt`.
- Documentação complementar em `docs/03-arquitetura.md`, seção 10.3.1.

---

## S4-03 — Performance e competição por CPU

### Descrição

Observar a competição entre processos concorrentes pelo uso da CPU e analisar a relação entre utilização do processador e consumo de memória.

### Experimento realizado

Foram executados dois processos simultaneamente para gerar carga de CPU:

```bash
yes > /dev/null &
yes > /dev/null &
```

A observação foi realizada utilizando:

```bash
top -b -n 1 | head -20
```

### Resultados observados

- Dois processos `yes` em execução.
- Cada processo apresentou aproximadamente 100% de utilização individual da CPU.
- O ambiente possuía quatro CPUs disponíveis.
- A CPU apresentou 41,4% de tempo ocioso.
- A memória permaneceu com aproximadamente 2,7 GiB disponíveis.
- A swap permaneceu sem utilização.

### Critérios de aceite

- [x] Registrar a execução de processos concorrentes.
- [x] Observar o consumo individual de CPU.
- [x] Registrar a utilização geral da CPU.
- [x] Comparar o consumo de CPU com a disponibilidade de memória.
- [x] Relacionar a competição por CPU aos possíveis gargalos de desempenho da LudCommerce.

### Evidências

- `evidencias/sprint-04/01-memoria.txt`.
- Documentação complementar em `docs/03-arquitetura.md`, seções 10.2 e 10.3.

---

## Definition of Done — Sprint 4

A Sprint 4 será considerada concluída quando:

- [x] O consumo de memória por processos estiver documentado.
- [x] Os experimentos de alocação de memória estiverem registrados.
- [x] A pressão de memória estiver documentada.
- [x] O comportamento da swap estiver registrado.
- [x] A competição por CPU estiver documentada.
- [x] Os resultados estiverem relacionados aos riscos operacionais da LudCommerce.
- [x] As evidências estiverem organizadas no repositório.
- [ ] A documentação e o backlog estiverem revisados e versionados no Git.

## Observações gerais

Os experimentos foram realizados em ambiente Linux disponibilizado pelo Codespaces. Os resultados representam as condições desse ambiente no momento das coletas e não devem ser interpretados como medições de uma infraestrutura de produção da LudCommerce.