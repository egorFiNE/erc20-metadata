# Quick loader of ERC20 token metadata

Simple on-chain lookup of `name`, `symbol` and `decimals`. Supports both backend and frontend as well as web3 and ethers.js.

# Usage with web3

```javascript
import ERC20 from 'erc20-metadata';

// import web3, connect to provider,

// Note: ERC20 ABI is included in this module for your convenience
const token = new web3.eth.Contract(ERC20.ABI, USDT_ADDRESS);

// Query the basic three metadata properties
await ERC20(token);

// `token.erc20` object has been added to `token`:
console.log(token.erc20.symbol, token.erc20.name, token.erc20.decimals);

// And `decimals` is a `Number`:
console.log(typeof token.erc20.decimals);
```

# Usage with ethers.js

Exactly the same as web3:

```javascript
// ...
const token = new ethers.Contract(USDT_ADDRESS, ERC20.ABI, provider);
await ERC20(token);
console.log(token.erc20.symbol, token.erc20.name, token.erc20.decimals);
```

# Typescript support

See `index.js`. This module is way too simple to be written in TypeScript. Contributions are welcome for the types support, though.

# Tests

See `index.js`. This module has no logic of it's own to test.

