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
weight: 225
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

