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

Cada módulo de Adapter será uma "ponte adaptadora! entre a API específica de cada moeda com a API genérica, para isso precisamos ter os seguintes módulos EM TODAS as moedas:

- Account;
- Block
- Info;
- Transaction;
- Wallet;


## Workflow - Wallet

Com uma carteira digital nós devemos poder:

- criar uma CONTA nova
 - definir uma senha (optional)
 - encriptar (optional)
- criar uma CARTEIRA nova, sendo filha da CONTA
  - definindo uma seed inicial (optional)
  - ler a CHAVE PUBLICA
  - ler a CHAVE PRIVADA (caso seja o dono da CONTA)
- enviar moedas
  - definir qual categoria de TAXA quer pagar
    - low (pagar pouco mas demora mais)
    - medium (pagar médio e demora médio)
    - high (pagar alto e demora menos)
- receber moedas
  - definir um tempo máximo para o pagamento (optional)

## Workflow - Recebendo um Pagamento


```js
Account.create => Wallet.create => Transaction.receive => Transaction.end

accountAddress => 
  Wallet.create(accountAddress) => 
    Transaction.receive(wallettAddress, amount, finish = 'receive') => 
      Transaction.end(transactionHash, amount, finish)
```


### Adapter - API - Account

### Adapter - API - Block

### Adapter - API - Info

### Adapter - API - Transaction

### Adapter - API - Wallet

- createWallet;
- getBalance;
- getAddress;
- getTransaction;
- send;
- receive;


### Facade - API

Por hora temos as seguinte funcionalidades básicas:

- getBalance;
- getDepositAddress;
- getWhitdrawAddress;
- send/pay;
- receive;
