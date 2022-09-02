# Upgradeable-Smart-Contract
Upgrading Smart Contracts through Proxy Patterns, We know that smart contracts on Ethereum are not upgradeable, as the code is immutable and cannot be changed once it is deployed. But writing perfect code the first time around is hard, and as humans we are all prone to making mistakes. Sometimes even contracts which have been audited turn out to have bugs that cost them millions.

To upgrade our contracts we use something called the Proxy Pattern. The word Proxy might sound very familiar to you because it is not a web3-native word.

Essentially how this pattern works is that a contract is split into two contracts - Proxy Contract and the Implementation contract.

The Proxy Contract is responsible for managing the state of the contract which involves persistent storage whereas Implementation Contract is responsible for executing the logic and doesn't store any persistent state. User calls the Proxy Contract which further does a delegatecall to the Implementation Contract so that it can implement the logic by using delegate call.

This pattern becomes interesting when Implementation Contract can be replaced which means the logic which is executed can be replaced by another version of the Implementation Contract without affecting the state of the contract which is stored in the proxy.

Singleton Patterns
There are mainly three ways in which we can replace/upgrade the Implementation Contract:

- Diamond Implementation
- Transparent Implementation
- UUPS Implementation
