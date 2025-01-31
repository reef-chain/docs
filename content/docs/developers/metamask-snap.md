---
title: "Metamask Snap"
description: "The Reef Chain Wallet Snap allows users to interact with the Reef Chain using MetaMask.."
lead: "The Reef Chain Wallet Snap allows users to interact with the Reef Chain using MetaMask."
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "developers"
weight: 260
toc: true
---

## What is Reef Snap?

Reef Snap is a **MetaMask Snap** that integrates Reef Chain with MetaMask, allowing users to seamlessly interact with the Reef Chain. 

Users can install the Reef Snap from Metamask's snap store.

![metamask snap](/images/metamask-snap/header.png "")

## Reef Snap in Action

This video showcases the seamless integration between MetaMask and Reef Chain, account creation, mnemonic generation, exporting accounts, signing transactions, fetching on chain data etc.

<video width="600" controls> <source src="/videos/reef-snap-demo.mp4" type="video/mp4"> Your browser does not support the video tag. </video>

## How to install Reef Snap? (Locally)

### Requirements

- Git
- Metamask Flask
- Node
- Yarn

### Procedure 
1. **Clone the Repository**

  Clone the official MetaMask Snap repository from Reef Chain Github:

  ```bash
  git clone https://github.com/reef-chain/metamask-snap
  ```

2. **Install Dependencies**
  
  Install required dependencies and start the server:

  ```bash
  yarn install && yarn start
  ```

  If the server starts successfully, you should see the following log:
  
  ![terminal-log](/images/metamask-snap/terminal-log.png "")

**3. Access the Interface**
 
  Visit http://localhost:8000/ on your Browser, you should be able to see an interface like this:

  ![terminal-log](/images/metamask-snap/snap-browser-preview.png "")


  {{< alert icon="💡" text="Note that you need to install Metamask Flask for local development." >}}

### Raw Signing

Signing Raw messages with Reef Snap on Demo Interface.

1. Visit [http://localhost:8000](http://localhost:8000/) in browser.

![terminal-log](/images/metamask-snap/demo-1.png "")

2. Click on **Sign bytes** button & approve the Request.

![terminal-log](/images/metamask-snap/demo-2.png "")

Acknowledgement is given as an alert

![terminal-log](/images/metamask-snap/demo-3.png "")




## Important Links

1. Reef Snap Source code : [@reef-chain/metamask-snap](https://github.com/reef-chain/metamask-snap)

2. Reef Snap npm repository : [@reef-chain/reef-snap](https://www.npmjs.com/package/@reef-chain/reef-snap)

## Frequently Asked Questions

  **1. Can I use Reef Snap on Scuba Testnet?**

  **Yes**, Reef Snap supports both mainnet & testnet.

  **2. Can I sign messages and Send Transactions using Reef Snap?**

  **Yes**, Reef Snap supports signing messages & sending transactions using Metamask.

  **3. Is the Reef Chain MetaMask Snap secure?** 

  **Yes**, A Snap is a JavaScript program run in an isolated and secure execution environment. You can read more about it [here](https://docs.metamask.io/snaps/learn/about-snaps/)

  **4. Is it possible to add multiple Reef Chain accounts to MetaMask using Reef Snap?**
  
  **Yes**, you can manage multiple Reef Chain accounts within MetaMask using Reef Snap. Each account will have its own Reef Chain address and assets, and you can switch between them easily in MetaMask.