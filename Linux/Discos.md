# DISCO

## INTERFACES DE DISCO

- **PATA (também conhecida como IDE)**
  - Foi desenvolvido como uma interface simples e de baixo custo para PCs
- **Serial ATA / SATA**
  - Sucessor do IDE convencional
- **Fibre Channel**
  - Interface serial que está ganhando popularidade
- **USB**
  - Tornou-se popular para conexão de dispositivos como teclados e mouses

## SISTEMAS DE ARQUIVOS DO LINUX

- **VFS (Virtual File System)**
  - Fornece estrutura necessária para montar sistemas de arquivos nativos
- **Ext2fs**
  - O segundo sistema e arquivos estendido conhecido comumente como ext2s foi, por muito tempo, o principal sistema de arquivos do Linux
- **Ext3fs**
  - Versão melhorada do ext2s mas com o acréscimo do "journaling (salva primeiro aqui dps no geral, oferece um 'backup')"
- **ReiserFS**
  - Escrito por Hans Reiser. Tem "journaling", fornece uma interface para manipulação e proteção dos arquivos
- **XFS e JFS**
  - XFS da SGI e JFS da IBM. Bons, mas perde pro ext2 e 3.

## COMANDOS IMPORTANTES

- **`mount`**
  - Monta sistemas de arquivos
- **`df`**
  - Verifica o tamanho de um sistema de arquivos
- **`hdparm`**
  - Interage com o driver IDE do Linux para obter e alterar parâmetros do disco
- **`mdadm`**
  - Gerencia o RAID, é poderoso e fácil de se utilizar
- **`fsck`**
  - Corrige problemas no sistema de arquivos de maneira mais segura e automática
- **`/etc/fstab`**
  - Contém detalhes para a montagem dos sistemas de arquivos do sistema
- **`lvcreate`**
  - Cria partições nos volumes
  - `# lvcreate -L 10G -n sinsenhor LVM1`
    - Criou, dentro do grupo "LVM1", um volume lógico com 10GB
- **`mkfs`**
  - Cria um sistema de arquivos Linux
- **`fdisk`**
  - Formata um disco
  - Interativo ao apertar a tecla "m" que mostra uma lista de seus comandos:
    - `n` ou `new` = cria uma partição nova
    - `t` ou `type` = altera o tipo de uma partição
    - `p` ou `print` = imprime uma tabela de partição
    - `w` ou `write` = grava a tabela de partições no disco

## MONTANDO UNIDADES USB

- `# /sbin/lsusb`
  - Lista os dispositivos USB que o kernel descobriu
- A unidade precisa ser montada pelo Linux antes de poder ser utilizada
  - `# mkdir /mnt/usb` // Cria um ponto de montagem
  - `# mount /dev/sde1 /mnt/usb` // Monta
- O kernel associou o dispositivo "/dev/sde" ao disco e o disco contém apenas uma única partição, "sde1"
- A unidade foi montada em "/mnt/usb" e está pronta para uso
