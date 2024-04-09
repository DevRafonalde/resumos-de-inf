# Gerenciamento de Memória

- A parte do SO que gerencia (parte da) hierarquia de memórias é chamada de **gerenciador de memória**;
  - Sua função é gerenciar eficientemente a memória: controlar quais partes estão sendo usadas, alocar memória para processos quando eles precisrem e liberá-la quando tiverem terminado;
- Sem abstração de memória, não tem como rodar dois programas ao mesmo tempo;

## Uma abstração de memória: espaço de um endereçamento

- Como um todo, expor a memória física a processos tem várias desvantagens importantes;
- Ao endereçar cada byte de memória, programas podem derrubar o SO, sem querer ou de propósito;
- Esse problema existe mesmo que so uma aplicação esteja rodando;
  <br>
- Dois problemas precisam ser solucionados para permitir que múltiplas aplicações rodem ao mesmo tempo: **proteção e realocação**;
- Solução primitiva para o primeiro caso, usada no IBM 360:
  - Rotular blocos de memória com uma chave de proteção e comparar a chave do processo em execução com aquele de toda palavra de memória buscada;
- Porém, não resolve o segundo B.O;
- Para isso, foi criado o espaço de endereçamento, que resolve os dois problemas;

## Troca de processos (Swapping)

- Consiste em trazer cada processo em sua totalidade, executá-lo por um tempo e então colocá-lo de volta no disco;
- Processos ociosos estão armazenados em disco em sua maior parte, portanto não ocupam qualquer memória quando não estão sendo executados;
- Outra estratédia, chamada de **memória virtual**, permite que os programas possam ser executados mesmo quando estão apenas parcialmente na memória principal;

## Memória Virtual

- Há outro problema que precisa ser solucionado: **gerenciar o bloatware**;
  - **Bloatware** é o termo utilizado para definir softwares que usam quantidadaes excessivas de memória;
- Uma solução adotada nos anos 60 foi **dividir os programas em módulos pequenos**, chamados de **sobreposições**;
- Mas isso deveria ser feito pelo programador e não era eficiente;
- O método encontrado ficou conhecido como **memória virtual**;
- A ideia básica é que **cada programa tem seu próprio espaço de endereçamento**, o qual é dividido em blocos chamados de páginas;
- Cada página é uma séria contígua de endereços. Elas são mapeadas na memória física, mas nem todas precisam estar lá ao mesmo tempo;
- Quando o programa referencia uma parte que está nno hardware, a busca é rápida no hardware, caso não esteja na física, ele busca a parte que falta e reexecuta.
