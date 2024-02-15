# BACKUP

- Permitem a um administrador restaurar  um sistema de arquivos (ou parte)
- Devem ser gravados em algum tipo de mídia removível
- `dump`
  - Cria uma lista de arquivos que foram modificados desde um `dump` anterior, depois enpacota esses arquivos em um único grande arquivo para arquivamento em um dispositivo externo
- `restore`
  - Restaura `dump`
- `tar` = empacotando arquivos
  -Lê vários arquivos ou diretórios e os empacota num único arquivo
  -Útil caso o ackup seja previsto
- `cpio` = utilitário de arquivamento arcaico
  - Similar ao tar
  - Raramente utilizado hoje
- `dd` = lidando com bits
  - Copia seus arquivos de entrada para os de saída
- `mt`
  - Útil para fazer vários `dump`s

## BACULA

- Solução de backup cliente/servidor corporativa

### Componentes

- Console
- Catálogo
- Daemon diretor
- Daemon de armazenamento
- Daemon de arquivo cliente
