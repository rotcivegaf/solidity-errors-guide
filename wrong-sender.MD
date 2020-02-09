When we want sent a transaction with invalid address

The log error:
```
     Error: Returned error: sender account not recognized
     at PromiEvent (/home/.nvm/versions/node/v8.10.0/lib/node_modules/truffle/build/webpack:/packages/contract/lib/promievent.js:9:1)
      at TruffleContract.approve (/home/.nvm/versions/node/v8.10.0/lib/node_modules/truffle/build/webpack:/packages/contract/lib/execute.js:169:1)
      at setApproveBalance (test/Test.js:43:17)
      at <anonymous>
      at process._tickCallback (internal/process/next_tick.js:188:7)
```

The solution its send the transaction with a account example: '0x990D8026871db9bfAb5f0054f6fC5E7B5c77cFa5'
