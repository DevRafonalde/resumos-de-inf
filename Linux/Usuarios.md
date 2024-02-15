# USUÁRIOS

## ARQUIVO /ETC/PASSWD

- Representa uma lista de usuários reconhecidos pelo sistema
  - `# nano /etc/passwd`
  - Formato: `NOME:SENHACRIPTOGRAFADA:UID:GID:GECOS:DIRETORIOHOME:SHELL`
  - Exemplo: `rafael:x:1002:1003:Rafael,Bukinha:/home/rafael:/bin/bash`

## O ARQUIVO /ETC/SHADOW

- Só é legível pelo root e serve para manter senhas criptografadas protegidas
  - `# nano /etc/shadow`
  - Formato: `NOME:SENHACRIP:DATAMUDSENHA(NUMDIADESDE1970):NUMMINDIAS:NUMMAXDIAS:NUMALERTA:DIASDESAB:DATAEXPIR`
  - Exemplo: `rafael:SENHACRIP:13348:0:180:14::14974`

## ARQUIVO /ETC/GROUP

- Nomes dos grupos e lista de membros de cada grupo
  - `# nano /etc/group`
  - Formato: `NOMEGRUPO:SENHA:GID:USUARIOS`
  - Exemplo: `albuquerques:x:24:rafael,camila,eduardo,leonardo,ana paula,alexandre`

## ADICIONAR USUÁRIOS

- Editar os arquivos "passwd" e "shadow" para definir a conta do usuário
- Adicionar o usuário ao arquivo "group"
- Configurar uma senha inicial
- Criar e aplicar os comandos "chown" e "chmod" do diretório inicial do usuário
- Isso tudo pode ser feito de forma manual ou automatizada com o comando "useradd"

## REMOVER USUÁRIO

- `userdel`

## DESATIVAR USUÁRIO

- Colocar manualmente um asterisco ou outro caractere na frente da senha encriptada no arquivo "shadow"
- Ou utilizar `usermod -L usuario` para BLOQUEAR e `usermod -U usuario` para DESBLOQUEAR senhas

## GERENCIAR GRUPOS

- `groupadd`, `groupmod` e `groupdel`
- Mesma coisa que os de usuário, mas para grupo
