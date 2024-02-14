# CRON

## AGENDANDO COMANDOS

- A execução periódica é normalmente tratada pelo **daemon** `cron.cron` e é iniciado junto ao sistema e permanece em execução enquanto o sistema estiver no ar
- `ISC cron`, `Vixie-cron` ou `crond`
- `crontab` = arquivo de configuração e pode estar em 3 locais diferentes:
  - `/var/spool/cron` no SUSE e `/var/spool/cron/crontabs` no Debian
  - `/etc/cron.d`
  - `/etc/crontab`

### Cron

- Lê todos os seus arquivos de configuração, verifica os horários de modificação nos arquivos crontab, recarrega quaisquer arquivos que foram modificados e depois executar quaisquer tarefas programadas e retornar ao seu estado de dormência.

- `MINUTO HORA DIA MES DIASEMANA NOMEUSUARIO COMANDO`

- Cada um dos campos relacionados a data/hora pode conter:

  - Um * em qualquer campo, ele vai repetir em todos
        - Ou seja, se eu coloco um * no campo de minutos, ele vai repetir todos os minutos

    - Um inteiro único, que coincide exatamente

    - Dois inteiros separados por um traço, coincidindo com um **intervalo de valores**
      - Ou seja, se eu coloco 0-30 no campo de minutos, ele vai repetir a cada minuto dentro desse intervalo
  
    - Uma série de inteiros ou intervalos separados por vírgulas, coincidindo com qualquer valor listado
      - Ou seja, se eu coloco 0, 30 no campo de minutos, ele vai repetir no minuto 0 e no 30.
      - Posso fazer o mesmo com intervalos

    - Ex.:
        `45 10 * * 1-5` = 10:45 da manhã, todos os dias de todos os meses de segunda à sexta

        `0,30 * 13 * 5` = A cada meia hora todas as sextas E a cada meia hora  do  13º dia do mês
        OBS.: **NÃO É "CADA MEIA HORA DA SEXTA-FEIRA 13**

        `55 23 * * 0-3,6  /staff/trent/bbin/checkservers` = O comando `/staff/trent/bbin/checkservers` será executados nos domingos, segundas, terças, quartas e sábados às 23:55

## GERENCIAMENTO DO CRONTAB

- `crontab filename`
  - Instala filename (nome do arquivo) como seu crontab, sustituindo qualquer versão anterior
- `crontab -e`
  - Verifica uma cópia de seu crontab
- `crontab -l`
  - Lista o conteúdo do seu crontab para saída padrão
- `crontab -r`
  - Elimina os arquivos crontab
- Os arquivos `/etc/cron.deny` e `/etc/cron.allow`, especificam quais usuários podem submeter arquivos crontab
