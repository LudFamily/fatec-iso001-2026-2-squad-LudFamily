# Sprint 6 — E/S, Rede, Dispositivos e Integrações

## Período
24/10/2026 a 07/11/2026

## Objetivo da Sprint

Investigar e documentar os aspectos de entrada e saída (E/S),
armazenamento, memória, rede, dispositivos, integrações externas
e possíveis pontos de falha relacionados à arquitetura da
LudCommerce.

## Atividades realizadas

| ID | Atividade | Evidência | Status |
|---|---|---|---|
| S6-01 | Identificar dispositivos e recursos de armazenamento | evidencias/sprint-06/01-diagnostico-sistema.txt | Concluída |
| S6-02 | Verificar utilização de memória RAM | evidencias/sprint-06/01-diagnostico-sistema.txt | Concluída |
| S6-03 | Identificar interfaces, endereços IP e rotas de rede | evidencias/sprint-06/01-diagnostico-sistema.txt | Concluída |
| S6-04 | Verificar resolução DNS | evidencias/sprint-06/01-diagnostico-sistema.txt | Concluída |
| S6-05 | Testar comunicação HTTP com serviço externo | evidencias/sprint-06/01-diagnostico-sistema.txt | Concluída |
| S6-06 | Simular resposta de indisponibilidade HTTP 503 | evidencias/sprint-06/02-integracoes-http.txt | Concluída |
| S6-07 | Simular falha de conectividade de rede | evidencias/sprint-06/03-pontos-de-falha.txt | Concluída |
| S6-08 | Documentar dispositivos e restrições do ambiente | evidencias/sprint-06/01-diagnostico-sistema.txt | Concluída |
| S6-09 | Consolidar análise técnica de E/S, rede e integrações | docs/06-io-rede-integracoes.md | Concluída |

## Resultados

- Diagnóstico de armazenamento e memória do ambiente Linux.
- Identificação de interfaces de rede, endereços IP e rotas.
- Verificação de resolução DNS.
- Teste de comunicação HTTP com resposta 200.
- Simulação de indisponibilidade de serviço com resposta HTTP 503.
- Simulação de falha de comunicação com 100% de perda de pacotes.
- Identificação de dispositivos virtuais e restrições de acesso ao kernel.
- Documentação técnica dos resultados e pontos de atenção para a arquitetura.

## Observações

Os testes foram realizados no ambiente de desenvolvimento
GitHub Codespaces. As simulações demonstram comportamentos
do ambiente e de serviços externos, não constituindo testes
de produção da aplicação LudCommerce.

## Status geral

Atividades de diagnóstico e documentação registradas.
A validação final da Sprint depende da revisão dos artefatos
e dos critérios definidos para a entrega.
