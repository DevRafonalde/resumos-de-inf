# Redes

## Roteamento

- As informações de roteamento assumem a forma de regras (rotas)
- Pode haver uma rota padrão caso falte especificar a rota de algum pacote
- Ficam armazenadas em uma tabela no kernel
- `netstat -r` = Examinar a tabela de roteamento
- `netstat -rn` = Não resolve os nomes, apresenta infos de forma numérica (IP ao invés do nome)
- A palavra roteamento é usada normalmente com dois significados:
  - Pesquisar um endereço de rede na tabela de roteamento
  - Construir uma tabela de roteamento primária
- As tabelas de roteamento podem ser configuradas **estática**, **dinâmicamente** ou com uma **combinação dos dois métodos**

### Roteamento Estático

- Uma **rota estática** é uma que introduzimos explicitamente por meio do comando `route`
  - `route add -net 132.236.220.64 netmask 255.255.255.192 gw 132.236.212.6 eth1`
- Para adicionar uma rota padrão para um endereço que não se encontre na tabela de roteamento, utiliza-se o **gateway padrão de rede**
- Para especificar o computador 192.168.1.1 como **gateway padrão** usamos:
  - `route add default gw 192.168.1.1 eth0`

### Roteamento dinâmico

- Para redes mais complicadas, é necessário o emprego de **roteamento dinâmico**, que é executado por um daemon que mantém e modifica a tabela de roteamento
- `route del` = Elimina uma entrada específica da tabela de roteamento
- `ARP` = Descobre o endereço de hardware (MAC) associado a determinado IP
- `RARP` = Descobre o IP associado a um MAC
- Configurar a rota padrão no Debian e Ubuntu
  - Arquivo a ser alterado: `/etc/network/interfaces`
  - Variável a ser alterada: `gateway`

## Adição de uma máquina na rede

- Atribuir um nome de host e um endereço IP exclusivos
- Definir o novo host para configurar suas interfaces de rede em tempo de inicialização
- Configurar uma rota padrão e talvez roteamento mais complexo
- Apontar para um servidor de nomes DNS, para possibilitar o acesso à Internet
- Arquivos de configuração no Debian e Ubuntu:
  - `/etc/hostname` = Nome de host
  - `/etc/network/interfaces` = Ip, máscara, rota padrão

## `ifconfig`: Configurando interfaces de rede

- Ativa ou desativa uma interface de rede
- Configura o seu endereço IP e máscara de sub-rede
- Configura várias outras opções e parâmetros
- Executado em tempo de inicialização, mas pode fazer alterações dps
- `ifconfig interface endereço opções ... up ...`
- `ifconfig eth0 192.168.1.13 netmask 255.255.255.0 up`
- `ipconfig interface` exibe as configurações atuais para interface sem alterá-las
- `ifconfig -a` pode descobrir quais interfaces estão presentes no sistema.
  - Caso seu sistema não interprete ifconfig, pode tentar netstat -i para descobrir o nome das interfaces
