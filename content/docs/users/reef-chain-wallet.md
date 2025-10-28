---
title: "Reef Chain Wallet"
description: "Reef Chain Wallet is the premier way to experience what the Reef ecosystem has to offer. Available now for Android and iOS."
lead: "Reef Chain Wallet is a mobile app that allows you to quickly create a Reef wallet, and start exploring the Reef ecosystem."
date: 2024-10-27T08:48:57+00:00
lastmod: 2025-10-27T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "users"
weight: 100
toc: true
---

# Reef Chain Wallet - Frequently Asked Questions (FAQ)

## General Questions

### What is Reef Chain Wallet?

Reef Chain Wallet is the official mobile wallet app for the Reef Chain ecosystem. It's a native mobile application designed to provide a secure, user-friendly way to manage your digital assets on Reef Chain. The wallet allows you to create and manage accounts, store and transfer tokens, view and send NFTs, and connect to decentralized applications (dApps) using WalletConnect.

### What platforms is Reef Chain Wallet available on?

Reef Chain Wallet is available on:
- **Android** - Available on Google Play Store
- **iOS** - Available on Apple App Store

The app requires iOS 16.0 or later for iPhone and iPad devices.

### Is Reef Chain Wallet free to use?

Yes, Reef Chain Wallet is completely free to download and use. However, you'll need to pay network transaction fees (gas fees) when sending tokens or interacting with smart contracts on Reef Chain. These fees are typically very low, averaging around 5 REEF per transaction.

### What is Reef Chain?

Reef Chain is a Layer 1 blockchain built using Substrate Framework, designed to make blockchain applications accessible to everyone. It's an EVM-compatible blockchain that offers fast transactions, low fees, and high scalability. Reef Chain uses a Nominated Proof of Stake (NPoS) consensus mechanism and supports Solidity smart contracts, making it easy for developers to migrate their dApps from Ethereum.

---

## Getting Started

### How do I create a new account/wallet?

1. Download Reef Chain Wallet from the App Store (iOS) or Google Play Store (Android)
2. Open the app and select "Add account"
3. Follow the on-screen instructions to set up your wallet
4. **IMPORTANT**: Write down your recovery phrase (seed phrase) and store it in a safe place
5. Set a secure password or enable biometric authentication
6. Name your account (you can create multiple accounts within the app)

### What is a recovery phrase (seed phrase)?

Your recovery phrase, also called a seed phrase or mnemonic, is a series of 12 words that acts as the master key to your wallet. This phrase is the ONLY way to recover your wallet if you lose access to your device. 

**Critical Security Notes:**
- Write it down on paper and store it in a safe place
- NEVER share your recovery phrase with anyone
- NEVER take a screenshot or store it digitally
- Anyone with your recovery phrase has complete access to your funds
- Reef Chain Wallet support will NEVER ask for your recovery phrase

### Can I import an existing wallet?

Yes! If you already have a Reef Chain wallet (from the browser extension or another device), you can import it into Reef Chain Wallet using your recovery phrase:

1. Open Reef Chain Wallet
2. Select "Add"
3. Select "From recovery phrase"
4. Enter your 12 word recovery phrase in the correct order
5. Set a new password or enable biometric authentication
6. Your account will be restored

### How do I backup my account/wallet?

Your recovery phrase IS your backup. When you first create your wallet, you'll be shown a recovery phrase - this must be written down and stored securely. You can also view your recovery phrase later in the app settings (typically under Security or Backup), but you'll need to authenticate with your PIN or biometrics first.

---

## Account Management

### Can I create multiple accounts?

Yes! Reef Chain Wallet allows you to create, name, rename, and delete multiple accounts within the same wallet. All accounts are derived from different recovery phrases, separating activity across accounts and making it harder for attackers to gain access to all your accounts at once.

### How do I switch between accounts?

In Reef Chain Wallet, you can easily switch between your accounts from the Wallet screen. Look for the vertical ellipsis — ⋮ — next to the account you want to use; select the vertical ellipsis ⋮ and then choose "Select Account".

