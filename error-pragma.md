When we have a configuration file for truffle (truffle.js) with different version of pragma than we use in contracts

In contract file we have solidity 0.5.11 version:
```
pragma solidity ^0.5.11;
contract Example {
}
```
In truffle config file we have solidity 0.5.6 version:
```
module.exports = {
  networks: {
    development: {
      host: 'localhost',
      port: 8545,
      network_id: '*',
    },
  },
  compilers: {
    solc: {
      version: '0.5.6',
      docker: false,
      settings: {
        optimizer: {
          enabled: true,
          runs: 200,
        },
        evmVersion: 'constantinople',
      },
    },
  },
};
```
The log error:
```
Compiling your contracts...
===========================
> Compiling ./contracts/Example.sol
TypeError: Cannot read property '0' of null
    at detectErrors (/.nvm/versions/node/v8.10.0/lib/node_modules/truffle/build/webpack:/packages/compile-solidity/run.js:283:61)
    at run (/.nvm/versions/node/v8.10.0/lib/node_modules/truffle/build/webpack:/packages/compile-solidity/run.js:36:29)
    at <anonymous>
Truffle v5.1.8 (core: 5.1.8)
Node v8.10.0
```
The solution its increase the truffle config version to the contract version(0.5.11) or downgrade the pragma version of the contract(0.5.6) to the truffle config


