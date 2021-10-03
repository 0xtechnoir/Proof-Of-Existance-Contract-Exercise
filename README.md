# Proof Of Existance Consensys Accadamy Bootcamp Exercise

This repo contains a simple application that takes the hash 'document' and stores it on-chain. This proving its existence at a specific point in history.

There are 3 versions of the application:

1. **ProofOfExistence1.sol** - most basic proof of concept
2. **ProofOfExistence2.sol** - additional functionality to check whether a document is stored.
3. **ProofOfExistence3.sol** - Uses the same code as ProofOfExistence2.sol but rather than using an array of bytes32 to store the document hashes it makes use of a mapping. This method is much less expensive (in terms of gas) to lookup data.

The truffle-config.js file defines both a development and a test (Rinkeby) network for deploying contracts.

To use the Rinkeby network you will need to create a .secret file in the prijects root directory and paste in your metamask 12 word seed phrase. This will allow your metamask browser extension to deploy your smart contracts to the Rinkeby network.

## Useful Commands:

```
// Creating and deploying contracts
truffle create contract ProofOfExistence1
truffle migrate
truffle migrate --reset

// Interacting with the smart contract
truffle console
const poe = await ProofOfExistence1.at(ProofOfExistence1.address)
poe.notarize('Hello World!')
poe.checkDocument('Hello World!')
.exit

// Deploying on Rinkeby
truffle migrate --network rinkeby

```
