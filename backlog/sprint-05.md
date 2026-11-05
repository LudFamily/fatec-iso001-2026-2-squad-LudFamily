# Sprint 5 — Filesystem, Permissões, Logs, Backup e Recuperação

**Período:** 10/10/2026 a 24/10/2026

## Objetivo da Sprint

Aprofundar a relação entre o sistema de arquivos, permissões,
logs, backup e recuperação no contexto da LudCommerce.

A Sprint busca demonstrar como o sistema operacional organiza
e protege os arquivos utilizados pela plataforma, registra
eventos operacionais e permite a recuperação de informações
após falhas ou perda de dados.

Serão realizados experimentos práticos em ambiente Linux,
com evidências relacionadas à arquitetura e aos riscos
operacionais da loja virtual.

---

## S5-01 — Sistema de arquivos (Filesystem)

### Descrição

Analisar como o sistema operacional organiza e disponibiliza
os arquivos e diretórios necessários à operação da LudCommerce.

### Atividades

- Identificar a estrutura de diretórios do projeto.
- Observar o espaço disponível em disco.
- Analisar o tamanho ocupado por arquivos e diretórios.
- Relacionar o armazenamento aos arquivos da aplicação,
  documentos, logs e backups.

### Critérios de aceite

- [x] Documentar a estrutura de diretórios.
- [x] Registrar informações de armazenamento.
- [x] Identificar riscos relacionados à falta de espaço.
- [x] Relacionar o filesystem à arquitetura da LudCommerce.
- [x] Registrar evidências práticas em Linux.

---

## S5-02 — Controle de permissões

### Descrição

Analisar como usuários, grupos e permissões controlam
o acesso aos arquivos e diretórios da LudCommerce.

### Atividades

- Examinar permissões de arquivos e diretórios.
- Realizar testes controlados de leitura e escrita.
- Utilizar comandos de alteração de permissões.
- Relacionar o princípio do menor privilégio à segurança
  dos arquivos da plataforma.

### Critérios de aceite

- [x] Explicar permissões de leitura, escrita e execução.
- [x] Demonstrar alterações de permissões.
- [ ] Registrar testes de acesso permitido e negado.
- [x] Relacionar os resultados à segurança da LudCommerce.
- [x] Registrar evidências práticas em Linux.

---

## S5-03 — Logs e registros operacionais

### Descrição

Analisar a importância dos logs para registrar eventos,
identificar falhas e auxiliar na investigação de incidentes
na operação da LudCommerce.

### Atividades

- Identificar a finalidade dos logs.
- Criar ou analisar registros de eventos simulados.
- Examinar registros utilizando ferramentas Linux.
- Relacionar logs à observabilidade e à investigação
  de problemas operacionais.

### Critérios de aceite

- [x] Explicar a função dos logs.
- [x] Demonstrar a criação ou leitura de registros.
- [x] Identificar informações relevantes em um log.
- [x] Relacionar logs aos riscos operacionais da loja.
- [x] Registrar evidências práticas em Linux.

---

## S5-04 — Backup

### Descrição

Demonstrar a criação de cópias de segurança dos arquivos
importantes para a operação da LudCommerce.

### Atividades

- Identificar arquivos que precisam de proteção.
- Criar um conjunto de arquivos representativos da operação.
- Realizar backup utilizando ferramentas Linux.
- Verificar a integridade do arquivo de backup.

### Critérios de aceite

- [x] Identificar os arquivos que devem ser protegidos.
- [x] Demonstrar a criação de um backup.
- [x] Verificar a integridade da cópia.
- [x] Relacionar a estratégia aos riscos de perda de dados.
- [x] Registrar evidências práticas em Linux.

---

## S5-05 — Recuperação de arquivos

### Descrição

Demonstrar a recuperação de arquivos a partir de uma
cópia de segurança, relacionando o procedimento à
continuidade operacional da LudCommerce.

### Atividades

- Simular a indisponibilidade ou perda de arquivos.
- Restaurar os arquivos a partir do backup.
- Comparar os arquivos restaurados com os originais.
- Registrar o resultado da recuperação.

### Critérios de aceite

- [x] Demonstrar a restauração dos arquivos.
- [x] Verificar a integridade dos arquivos recuperados.
- [x] Documentar o procedimento de recuperação.
- [x] Relacionar a recuperação à disponibilidade da loja.
- [x] Registrar evidências práticas em Linux.

---

## Entregas da Sprint

- Backlog da Sprint 5.
- Evidências dos experimentos Linux.
- Documentação dos resultados.
- Relação dos experimentos com a arquitetura da LudCommerce.
- Registro de riscos e decisões técnicas relacionados
  aos temas trabalhados.

## Relação com Sistemas Operacionais

- Sistema de arquivos.
- Gerenciamento de permissões.
- Registro e análise de logs.
- Armazenamento e backup.
- Recuperação de arquivos.
- Segurança e disponibilidade.
