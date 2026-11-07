# 06 - Entrada e Saída, Rede e Integrações

## 1. Objetivo

Documentar os aspectos de entrada e saída (E/S), armazenamento,
memória, comunicação de rede, dispositivos e integrações externas
relacionados à arquitetura da LudCommerce.

Os testes foram realizados no ambiente Linux disponibilizado pelo
GitHub Codespaces, utilizando comandos de diagnóstico do sistema
operacional e requisições HTTP.

## 2. Armazenamento e memória

Foram utilizados os comandos:

- `lsblk`: identificação dos dispositivos de armazenamento.
- `df -h`: verificação do espaço utilizado e disponível.
- `free -h`: consulta da utilização de memória RAM.

### Resultados observados

- Armazenamento: partição de aproximadamente 30 GB, além de
  outros volumes disponibilizados pelo ambiente.
- Sistema de arquivos principal: aproximadamente 32 GB,
  com 14 GB utilizados e 17 GB disponíveis.
- Memória RAM: 7,8 GiB no total.
- Memória disponível: aproximadamente 4,7 GiB.
- Swap: não configurada no ambiente analisado.

Essas informações permitem observar os recursos disponíveis
para a execução dos processos e serviços da aplicação.

## 3. Comunicação de rede

Foram utilizados os comandos:

- `ip addr`: identificação das interfaces de rede.
- `ip route`: consulta das rotas de comunicação.
- `ss -tuln`: identificação de portas e serviços em escuta.
- `getent hosts github.com`: teste de resolução DNS.

### Resultados observados

- Interface de rede `eth0` ativa.
- Endereço IP identificado: `10.0.2.204`.
- Gateway padrão: `10.0.0.1`.
- Resolução DNS de `github.com` realizada com sucesso.
- Serviços locais identificados por meio do comando `ss -tuln`.

A comunicação de rede é necessária para permitir que a
LudCommerce se comunique com usuários, serviços externos
e componentes de infraestrutura.

## 4. Testes de conectividade HTTP

### 4.1 Comunicação bem-sucedida

Foi realizada uma requisição HTTP ao GitHub:

`curl -I --max-time 10 https://github.com`

Resultado observado: `HTTP/2 200`.

O resultado indica que o servidor respondeu com sucesso
à requisição realizada.

### 4.2 Simulação de indisponibilidade de serviço

Foi realizada uma requisição ao endpoint de teste do HTTPBin:

`curl -i --max-time 10 https://httpbin.org/status/503`

Resultado observado: `HTTP/2 503 - Service Unavailable`.

O servidor respondeu à requisição, mas informou que o serviço
estava indisponível para atendimento.

Na LudCommerce, uma situação semelhante poderia ocorrer
em uma integração externa, como um gateway de pagamento.
A aplicação deverá prever o tratamento de respostas de erro
e indisponibilidade, sem considerar uma operação como concluída
sem a confirmação do serviço responsável.

## 5. Simulação de falha de comunicação

Foi executado o comando:

`ping -c 4 192.0.2.1`

Resultado observado:

- 4 pacotes transmitidos.
- 0 pacotes recebidos.
- 100% de perda de pacotes.

O endereço utilizado pertence a uma faixa reservada para
documentação e exemplos. O teste demonstrou uma tentativa
de comunicação sem recebimento de respostas.

Esse cenário representa um exemplo de falha de conectividade
que deve ser considerado no planejamento da infraestrutura.

## 6. Dispositivos e interfaces do sistema

Foi utilizado o comando:

`ls -l /dev`

A listagem apresentou dispositivos e interfaces virtuais
disponibilizados pelo ambiente Linux, incluindo dispositivos
de armazenamento e interfaces do sistema.

Também foi realizada uma tentativa de consulta ao buffer
de mensagens do kernel por meio do comando `dmesg`.

Resultado: acesso negado por restrição de permissões
do ambiente Codespaces.

Essa limitação demonstra que o ambiente de desenvolvimento
em contêiner não disponibiliza acesso irrestrito a todos
os recursos do sistema operacional hospedeiro.

## 7. Relação com a arquitetura da LudCommerce

Os testes permitem identificar aspectos importantes para
o funcionamento da loja virtual:

- E/S e armazenamento: leitura e gravação de dados,
  arquivos e informações persistidas.
- Memória: recursos utilizados pelos processos e serviços.
- Rede: comunicação entre os componentes da aplicação.
- DNS: resolução dos endereços dos serviços externos.
- Integrações: comunicação com serviços de terceiros,
  como sistemas de pagamento.
- Tratamento de falhas: necessidade de prever indisponibilidade
  de serviços e perda de comunicação.

## 8. Pontos de atenção

Com base nos testes realizados, foram identificados os
seguintes pontos que devem ser considerados na arquitetura:

1. Monitorar a utilização de armazenamento e memória.
2. Garantir comunicação entre os componentes da aplicação.
3. Prever tratamento de erros em integrações externas.
4. Considerar indisponibilidade temporária de serviços.
5. Evitar considerar operações externas concluídas sem
   confirmação adequada.
6. Considerar as restrições de acesso existentes em ambientes
   virtualizados e conteinerizados.

## 9. Conclusão

Os testes realizados no ambiente Linux permitiram observar
recursos de armazenamento, memória, dispositivos e rede,
além de verificar respostas de serviços externos.

Os resultados demonstraram tanto situações de comunicação
bem-sucedida quanto cenários de indisponibilidade e falha.

Essas evidências contribuem para o planejamento da arquitetura
operacional da LudCommerce, especialmente nos aspectos de
entrada e saída, comunicação, integrações e tratamento de falhas.

**Observação:** os testes foram realizados no ambiente de
desenvolvimento GitHub Codespaces. Eles não representam,
por si só, testes de desempenho ou disponibilidade da aplicação
LudCommerce em produção.
