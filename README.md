Simple multisig wallet dapp...

**TODO:**

**1. Configure Truffle to use Infura with hdwallet-provider**

in project root
```
npm install @truffle/hdwallet-provider
```
in truffle-config.js:
```
const provider = require('@truffle/hdwallet-provider');
const fs = require('fs');
const privateKeys = JSON.parse(fs.readFileSync('.secrets.json').toString().trim());
...
networks: {
  kovan: {
    provider: () =>
      new provider(
        <private keys, array or mnemonic phrase>, 
        <infura url>,
        0,
        3
      ),
     network_id: 42
  }
},
```

**2. Deploy to kovan testnet**

```
truffle migrate --reset --network kovan
```

**3. Deploy frontend**

in frontend root:
```
npm run build
```

deploy on build folder on [netlify](https://www.netlify.com/) or [digitalocean](https://www.digitalocean.com/)
