# Introdução Redes

## Hardware de Rede

- Broadcast: Um pra todos;
- Ponto a Ponto: 1 a 1.

### Tipos de Rede

- Redes Pessoais - PAN
- Redes Locais - LAN
- Redes Metropolitanas - MAN
- Redes de Longas Distâncias - WAN
- Redes Interligadas - Internet

## Software de Rede

- Camadas de Rede (Modelo OSI):
  - 1: Física:
    - Trata da transmissão de bits;
    - Garante que, se for enviado um bit **1**, o outro lado receberá um bit **1**.
  - 2: Enlace de Dados:
    - Trata os dados para que possam ser enviados livre e tranquilamente;
    - Fornece controle de acesso ao meio.
  - 3: Rede:
    - Determina a maneira como os pacotes são **roteados** da origem até o destino.
  - 4: Transporte:
    - Garante que os dados chegarão corretamente ao destino.
  - 5: Sessão:
    - Permite que diferentes máquinas estabeleçam sessões de comunicação entre si.
  - 6: Apresentação:
    - Cuida da sintaxe e semântica das informações transmitidas.
  - 7: Aplicação:
    - Onde ficam os protocolos comumente utilizados pelos usuários.
- Camadas de Rede (Modelo TCP/IP):
  - 1: Enlace:
    - Não é uma camada propriamente dita, mas uma interface entre os hosts e os enlaces de transmissão.
  - 2: Internet:
    - Entrega os pacotes IP onde são necessários;
    - O **roteamento** é extremamente importante nessa camada.
  - 3: Transporte:
    - Permite que hosts de origem e destino mantenham uma conversação.
    - Protocolos:
      - **TCP (Transmission Control Protocol)**:
        - Orientado a conexões;
        - Confiável, entrega o fluxo de bytes sem erro.
      - **UDP (User Datagram Protocol)**:
        - Nâo orientado a conexões;
        - Não confiável, pode perder pacotes no meio do caminho;
        - Muito utilizado em transmissão de voz ou vídeo.
  - 4: Aplicação:
    - Contém todos os protocolos de nível mais alto
    - Ex.: SMTP, TELNET, FTP

## Principais Padronizações de Rede

- 802.1 Avaliação e arquitetura de LANs
- 802.3 Ethernet
- 802.11 LANs sem fios (WIFI)
- 802.15 Redes pessoais (bluetooth, Zigbee)

## Topologias

### Linear/Barramento

- Todas as estações são ligadas a um único cabo comum (Backbone);
- Quando um sinal é lançado na rede, ele percorre ambas as direções, atingindo todos os nós;
- Quando o sinal chega nas extremidades, ele é destruído.

### Anel

- Os nós se ligam uns aos outros, formando um anel;
- Não tem início e nem fim;
- Cada estação funciona como um repetidor;
- O anel é de mão única.

### Estrela

- Tem um elemento central (HUB ou Switch) que gerencia o fluxo de dados;
- Como o HUB repete os dados para todas as portas, ao utilizá-lo, age como linear;
- O Switch limita a porta que o dado deve ir, portanto, age como estrela.

### Malha

- Geral ligado em geral.

### Hierárquica

- Em cadeia de hierarquia.
