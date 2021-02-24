# A STARTER CODE TO USE TRUFFLE WITH BINANCE

The `.env.example` file contains all information to make this script run perfectly, duplicate this file and rename it to `.env`, then fill in every variable with your details.

### ENV VARIABLES

##### BINANCE CONFIGURATIONS

```js
BSC_PRIVATE_KEY; // Variable responsible for the private key of the `SmartChain` address you wish to deploy with.
BSC_SEED_PHRASE; // Your `SmartChain` wallet 12 mnemonic phrases, first account will be used to deploy the contract by default
BSC_API_KEY; // Your `SmartChain` API KEY gotten from bscscan.com/myapikey, this is used to verify deployed contracts on testnet and mainnet
```

##### ETHEREUM CONFIGURATIONS

```js
ETH_PRIVATE_KEY; // Variable responsible for the private key of the `Ethereum` address you wish to deploy with.
ETH_SEED_PHRASE; // Your `Ethereum` wallet 12 mnemonic phrases, first account will be used to deploy the contract by default
ETH_API_KEY; // Your `Ethereum` API KEY gotten from etherscan.com/myapikey, this is used to verify deployed contracts on testnet and mainnet
INFURA_PROJECT_ID; //This should hold your infura project id
```

### USING THE REPO

Run `yarn install` to install all dependencies

---

The `truffle-config.js` file has 5 networks:

```js
ganache = "to deploy to the ganache network";
bsc_test = "deploy to the binance testnet";
bsc_main = "deploy to the binance mainnet";
eth_test = "deploy to the ethereum ropsten testnet";
eth_main = "deploy to the ethereum mainnet";
```

To deploy a contract you first need to create a migration file that deploys your specified contract, finally run:

###### Deploy contracts to specified network

`truffle migrate --reset --network <network_name>`

###### Run contract tests on a specified network

`truffle test --network <network_name>`

Where `network_name` is any of the above mentioned network.

###### Verify deployed contracts on testnet or mainnet

`truffle run verify <contract>@<contract_address> --network <network_name>`

Where:

1. `contract` is the name of the deployed contract you wish to verify.
2. `contract_address` is the address of the deployed contract you wish to verify.
3. `network_name` is any of the above mentioned network.

E.G: I want to verify a contract named ZeekToken and the address is 0x3582AFa8dfaF9e2072467908392459CF184a9399 deployed on the bsc mainet, I'll simply run `truffle run verify ZeekToken@0x3582AFa8dfaF9e2072467908392459CF184a9399 --network bsc_main`;

BTW I have a playlist of this repo which you can find here: [Contracts Development on Binance Smart Chain with Truffle](https://www.youtube.com/playlist?list=PLG3Tf5BKdISnT1NjbIuAgRzvwnTs72p-F)
