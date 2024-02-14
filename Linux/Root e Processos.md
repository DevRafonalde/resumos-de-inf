# PODERES DO ROOT

## POSSE DE ARQUIVOS E PROCESSOS
- Todo arquivo tem um usuário e um grupo proprietário
- O proprietário do arquivo pode modificar as permissões do arquivo
- Os grupos são definidos no arquivo "/etc/group"
- Ambas as propriedades de um arquivo podem ser verificadas através do comando "ls -l *nome do arquivo*"

- O Linux controla os proprietários e grupos como NÚMEROS, e não como nomes na forma de texto
- Os UIDs são associados a nomes de usuários no arquivo "/etc/passwd"
- Os GIDs são associados a nomes de grupos no arquivo "/etc/group"

## O SUPERUSUÁRIO (root)
- Não deixa log
- Usar o comando "su" para acessar, ele solicita a senha do root e inicializa o shell root
- O comando "sudo" tem a capacidade de dar a alguém o acesso de admin, sem que essa pessoa tenha livre acesso ao sistema
- O programa sudo consulta o arquivo "/etc/sudoers", que lista as pessoas que podem usar o sudo e quais comandos podem executar.
- Para modificar o arquivo "/etc/sudoers", utilizamos o comando "visudo"

## PSEUDO-USUÁRIOS
- Root
- Bin: Proprietário herdado de comandos de sistema
- Daemon: Proprietário de software de sistema não-privilegiado
- Nobody: O usuário NFS genérico

## CONTROLE DE PROCESSOS
- Processo é uma abstração utilizada pelo Linux para representar um programa em execução

### COMPONENTES DE UM PROCESSO
- Espaço de endereços
  - Conjunto de páginas de memória que o kernel marcou para ser empregado pelo processo.

- Estruturas de dados internas do kernel
  - Registram vários tipos de informações sobre cada processo

- PID
  - Número de identificação de processo
  - Quando um processo é clonado, o original é chamado de pai e a cópia de filho
  - O atributo PPID de um processo é o PID do pai que foi clonado

- FSUID
  - Controla a determinação de permissões do sistema de arquivos

- UID e EUID
  - Identificadores de usuário real (fins de contabilidade) e efetivo (fins de acesso/permissão)

- GID e EGID
  - Identificadores de grupo real e efetivo

- NICENESS
  - "Gentileza"
  - Assim chamado porque ele informa o quão gentil você planeja ser com os demais usuários do sistema (tempo de CPU/PRIORIDADE)

- FORK
  - Sistema que cria uma cópia do processo original que é, em grande parte, idêntica ao pai

## NICE E RENICE
- Um valor nice alto significa baixa prioridade, pois ele é muito gentil, para o seu processo.
- Um valor nice baixo ou negativo significa alta prioridade, pois ele é pouco gentil.
- O valor nice pode variar de -20 até +19
- O valor nice de um processo pode ser configurado no momento da criação pelo comando "nice" e/ou ser ajustado posteriormente com o comando "renice"
  - `# nice -n 5 ~/bin/longtask` // Configura a prioridade para 5
  - `# renice -5 8829` // Ajusta o valor nice do PID 8829 para -5
  - `# renice 5 -u rafael` // Ajusta o valor nice dos processos do usuário rafael como 5

## PS: MONITORANDO PROCESSOS
- `ps` é o principal comando do admin de sistemas para monitoramento de processos, ele exibe:
  - PID
  - UID
  - Prioridade
  - Terminal de controle de processos
  - Informação de memória consumida
  - Estado atual do processo (zumbis aparecem como <defunct>)

- Você pode obter uma visão geral dos processos em execução no sistema via `ps -aux`
  - `-a`: Mostra os processos criados por você e de outros usuários do sistema
  - `-u`: Mostra o nome do usuário que iniciou o processo e quando foi iniciado
  - `-x`: Mostra processos que não são controlados pelo terminal

## TOP: MONITORANDO MELHOR OS PROCESSOS
- Fornece um resumo regularmente atualizado dos processos ativos e o uso de recursos
- Por padrão, é atualizado a cada 10 segundos e os processos mais ativos aparecem no alto
  - `# top`

## /PROC
- O "ps" e o "top" leem suas informações sobre o status de um processo a partir do diretório "/proc", um pseudo-sistema de arquivo em que o kernel expõe uma variedade de informações interessantes sobre o estado do sistema
- Apesar do nome "/proc", as informações não estão limitadas às informações sobre processos, todas as informações sobre o status e as estatísticas geradas pelo kernel são representadas aqui
