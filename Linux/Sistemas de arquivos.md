# SISTEMA DE ARQUIVOS

- Tem como objetivo representar e organizar os recursos de armazenamento de um sistema
- Pode ser imaginado como quatro componentes principais

  1. Um espaço de nomes
     - Uma maneira de dar nomes às coisas e organizá-las de forma hierárquica

  2. Uma API
     - Um conjunto de chamadas de sistema para navegar e manipular objetos

  3. Um modelo de segurança
     - Um esquema para proteger, ocultar e compartilhar coisas

  4. Uma implementação
     - Software que amarra o modelo lógico ao hardware em si

## NOMES DE CAMINHO
- "/" = diretório raíz

## MONTAGEM E DESMONTAGEM
- O comando "mount" ensina o SO a deixar um sistema de arquivos disponível para uso em um local específico denominado "ponto de montagem"
  - `# mount /dev/hda4 /users`
- Uma lista dos sistemas que são normalmente montados em um sistema é mantida no arquivo /etc/fstab
- Se o sistema estiver vazio, pode-se desmontar com "umount"
- "fuser" exibe cada processo que está utilizando um arquivo ou diretório nesse sistema para fins de desmontagem
- O diretório raíz do processo é configurado através do "chroot"

## PERMISSÕES
- `r` = Read = 4
- `w` = Write = 2
- `x` = Execute = 1

- `U` = Proprietário do arquivo
- `G` = Grupo do proprietário
- `O` = Outros usuários
- `A` = Todos

  - `# chmod PROP(soma valores acima) GR(soma valores acima) OUTROS(soma valores acima) CAMINHO`
  - `# chmod 574 /usr/include`

  - Também pode ser usado assim:
    - `# chmod U +/=/- r /usr/include`

## BITS SETUID E SETGID
- `+/- S`
- Faz aquele grupo (U, G, O ou A) executar com a permissão do root
  - `# chmod u+s usr/include`
- O usuário proprietário da pasta vai estar executando os processos com a permissão do root

## STICKY BIT
- Mesmo esquema de configuração do SETUID, mas com T ao invés do S
- Não permite que usuários comuns apaguem ou renomeiem o arquivo, apenas o root e o proprietário

## CHOWN
- Altera o proprietário e/ou o grupo de um arquivo/diretório

## UMASK
- Manipula as permissões padrão dos arquivos, dizendo quais serão revogadas. Por exemplo:
  - `# umask 027`
  - Todas as permissões para o proprietário, nenhuma revogada;
  - Proíbe gravação para o grupo (w = 2);
  - Não dá nenhuma permissão para os demais (r+w+x = 4+2+1);
  - Resultado: `rwx r-x ---`
  - O valor padrão de umask é 022.

## LS -LD
- TIPO PERMISSOES QNTDLINKS PROPRIETÁRIO GRUPO TAMANHO(BYTES) DATAMOD CAMINHO
  - `# ls -ld /user/include`
  - `drwxrwxr-- 27 root root 4096 datahora /usr/include`
