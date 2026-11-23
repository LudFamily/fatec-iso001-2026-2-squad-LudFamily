
# Evidência Prática — Deadlocks

**Grupo:** LudFamily  
**Projeto:** LudCommerce  
**Disciplina:** ISO001 — Sistemas Operacionais  
**Instituição:** FATEC Mauá

## 1. Objetivo

Demonstrar, por meio de simulações em Python, o funcionamento
dos mecanismos de prevenção, evitação, detecção e recuperação
de deadlocks em sistemas operacionais.

## 2. Contextualização

A simulação utiliza um cenário fictício da LudCommerce,
uma loja de hardware e periféricos.

São representados processos que disputam recursos
compartilhados, como conexões com banco de dados e acesso
ao estoque.

## 3. Conteúdo desenvolvido

O notebook apresenta:

- Cenário de disputa por recursos.
- Grafo de alocação e espera.
- Condições necessárias para ocorrência de deadlock.
- Matrizes Available, Allocation, Max e Need.
- Verificação de estados seguros e inseguros.
- Simulação de solicitação aprovada e negada.
- Detecção de espera circular.
- Recuperação por interrupção de processo e liberação de recursos.

## 4. Tecnologias utilizadas

- Python
- Google Colab
- NumPy
- NetworkX
- Matplotlib

## 5. Como executar

1. Acesse o Google Colab.
2. Abra o arquivo `deadlock_ludcommerce.ipynb`.
3. Execute as células na ordem apresentada.
4. Observe os resultados das simulações.

## 6. Observações

Os dados e cenários utilizados são fictícios e possuem
finalidade didática. A simulação não representa uma
infraestrutura de produção da LudCommerce.

A detecção por ciclo considera recursos com instância única.
O algoritmo do banqueiro é utilizado para demonstrar
a evitação de deadlocks.