### Can I delete an account?

Yes, you can delete accounts from within the app. However, this only removes the account from your view in the app - the account and any funds in it still exist on the blockchain. You can restore deleted accounts at any time using the same recovery phrase.

---

## Security & Privacy

### Is my data collected by Reef Chain Wallet?

No. According to the App Store privacy policy, Reef Chain Wallet does NOT collect any data from users. The app is fully self-custodial, meaning:
- You control your private keys
- Your data is encrypted and stored only on your device
- No user information is shared with Reef Chain or third parties
- The wallet operates without requiring personal information or KYC

### What does "self-custodial" mean?

Self-custodial (or non-custodial) means YOU have complete control over your digital assets. Unlike exchange wallets where the exchange holds your private keys, Reef Chain Wallet stores your private keys directly on your device. You are the only person who can access your funds - Reef Chain cannot access, freeze, or recover your wallet.

This also means you're fully responsible for keeping your recovery phrase safe. If you lose it, no one can help you recover your funds.

### How do I secure my wallet?

**Essential Security Steps:**
1. **Write down your recovery phrase** and store it in multiple secure physical locations
2. **Enable biometric authentication** (Face ID/Touch ID) or use a strong password
3. **Never share your recovery phrase** with anyone - not even support staff
4. **Verify app authenticity** - only download from official App Store/Google Play
5. **Keep your device secure** - use device encryption and lock screen
6. **Be cautious of phishing** - double-check URLs and app authenticity
7. **Use unique passwords** - don't reuse passwords from other services
8. **Update regularly** - keep the app and your device OS up to date

### What if I lose my phone?

If you lose your phone but have your recovery phrase:
1. Download Reef Chain Wallet on a new device
2. Select "Add"
3. Select "From recovery phrase"
4. Enter your recovery phrase
5. Your account will be restored

If you've lost both your phone AND your recovery phrase, your funds are permanently inaccessible. This is why backing up your recovery phrase is critically important.

### Can someone hack my wallet?

Reef Chain Wallet stores your private keys encrypted on your device. The main security risks come from:
- Someone obtaining your recovery phrase
- Malware on your device
- Phishing attacks tricking you into revealing sensitive information
- Social engineering

Following the security best practices above minimizes these risks. The app itself uses industry-standard encryption and security measures.

---

## Sending & Receiving Tokens

### How do I receive REEF or other tokens?

1. Open Reef Chain Wallet
2. Select the vertical ellipsis ⋮ for the account you want to receive tokens into
3. Tap "Copy native address" or "Copy EVM address"
4. Share your wallet address with the sender by copying and sending your wallet address (a long string starting with letters and numbers)

**Important**: Always double-check the address before sharing. Sending crypto to the wrong address usually results in permanent loss.

### How do I send tokens?

1. Open Reef Chain Wallet
2. Select the account containing the tokens you want to send
3. Choose the token from your balance list
4. Tap "Send"
5. Enter or scan the recipient's wallet address
6. Enter the amount to send
7. Review the transaction details and gas fee
8. Confirm and authorize the transaction with your password or biometric
9. Wait for the transaction to be confirmed on the blockchain

### What are transaction fees (gas fees)?

Transaction fees (also called gas fees) are small amounts of REEF paid to validators who process your transaction on the Reef Chain network. These fees help secure the network and prevent spam.

Reef Chain is known for its LOW fees - the average transaction costs only about 5 REEF. The fee is automatically calculated based on network conditions, though you may be able to adjust it in advanced settings for faster processing.

### Why is my transaction pending?

Transactions on Reef Chain are typically processed very quickly (within seconds). If your transaction is pending:
- The network may be experiencing high traffic (rare on Reef Chain)
- Your gas fee may have been set too low
- There may be an issue with network connectivity

