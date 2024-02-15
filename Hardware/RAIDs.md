# REDUNDANT ARRAY OF INDEPENDENT DISKS (RAID)

- Permite que HDs ou SSDs sejam combinados para aumentar o desempenho ou a confiabilidade;
- Os métodos de divisão de dados e espelhamento são a base do RAID.

## VERSÕES

### RAID 0

- É a forma mais simples do método de divisão de dados = desempenho;
- Requer pelo menos duas unidades de armazenamento;
- Se uma unidade falhar, o arranjo para de funcionar e há perda de dados.

### RAID 1

- É a forma mais simples do método de espelhamento = segurança;
- Se uma das unidades falhar, o arranjo continua em operação e não há perda de dados.

### RAID 0+1

- É a combinação dos modos 0 e 1 ao mesmo tempo;
- São necessárias pelo menos quatro unidades de armazenamento;
- Deve-se usar um número par de unidades.

### RAID 10

- Idêntico ao RAID 0+1;
- A diferença está no modo em que as unidades de armazenamento são organizadas;
- Com quatro unidades, são formados dois arranjos de RAID 0 e depois mais dois RAID 1 com esses dois 0.

### RAID 1E

- Montam o modo RAID 10 com apenas METADE da capacidade de armazenamento das unidades;
- Não apresenta o mesmo nível de confiabilidade do modo 10;

### RAID 2

- Igual ao RAID 0 com informações de paridade POR CÓDIGO HAMMING gravados em uma unidade de armazenamento à parte.

### RAID 3

- Igual ao RAID 0 com informações de paridade gravados em uma unidade de armazenamento à parte.

### RAID 0+3, 30 ou 53

- Funciona combinando-se unidades de armazenamento em RAID 0 e depois combinando esses arranjos em RAID 3;
- São necessárias pelo menos seis unidades para montar esse modo.

### RAID 4

- Igual ao RAID 3, porém usando um método diferente para o cálculo da informação de paridade.

### RAID 5

- É um RAID 0 que grava informações de paridade, aumentando a confiabilidade do arranjo;
- As informações de paridade são gravadas nas mesmas unidades do armazenamento dos dados;
- Requer ao menos 3 unidades de disco.

### RAID 6

- Igual ao RAID 5, porém gravando duas informações de paridade;
- São necessárias pelo menos quatro unidades para montar esse arranjo.

### RAID 7

- É uma marca registrada da empresa Storage Computer Corporation, sendo um método RAID proprietário;
- Funciona como os modos RAID 3 e 4, porém usando cache de dados para aumentar o desempenho.

- RAIDs de Hardware tem maior desempenho do que RAIDs de software.
