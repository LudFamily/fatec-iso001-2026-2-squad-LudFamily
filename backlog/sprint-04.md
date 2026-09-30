# Sprint 4 — Memória, Limites, Performance e Gargalos

**Período:** 26/09/2026 a 10/10/2026

## Objetivo da Sprint

A Sprint 4 tem como objetivo aprofundar a relação entre a memória e o
desempenho da LudCommerce, analisando consumo de memória, limites,
performance e possíveis gargalos de recursos.

Durante a sprint serão realizados experimentos práticos em ambiente Linux
para observar o consumo de memória por processos, a redução da memória
disponível e a competição por CPU.

Os resultados dos experimentos serão utilizados como evidências e
relacionados à arquitetura e aos riscos operacionais da LudCommerce.

---

## S4-01 — Consumo de memória por processos

### Descrição

Analisar como processos em execução utilizam memória RAM e como esse
consumo pode ser observado por meio das ferramentas do sistema
operacional.

Foi utilizado um processo Python para reservar aproximadamente 500 MiB
de memória e observar a alteração no consumo de RAM.

### Experimento realizado

Estado inicial:

- Memória total: 3.8 GiB
- Memória usada: 1.1 GiB
- Memória disponível: 2.7 GiB
- Swap utilizada: 0 B

Comando utilizado:

```bash
python3 -c 'a = bytearray(500 * 1024 * 1024); input("Pressione Enter para liberar a memória...")'