You can check transaction status on ReefScan (Reef's blockchain explorer) by entering your transaction hash.

### Can I cancel a transaction?

Once a transaction is broadcast to the Reef Chain network, it cannot be cancelled.

### What if I send tokens to the wrong address?

Blockchain transactions are irreversible. If you send tokens to the wrong address, they cannot be recovered unless you control that address. Always double-check recipient addresses before confirming transactions.

---

## Tokens & Assets

### What tokens can I store in Reef Chain Wallet?

Reef Chain Wallet can store:
- REEF (the native token)
- Any token created on Reef Chain (Reef20 tokens)
- ERC-20 tokens that have been bridged to Reef Chain

The wallet automatically detects and displays tokens in your accounts.

### How do I swap tokens? (Android only)

Reef Chain Wallet includes built-in token swapping powered by ReefSwap, the native decentralized exchange (DEX) on Reef Chain:

1. Open the wallet and select "Swap" or navigate to the swap feature
2. Select the token you want to swap FROM
3. Select the token you want to swap TO
4. Enter the amount
5. Review the exchange rate and slippage tolerance (default is 0.8%)
6. Confirm the swap
7. Sign the transaction(s) to complete

For low-liquidity token pairs, you may need to increase slippage tolerance.

### What is slippage tolerance?

Slippage tolerance is the maximum price movement you're willing to accept for a swap. For example, 0.8% slippage means you'll accept up to a 0.8% worse rate than quoted. Higher slippage may be needed for:
- Tokens with low liquidity
- Large trade amounts
- Volatile market conditions

### Can I view NFTs in my wallet?

Yes! Reef Chain Wallet includes NFT support. You can:
- View NFTs in your collection
- Send NFTs to other addresses (Android only)
- View NFT metadata and images

To view your NFTs, look for an "NFTs" or "Collectibles" section in the wallet.

### How do I add a custom token?

Most tokens on Reef Chain are automatically detected and displayed. If a token doesn't appear:
1. Look for "Add Token" or "Import Token" in settings
2. Enter the token's contract address
3. The token details should auto-populate
4. Confirm to add it to your wallet view

You can find token contract addresses on ReefScan.

---

## WalletConnect & dApps

### What is WalletConnect?

WalletConnect is a popular open-source protocol that allows your mobile wallet to securely connect to decentralized applications (dApps) on your computer or within other apps. It uses QR code scanning to establish an encrypted connection between your wallet and the dApp.

### How do I connect to a dApp using WalletConnect?

1. Open the dApp in your web browser or the dApp's app
2. Look for "Connect Wallet" and select "WalletConnect"
3. A QR code will be displayed
4. Open Reef Chain Wallet and tap the WalletConnect scanner (`W` icon in top-right corner)
5. Scan the QR code displayed by the dApp
6. Review the connection request and approve it
7. You're now connected! You can interact with the dApp while your wallet remains on your phone

### What can I do with WalletConnect?

With WalletConnect, you can:
- Use ReefSwap DEX on your computer while managing keys on your phone
- Interact with DeFi protocols, games, and NFT marketplaces
- Sign transactions securely from your mobile wallet
- Connect to multiple dApps simultaneously

### Is WalletConnect secure?

Yes. WalletConnect uses end-to-end encryption and never exposes your private keys. The connection requires explicit approval from you, and you must confirm each transaction on your mobile device. You can also disconnect from dApps at any time.

### What is ReefSwap?

ReefSwap is the native decentralized exchange (DEX) on Reef Chain. It allows you to:
- Swap tokens directly on Reef Chain
- Provide liquidity to earn fees
- Create token pairs
- Trade with minimal slippage thanks to deep liquidity pools

ReefSwap is built into Reef Chain Wallet's swap feature and can also be accessed via web browser at reefswap.com.

### How do I disconnect from a dApp?

In Reef Chain Wallet:
1. Go to Settings or WalletConnect section
2. View your active connections
3. Select the dApp you want to disconnect from
4. Tap "Disconnect" or the disconnect icon

You can also disconnect directly from the dApp's interface.

---

## Technical Questions

### Can I use the same address across devices?

Yes! Your wallet address is derived from your recovery phrase. You can access the same accounts on multiple devices by importing your recovery phrase into Reef Chain Wallet on each device. All devices will show the same balances and transaction history because they're viewing the same accounts on the Reef Chain blockchain.

### What is an EVM address?

EVM (Ethereum Virtual Machine) addresses are compatible with Ethereum-style addresses. Reef Chain is EVM-compatible, meaning you can claim and use an EVM-formatted address. This allows:
- Easier integration with Ethereum-based tools
- Compatibility with MetaMask and other Ethereum wallets (via Reef Chain configuration)
- Interaction with EVM-compatible dApps

### Where can I view my transaction history?

Transaction history is available:
1. **On ReefScan** - Visit reefscan.com and search for your wallet address to see complete on-chain history
2. **On SubScan** - Visit reef.subscan.io and search for your wallet address to see on-chain history and analytics

---

## Troubleshooting

### The app won't open or keeps crashing

Try these steps:
1. Force close the app and reopen it
2. Check for app updates in the App Store/Google Play
3. Restart your device
4. Ensure your device OS is up to date
5. If issues persist, uninstall and reinstall the app (make sure you have your recovery phrase first!)

### My balance isn't showing correctly

If your balance appears incorrect:
1. Pull down to refresh the balance
2. Check your network connection
3. Ensure you're viewing the correct account
4. Verify the transaction on ReefScan
5. Wait a few moments and refresh again (sometimes there's a brief delay)

### I can't complete a transaction

Common solutions:
1. **Ensure you have enough REEF** for gas fees
2. **Check network connection** - you need internet to broadcast transactions
3. **Verify recipient address** is valid and correctly formatted
4. **Update the app** to the latest version

### A token isn't showing in my wallet

If a token isn't displaying:
1. Refresh your wallet balance
2. Check if the token is on Reef Chain (not Ethereum or BNB Smart Chain)
3. Manually add the token using its contract address
4. Verify the transaction on ReefScan to confirm the tokens were sent to your address

### I forgot my password

If you forget your PIN but have your recovery phrase:
1. Uninstall and reinstall the app
2. Select "Add"
2. Select "From recovery phrase"
3. Enter your recovery phrase
4. Set a new password

If you've forgotten both your password and recovery phrase, your wallet cannot be recovered.

### How do I contact support?

For support:
- **Community Discord** - Join Reef's Discord for community help
- **Community Telegram** - Join Reef's Telegram for community help
- **Official Documentation** - Visit docs.reef.io for guides and documentation
- **X (Twitter)** - Follow @Reef_Chain for updates and announcements
- **App Store/Google Play Reviews** - Report technical issues (but NEVER share your recovery phrase)

**Warning**: Be extremely cautious of scammers posing as support. Official Reef support will NEVER:
- Ask for your recovery phrase or private keys
- Ask you to send them REEF or other tokens
- Direct message you first on social media
- Request remote access to your device

---

## Advanced Features

### Can I stake REEF from the wallet?

Currently, Reef Chain Wallet focuses on core wallet functionality, token swaps, and dApp connectivity. For staking REEF:
- You can nominate validators through https://console.reefscan.com
- Staking features are also available in Fearless Wallet's mobile app

Check reef.io for current staking options and supported platforms.

### Can I use hardware wallet support?

Reef Chain Wallet is designed as a mobile-first self-custodial wallet. For hardware wallet support:
- Ledger devices support REEF through https://console.reefscan.com
- You can use hardware wallets with the Reef browser extension
- Mobile hardware wallet integration may be added in future updates

### What are the network settings?

Reef Chain Wallet is pre-configured for Reef mainnet. You typically don't need to adjust network settings. For developers or advanced users who need testnet access, check the app settings for network configuration options.

### Can I export my private keys?

While Reef Chain Wallet focuses on recovery phrase-based backup, you may be able to export individual account private keys from the advanced settings (this varies by app version). Remember:
- Your recovery phrase controls ALL accounts
- Individual private keys control only specific accounts
- Never share private keys with anyone
- Store exported keys as securely as recovery phrases

---

## Fees & Costs

### Are there any fees to use the wallet?

The wallet app itself is free. However, you'll pay:
- **Network transaction fees (gas)** - typically around 5 REEF per transaction
- **Swap fees** - small fees when using ReefSwap (a percentage of trade value)
- **No additional wallet fees** - Reef Chain Wallet doesn't charge extra fees beyond network costs

### Why do I need REEF for transaction fees?

REEF is the native token of Reef Chain and is required to pay for all on-chain operations:
- Sending tokens
- Interacting with smart contracts
- Swapping on ReefSwap
- Creating or transferring NFTs

Always keep some REEF in your wallet for gas fees.

### How much REEF do I need for fees?

For typical usage:
- **Minimum recommended**: 100-500 REEF
- **Average transaction**: ~5 REEF
- **Token swaps**: 5-20 REEF (varies by complexity)

These amounts can perform many transactions and are very affordable compared to other blockchains.

---

## Token Migration (Important)

### What is the REEF token migration?

REEF was originally an ERC-20 token on Ethereum and BEP-20 token on BNB Smart Chain. Reef Chain now has its own native REEF token (Reef20). Users need to bridge/swap their old tokens to the new Reef20 format.

### How do I migrate my REEF tokens?

1. Visit the official Reef Bridge at reefbridge.app
2. Connect your wallet containing ERC-20 or BEP-20 REEF
3. Follow the bridge process to convert to Reef20
4. **Deadline**: Complete migration before Q1 2026

### What happens if I don't migrate?

After the Q1 2026 deadline:
- ERC-20 and BEP-20 REEF will not be supported by centralized exchanges
- You won't be able to sell or trade unmigrated tokens on most platforms
- Reef Chain Wallet only supports native Reef20 REEF

**Action required**: Bridge your tokens as soon as possible to avoid issues.

---

## Getting Help

### Where can I learn more about Reef Chain?

- **Official Website**: reef.io
- **Documentation**: docs.reef.io
- **ReefScan Explorer**: reefscan.com
- **Twitter/X**: @Reef_Chain
- **Discord**: Join the official Reef community Discord
- **Announcements**: Read updates on blog.reef.io

### How do I report a bug?

1. Document the issue with screenshots if possible
2. Report through the App Store (iOS) or Google Play (Android) review system
3. Use the chat bubble in the bottom-right corner report it to customer support
4. Do NOT include sensitive information like recovery phrases

### Is there a user guide or tutorial?

Check these resources:
- In-app tutorials (first time you open certain features)
- Reef blog at blog.reef.io for step-by-step guides
- Official YouTube channel for video tutorials
- Community-created content on X and Discord

---

## Important Reminders

### Security Best Practices Checklist

✅ Write down your recovery phrase and store it securely offline
✅ Never share your recovery phrase or private keys with anyone
✅ Enable biometric authentication or use a strong PIN
✅ Verify all transaction details before confirming
✅ Only download Reef Chain Wallet from official app stores
✅ Be cautious of phishing attempts and fake support
✅ Keep your app and device software updated
✅ Keep some REEF for transaction fees
✅ Double-check addresses before sending tokens

### Red Flags - Common Scams

🚨 Anyone asking for your recovery phrase or private keys
🚨 "Support" agents direct messaging you first
🚨 Promises of free tokens or giveaways requiring you to send tokens first
🚨 Suspicious apps or websites that look similar to official ones
🚨 Pressure to act quickly or urgently
🚨 Requests to install remote access software

**Remember**: If something seems too good to be true, it probably is. When in doubt, verify through official Reef channels.

---

*This FAQ is designed for Reef Chain Wallet iOS launch (October 28, 2025). Some features may vary between iOS and Android versions. Information is based on current app store listings, Reef Chain documentation, and general cryptocurrency wallet best practices.*

*Last Updated: October 27, 2025*