# OpenMulticryptocoinWallet
Wallet multicoin OPEN SOURCE


## Arquitetura

Teremos basicamente 3 camadas distintas:

- fullnode para casa moeda desejada;
- api específica para cada fullnode;
- api genérica para acesso externo.


### Fullnode

Para cada moeda desejada seu fullnode deverá ser executado "localmente" pois TODAS as ações requeridas pela carteira irão bater diretamente NESSE fullnode local para garantir maior segurança e velocidade nas transações.


### Adapter - API


### Facade - API
