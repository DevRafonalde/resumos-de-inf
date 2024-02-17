# Sistema de arquivo de rede

- O **Network Fily System**, comumente conhecido como NFS, permite compartilhar sistemas de arquivos entre computadores.
- o **NFS** é quase transparente para os usuários e é "sem estado", o que significa que nenhuma informação é perdida quando um servidos NFS trava
- **Suportado por TODAS as distribuições do Linux**
- Componentes:
  - Protocolo de montagem
  - Servidor de montagem
  - Daemons
  - Outros utilitários de diagnóstico

## Informações gerais sobre o NFS

### Acesso de root e a conta nobody

- É tradicional impedir que root seja executado irrestritamente em sistemas de arquivos montados com NFS
- `squashing root` = limita o root e o "transforma" no pseudo-usuário `nobody`
