# GERENCIAMENTO DE SOFTWARE E CONFIGURAÇÃO

- Há **dois formatos** de pacotes sendo utilizados comumente:
  - O Red Hat, Fedora, o SUSE e outros utilizam o `.rpm`
  - O Debian e o Ubunto utilizam formatos `.deb`
  - Ambos funcionam de forma semelhante

## Sistemas de gerenciamento de baixo nível

- `rpm`
  - O comando `rpm` instala, verifica  e consulta  status dos pacotes `.rpm`
- `dpkg`
  - O comando `dpkg` instala, remove e lista pacotes

## Sistemas de gerenciamento de alto nível

- Sistemas de gerenciamento como o `APT` e `YUM` compartilham vários objetivos
  - Simplificar a localização e processo de cópia  de pacotes
  - Automatizar o processo de atualização de sistemas
  - Facilitar o gerenciamento de dependências entre pacotes

| PACOTES     | ALTO NÍVEL      | BAIXO NÍVEL       |
|---------------------|----------|-----------|
| Debian/Ubuntu      | APT        | `dpkg` |
| Red Hat           | YUM    | `rpm`     |

## APT: A ADVANCED PACKAGE TOOL

- O APT é um dos sistemas de gerenciamento de pacotes mais maduros
- É possível atualizar um sistema inteiro com um único comando `apt-get`
- Para seu funcionamento, utiliza-se  o arquivo `//etc/apt//sources.list`, que lista as "fontes" de onde ele obterá os pacotes
- Assim que configurar esse arquivo, resta apenas executar `apt-get update` para atualizar as informações do `apt-get`
- Depois disso, basta executar `apt-get install nomeDoPacote` para instalar ou atualizar um pacote
