# SYSLOG

- Praticamente tudo gera registros que precisam ser resumidos e armazenados po certo tempo
- As diretivas de registro em log variam de instalação para instalação
- Esquemas comuns incluem:
  - Jogar fora todos os dados imediatamente
  - Reiniciar arquivos de log em intervalos periódicos
  - Fazer um rodízio dos arquivos de log, mantendo dados por um período fixo
  - Compactar e arquivar logs em fita ou outras mídia permanentes
- A escolha correta depende da preocupação com segurança e o espaço em disco disponível
- Automatize a manutenção dos arquivos com `cron`
- `/var/log` e `/var/adm` são locais comuns de armazenamento desses registros
- `/etc/syslog.conf` = arquivo de configuração do syslog

## Arquivos de log especiais

- `/var/log/wtmp`
  - Contém um registro de logins e logouts, reinicializações e desligamentos do sistema
  - É mantido em binário, se decodifica com `last`
- `/var/logg/lastlog`
  - Mesmo esquema do `wtmp`, mas registra apenas o tempo de login
- O arquivo de configuração `logrotate` é formado por especificações para gerenciamento de logs.
  - Excelente recurso para gerenciamento

## Syslog

- Sistema de registro de log abrandente
  - Possui a habilidade de centralizar o registro em log para uma rede
  - Libera os programadores da mecânica entediante da gravação de log
  - Coloca o adm no controle do processo de registro
- Syslog é formado por 3 partes:
  - `Syslogd`
    - Daemon de registro em log
  - `openlog et al`
    - Rotinas de biblioteca que submetem mensagens s syslog
  - `logger`
    - Commando em nível de usuário que submete entradas de log no shell
