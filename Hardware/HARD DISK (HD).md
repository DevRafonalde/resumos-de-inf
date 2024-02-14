# HARD DISK (HD)

## GEOMETRIA ou CHS
- Internamente, um HD tem um ou mais discos magnéticos em seu interior, chamados pratos;
- Cada face de cada prato é dividida em várias trilhas, que são divididas em vários setores. Cada setor armazena 512 bytes de informação;
- "Cilindro" é usado para identificar todas as trilhas de mesmo número de ordem localizadas em todas as faces de todos os pratos;
- "Cabeça" é cada face de cada prato.

  Número total de setores = Trilha x Lados x Setores

- Cada setor é formado por: Cabeçalho, Área de Dados e Rodapé;

- Antigamente era usado o método CHS para acessar um setor (informava face, trilha e setor);
- Atualmente se utiliza o LBA que tem apenas um parâmetro.

## FORMATAÇÃO
- **Baixo nível (Formatação física)**
  - Divide a superfície magnética do disco em trilhas e setores;
  - Feito na fábrica;
  - Destrói o disco permanentemente, pois apaga os "servos" (orientação das cabeças).

- **Alto nível (Formatação lógica)**
  - Cria as estruturas a serem usadas pelo SO;
  - Não apaga o conteúdo do HD;
  - Apaga os setores que contém estruturas de armazenamento.

## TECNOLOGIA SMART
- Informa ao usuário caso o HD esteja prestes a falhar, monitorando os seguintes parâmetros:
  - Número de erros de leitura acima do normal;
  - Taxa de transferência abaixo do normal;
  - Tempo para RPM máximo acima do normal;
  - Número de setores reserva alto;
  - Cabeças mais próximas da superfície magnética.