---
title: "Hardhat Materials"
description: "Getting started with Hardhat on Reef Pelagia testnet"
lead: "Here's sample code for deploying smart contracts on Reef Pelagia testnet using Hardhat."
date: 2026-03-05T00:00:00+00:00
lastmod: 2026-03-05T00:00:00+00:00
draft: false
images: []
menu:
  docs:
    parent: "developers"
weight: 230
toc: true
---

## Test and Deploy with Hardhat

Master Solidity smart contract development with Hardhat. 
Learn testing, deployment, and network interaction in one comprehensive tutorial.

[Get Started](https://docs.polkadot.com/tutorials/smart-contracts/launch-your-first-project/test-and-deploy-with-hardhat)

---

## Contracts Code Blob Size Disclaimer

- The maximum contract code blob size on Reef Pelagia testnet is **100 kilobytes**, significantly larger than Ethereum’s EVM limit of **24 kilobytes**.
- For detailed comparisons and migration guidelines, see the  
  [EVM vs. PolkaVM](https://docs.polkadot.com/polkadot-protocol/smart-contract-basics/evm-vs-polkavm/#current-memory-limits) documentation page.

---

### Overview

Hardhat is a robust development environment for Ethereum-compatible chains that makes smart contract development more efficient. This guide walks you through the essentials of using Hardhat to create, compile, test, and deploy smart contracts on Reef Chain.

---

### Prerequisites

Before getting started, ensure you have:

- [Node.js](https://nodejs.org/) (v16.0.0 or later) and npm installed.  
  - Consider using Node.js **22.18+** and npm **10.9.0+** to avoid issues with the Polkadot plugin.
- Basic understanding of Solidity programming.
- Some **REEF** test tokens to cover transaction fees (easily obtainable from Discord).

---

### Set Up Hardhat
1. Create a new directory for your project and navigate into it:
```
mkdir hardhat-example
cd hardhat-example
```
2. Initialize a new npm project
```
npm init -y
```
3. To interact with Reef Chain, Hardhat requires the following plugin to compile contracts to PolkaVM bytecode and to spawn a local node compatible with PolkaVM
```
npm install --save-dev @parity/hardhat-polkadot@0.1.9
```
4. Create a Hardhat project
```
npx hardhat-polkadot init
```
Select Create a JavaScript project when prompted and follow the instructions. <br>
After that, your project will be created with three main folders:

- **`contracts`**: Where your Solidity smart contracts live.
- **`test`**: Contains your test files that validate contract functionality.
- **`ignition`**: Deployment modules for safely deploying your contracts to various networks.

5. Add the following folder to the .gitignore file if it is not already there
```
echo '/ignition/deployments/' >> .gitignore
```
6. Finish the setup by installing all the dependencies:
```
npm install
```
**Note**

This last step is needed to set up the `hardhat-polkadot` plugin. It will install the `@parity/hardhat-polkadot` package and all its dependencies. <br>
In the future, the plugin will handle this automatically.

---

### Compile Your Contract

The plugin will compile your Solidity contracts for Solidity versions 0.8.0 and higher to be PolkaVM compatible. When compiling your contract, there are two ways to configure your compilation process:

- npm compiler: Uses library [`@parity/resolc`](https://www.npmjs.com/package/@parity/resolc) for simplicity and ease of use.
- Binary compiler: Uses your local `resolc` binary directly for more control and configuration options.

To compile your project, follow these instructions:

Modify your Hardhat configuration file to specify which compilation process you will be using and activate the `polkavm` flag in the Hardhat network:

npm configuration:
```
// hardhat.config.js
require('@nomicfoundation/hardhat-toolbox');

require('@parity/hardhat-polkadot');

/** @type import('hardhat/config').HardhatUserConfig */
module.exports = {
  solidity: '0.8.28',
  resolc: {
    compilerSource: 'npm',
  },
  networks: {
    hardhat: {
      polkavm: true,
    },
  },
};
``` 
Binary configuration:
```
// hardhat.config.js
require('@nomicfoundation/hardhat-toolbox');

require('@parity/hardhat-polkadot');

/** @type import('hardhat/config').HardhatUserConfig */
module.exports = {
  solidity: '0.8.28',
  resolc: {
    compilerSource: 'binary',
    settings: {
      compilerPath: 'INSERT_PATH_TO_RESOLC_COMPILER',
    },
  },
  networks: {
    hardhat: {
      polkavm: true,
    },
  },
};
```

For the binary configuration, replace `INSERT_PATH_TO_RESOLC_COMPILER` with the proper path to the binary. <br>
To obtain the binary, check the [releases](https://github.com/paritytech/revive/releases) section of the `resolc` compiler, and download the latest version.

The default settings used can be found in the [`constants.ts`](https://github.com/paritytech/hardhat-polkadot/blob/v0.1.5/packages/hardhat-polkadot-resolc/src/constants.ts#L8-L23) file of the `hardhat-polkadot` source code. <br>
You can change them according to your project needs. Generally, the recommended settings for optimized outputs are the following:

`hardhat.config.js`
```
resolc: {
  ...
  settings: {
    optimizer: {
      enabled: true,
      parameters: 'z',
      fallbackOz: true,
      runs: 200,
    },
    standardJson: true,
  },
  ...
}
```

You can check the [`ResolcConfig`](https://github.com/paritytech/hardhat-polkadot/blob/v0.1.5/packages/hardhat-polkadot-resolc/src/types.ts#L26) for more information about compilation settings.

- Compile the contract with Hardhat:
    
    `npx hardhat compile`
    
- After successful compilation, you'll see the artifacts generated in the `artifacts-pvm` directory:
    
    `ls artifacts-pvm/contracts/*.sol/`
    
    You should see JSON files containing the contract ABI and bytecode of the contracts you compiled.

    ---

### Set Up a Testing Environment
Hardhat allows you to spin up a local testing environment to test and validate your smart contract functionalities before deploying to live networks. <br>
The `hardhat-polkadot` plugin provides the possibility to spin up a local node with an ETH-RPC adapter for running local tests.

For complete isolation and control over the testing environment, you can configure Hardhat to work with a fresh local Reef node.  <br>
Instead, you can skip down to **Deploying to Pelagia** at the end.


**⚠️Warning⚠️**

If you're using the default `hardhat.config.js` created by the `hardhat-polkadot` plugin: <br>
it includes a `forking` section pointing to the Reef Pelagia Testnet.<br>

When you run `npx hardhat node`, Hardhat will start a fork of that network. <br>

To use your local node instead, comment out the `forking` section.
 <br>
Otherwise, `npx hardhat node` will continue to use the forked network even if a local node is defined in the configuration.

Once configured, start your chosen testing environment with:

`npx hardhat node`

This command will launch either the forked network or local node (depending on your configuration) along with the ETH-RPC adapter, 
providing you with a complete testing environment ready for contract deployment and interaction. 

By default, the Substrate node will be running on `localhost:8000` and the ETH-RPC adapter on `localhost:8545`

The output will be something like this:
```
adejare-laptop:~$ npx hardhat node

Starting server at 127.0.0.1:8000
../bin/substrate-node --rpc-port=8000 --dev
Starting the Eth RPC Adapter at 127.0.0.1:8545
../bin/eth-rpc --node-rpc-url=ws://localhost:8000 --dev
2025-05-29 13:00:32 Running in --dev mode, RPC CORS has been disabled.
2025-05-29 13:00:32 Running in --dev mode, RPC CORS has been disabled.
2025-05-29 13:00:32 🌐 Connecting to node at: ws://localhost:8000 ...
2025-05-29 13:00:32 Substrate Node
2025-05-29 13:00:32 ✌️ version 3.0.0-dev-f73c228b7a1
2025-05-29 13:00:32 ❤️ by Parity Technologies <admin@parity.io>, 2017-2025
2025-05-29 13:00:32 📋 Chain specification: Development
2025-05-29 13:00:32 🏷 Node name: electric-activity-4221
2025-05-29 13:00:32 👤 Role: AUTHORITY
2025-05-29 13:00:32 💾 Database: RocksDb at /var/folders/f4/7rdt2m9d7j361dm453cpggbm0000gn/T/substrateOaoecu/chains/dev/db/full
2025-05-29 13:00:36 [0] 💸 generated 1 npos voters, 1 from validators and 0 nominators
```
 ---

### Test Your Contract
When testing your contract, be aware that [`@nomicfoundation/hardhat-toolbox/network-helpers`](https://hardhat.org/hardhat-network-helpers/docs/overview) is not fully compatible with Reef Pelagia’s available RPCs. 

Specifically, Hardhat-only helpers like `time` and `loadFixture` may not work due to missing RPC calls in the node. 

For more details, refer to the [Compatibility](https://github.com/paritytech/hardhat-polkadot/tree/main/packages/hardhat-polkadot-node#compatibility) section in the `hardhat-revive` docs. 

You should avoid using helpers like `time` and `loadFixture` when writing tests.

To run your tests:

1. Update the `hardhat.config.js` file accordingly to the [Set Up a Testing Environment](https://docs.polkadot.com/develop/smart-contracts/dev-environments/hardhat/#set-up-a-testing-environment) section.
2. Execute the following command to run your tests:
    
    `npx hardhat test`

---

### Deploying to Reef Pelagia
After testing your contract locally, you can deploy it to a live network. <br>
This guide will use the Reef Pelagia testnet as the target network. 

Here's how to configure and deploy:

1. Fund your deployment account with enough tokens to cover gas fees. In this case, the needed tokens are REEF.
2. Export your private key and save it in your Hardhat environment:

```
npx hardhat vars set PRIVATE_KEY "INSERT_PRIVATE_KEY"
```

3. Check that your private key has been set up successfully by running:

```
npx hardhat vars get PRIVATE_KEY
```

4. Update your Hardhat configuration file with network settings for the Reef network you want to target:

```
// hardhat.config.js
require('@nomicfoundation/hardhat-toolbox');

require('@parity/hardhat-polkadot');

const { vars } = require('hardhat/config');

/** @type import('hardhat/config').HardhatUserConfig */
module.exports = {
    ...
    networks: {
      hardhat: {
        ...
      },
      localNode: {
        ...
      },
      reefPelagiaTestnet: {
        polkavm: true,
        url: 'http://34.123.142.246:8545',
        accounts: [vars.get('PRIVATE_KEY')],
      },
    },
  },
};
```
5. Deploy your contract using Ignition:

```
npx hardhat ignition deploy ./ignition/modules/MyToken.js --network reefPelagiaTestnet
```

6. Use this [verifier](https://testnet-sc-verifier-dmxrcv-2e0f9f-72-60-35-83.traefik.me/api/v2/verifier/solidity/versions) to verify your smart contract.

---

### Interacting with your contract
Once deployed, you can create a script to interact with your contract. <br>
To do so, create a file called `scripts/interact.js` and add some logic to interact with the contract.

For example, for the default `MyToken.sol` contract, you can use the following file that connects to the contract at its address and retrieves the `unlockTime`, which represents when funds can be withdrawn. 

The script converts this timestamp into a readable date and logs it. 

It then checks the contract's balance and displays it. <br>
Finally, it attempts to call the withdrawal function on the contract, but it catches and logs the error message if the withdrawal is not yet allowed (e.g., before `unlockTime`).

```
// interact.js

const hre = require('hardhat');

async function main() {
  // Get the contract factory
  const MyToken = await hre.ethers.getContractFactory('MyToken');

  // Replace with your deployed contract address
  const contractAddress = 'INSERT_CONTRACT_ADDRESS';

  // Attach to existing contract
  const token = await MyToken.attach(contractAddress);

  // Get signers
  const [deployer] = await hre.ethers.getSigners();

  // Read contract state
  const name = await token.name();
  const symbol = await token.symbol();
  const totalSupply = await token.totalSupply();
  const balance = await token.balanceOf(deployer.address);

  console.log(`Token: ${name} (${symbol})`);
  console.log(
    `Total Supply: ${hre.ethers.formatUnits(totalSupply, 18)} tokens`,
  );
  console.log(
    `Deployer Balance: ${hre.ethers.formatUnits(balance, 18)} tokens`,
  );
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
```

Once done, Run your interaction script:
```
npx hardhat run scripts/interact.js --network reefPelagiaTestnet
```
---

### Upgrading the Plugin
If you already have a Hardhat Polkadot project and want to upgrade to a newer version of the plugin, to avoid errors (for example, `Cannot find module 'run-container'`), you can clean your dependencies by running the following commands:

`rm -rf node_modules package-lock.json`

After that, you can upgrade the plugin to the latest version by running the following commands:

`npm install --save-dev @parity/hardhat-polkadot@latest
npm install`

Consider using [Node.js](https://nodejs.org/) 22.18+ and [npm](https://www.npmjs.com/) version 10.9.0+ to avoid issues with the plugin.


