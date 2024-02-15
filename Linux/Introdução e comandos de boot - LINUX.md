# LINUX

## INICIALIZAÇÃO

### BOOTSTRAPPING

- Carregamento e inicialização do kernel
- Detecção e configuração de dispositivos
- Criação de threads do Kernel para processos de sistemas espontâneos
- Intervenção do operador (somente para inicialização manual)
- Execução dos scripts de inicialização do sistema
- Operação multiusuário

### INICIALIZAÇÃO LILO E GRUB

#### LILO

- Rotina Tradicional
- Ofuscada pelo GRUB

#### GRUB

- Permite uma variedade de SOs na mesma máquina
- NÃO deve ser reinstalado no registro de inicialização ou MBR
- É instalado em uma unidade de inicialização executando o comando grub-install

  - `# grub-install '(hd 0, 0)`
    - `hd (0, 0) = /dev/hda1`
    - `dev` = Diretório onde são armazenados os dispositivos existentes no sistema
    - `hd` = Sigla que identifica o tipo do disco rígido (hd=ide, sd=SCSI)
    - `a` = Letra que identifica o disco rígido (a=primeiro, b=segundo, etc...)
    - `1` = Número que identifica o número de partição no disco rígido

*Arquivo de configuração GRUB:* `/boot/grub/grub.conf`

## REINICIALIZANDO E DESLIGANDO

- **Shutdown:**
  - A maneira mais segura e ajuizada de iniciar o processo de parada ou de reinicialização ou retorno ao modo monousuário

- **Halt:**
  - Uma maneira mais simples de desligar o sistema, realiza as tarefas essenciais necessárias para desligar o sistema

- **Reboot:**
  - Reinicialização rápida e suja, idêntica ao halt, porém inicializa a máquina em vez de parar

- **Telinit:**
  - Modifica o nível de execução de init

- **Init:**
  - É o primeiro processo (programa) executado pelo kernel durante a inicialização. Basicamente ele é um processo que cria todos os demais processos.
  - **Nível 0:** Nível no qual o sistema está completamente desligado
  - **Nível 1 ou S:** Representa o modo monousuário
  - **Níveis 2 a 5:** Níveis multiusuário
  - **Nível 6:** Nível de "reinicialização"
  - *O arquivo* `/etc/inittab` *instrui init sobre o que fazer em cada um desses níveis;*
  - *As cópias mestras dos scripts de inicialização residem no diretório* `/etc/init.d`;
  - *Esses scripts (/etc/init.d) aceitam argumentos como* `start`, `stop`, `restart`.
    - `# /etc/init.d/apache2 restart`

- **Poweroff:**
  - Idêntico ao comando halt, porém solicita o sistema de gerenciamento de energia em sistemas que possuem um, para desligar a alimentação principal do sistema
