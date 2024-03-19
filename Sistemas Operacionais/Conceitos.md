# Conceitos de Sistemas Operacionais

## Processos

- Processo: Programa em execução;
- Espaço de endereçamento:
  - Associado a cada processo;
  - Uma lista de posições de memória que vai de 0 a algum máximo, onde o processo pode ler e escrever;
  - Contém o programa executável, os dados do programa e sua pilha;
  - Também chamado de **imagem do núcleo**;
- Tabela de processos: Guarda todas as informações dos processos, com exceção do endereço;
- Estrutura da árvore: "Árvore" de processos;
- Chamadas de sistema: Abrem, leem e fecham os arquivos;
- Descritor de arquivo: É retornado pelo sistema caso o acesso a um arquivo seja permitido;
- Pipe: Usado para conectar dois processos;
